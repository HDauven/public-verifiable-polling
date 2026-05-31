# Architecture

The architecture starts from the polling event and the artifacts it produces.

The backend should not determine the design. A local file store, HTTP service, transparency log, smart contract or DLT backend can all be backends if they publish the artifacts needed for verification.

These actors are logical roles. A deployment may combine them, but doing so can weaken privacy and trust assumptions.

## Actors

**Organizer**

Defines the polling event. This includes eligibility rules, polling rules, options or candidates, privacy mode, tally method and verification rules.

**Issuer**

Confirms that a participant is eligible. In the first version this can be a mock issuer. Later it could be an EUDI/OpenID4VP flow, a regulated identity flow, a membership list, a ticketing system or another eligibility source.

**Participant**

Receives event-scoped material after eligibility is confirmed. The participant uses that material to submit votes or other polling artifacts.

**Backend**

Accepts submissions and publishes artifacts. The first backend should be local and simple. It should not require a chain, production identity integration or any specific regulated system.

**Verifier**

Checks the published artifacts against the event rules and recomputes the result.

## Core Components

**Event config**

Machine-readable description of the event.

It should define eligibility policy, options or candidates, vote budget, per-option caps, tally method, privacy mode and verification rules.

**Eligibility issuer interface**

A generic interface for saying that a participant is eligible for a specific event.

The first implementation can be mocked. The interface should be shaped so real issuers can be added later.

**Event-scoped material**

Participants should not receive a permanent public polling identity.

The system should use event-scoped credentials, commitments or nullifiers so the verification layer does not require the participant's real identity.

**Rule engine**

The first rule engine should cover the basic rules needed for capped polling.

- one-person-one-vote;
- max `N` votes per participant;
- max `K` votes per option or candidate;
- round scoping;
- duplicate nullifier rejection.

**Public artifacts**

The backend should publish the artifacts needed for independent verification.

- event config;
- issuer or eligibility artifacts;
- accepted submissions;
- nullifier set;
- tally artifact;
- optional reference verifier output.

**Verifier**

The verifier should be useful on its own. A third party should be able to run it locally and check that the result follows the public rules.

## Verification Flow

1. Load the event config.
2. Load the published submissions.
3. Check that every submission belongs to the event and round.
4. Check that every selected option or candidate is valid.
5. Reject duplicate nullifiers.
6. Check vote budgets and per-option caps.
7. Recompute the tally.
8. Compare the computed tally with the published result.

The exact cryptographic construction can evolve. The verification semantics should stay understandable.

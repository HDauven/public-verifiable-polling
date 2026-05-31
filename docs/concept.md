# Concept

The project defines infrastructure for polling events where eligibility, rule enforcement and tallying can be checked afterwards.

The basic model has six parts:

1. An organizer defines a polling event.
2. An issuer confirms that a participant is eligible.
3. The participant receives event-scoped material.
4. The participant submits votes or other polling artifacts within the event rules.
5. The backend publishes enough information for independent verification.
6. A verifier checks that the result follows the published rules.

The backend should not define the project. The first implementation can use local files or a simple HTTP bulletin board. Later publication backends could include transparency logs, smart contracts, DLT backends or append-only object storage. Later eligibility mechanisms could include EUDI/OpenID4VP flows, regulated identity flows, membership lists or ticketing systems.

The published result should be verifiable while the privacy model can vary by use case.

## Polling Events

A polling event defines the rules and context for the poll.

- who is eligible;
- what participants can do;
- how many votes or submissions are allowed;
- whether there are per-option or per-candidate caps;
- what the options or candidates are;
- which privacy mode applies;
- which artifacts are published;
- how the result is verified.

The same model should work for different low-risk use cases, including cultural voting, community polls, association polling, participatory budgeting pilots and public consultations.

## Rationale

Many polling systems ask people to trust the operator. The operator collects eligibility information, accepts votes or submissions, runs the tally and publishes a result.

That may be fine for some settings, but it is weak as public infrastructure.

The project separates the parts that have to be trusted from the parts that can be checked. The issuer may still be trusted for eligibility. The backend may still be trusted to stay available. The tally and rule enforcement should be verifiable from public artifacts.

## First Target

The first version focuses on event-scoped pseudonyms with public verification.

Participants should not need to publish their real identity or use a permanent public voting identity. They should use event-scoped material instead. The published artifacts should contain enough information for the rules and result to be checked afterwards.

This does not provide full anonymity, but it is a practical first step. It keeps the verifier simple and makes the public artifact model easier to reason about.

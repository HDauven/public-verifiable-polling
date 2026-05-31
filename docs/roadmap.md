# Roadmap

## Phase One

The first phase should deliver a small but reviewable core.

- event config format;
- mock issuer;
- event-scoped pseudonym / commitment / nullifier model;
- simple local backend;
- rule engine for total vote budgets and per-option caps;
- public artifact bundle;
- verifier CLI/library;
- song-contest demo;
- test vectors;
- technical paper/spec;
- developer documentation.

After phase one, someone should be able to run a local polling event with a mock issuer, submit capped song-contest-style votes, publish the event artifacts and verify that the tally follows the published rules.

## Later Extensions

Identity and eligibility

- EUDI/OpenID4VP adapter;
- regulated identity adapter;
- bank/eID adapter;
- membership-list adapter;
- ticketing-system adapter;
- civic registry adapter.

Backends

- transparency log adapter;
- chain adapter;
- smart-contract adapter;
- DLT backend adapter;
- append-only object storage adapter.

Privacy

- encrypted ballot mode;
- batching;
- relay submission;
- metadata-minimizing backend patterns.

Governance

- multi-issuer support;
- threshold issuance;
- independent observer tooling;
- audit dashboards.

## Research Questions

- What exactly must be public for independent verification in each privacy mode?
- How should event-scoped commitments be derived and rotated?
- What issuer artifacts are enough to make over-issuance visible?
- Which rule semantics can be verified without weakening privacy?
- Where is the boundary between polling events and binding elections?

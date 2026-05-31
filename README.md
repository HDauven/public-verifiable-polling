# Public Verifiable Polling

Public Verifiable Polling is a research project for reusable infrastructure around eligibility-gated polling events.

A polling event is a process where a defined group of eligible people can take part under published rules, for example by voting, ranking options or submitting input.

The event defines who is eligible, what the rules are, how participants may vote or submit input, what artifacts are published and how the result can be checked afterwards.

The published artifacts should let a third party check that the outcome follows the event rules.

The privacy model can differ by use case. The first version focuses on event-scoped pseudonyms with public verification. Participants do not use a permanent public identity, while the published artifacts contain enough information to verify the result.

The planned first implementation starts with a mock issuer, a local backend, public artifacts, a verifier and a song-contest demo that exercises multi-vote rules.

## Repository

- `docs/concept.md` explains the core idea.
- `docs/architecture.md` describes the actors, artifacts and verification flow.
- `docs/privacy-modes.md` describes the privacy modes.
- `docs/threat-model.md` lists assumptions, guarantees and limitations.
- `docs/roadmap.md` separates phase-one work from later extensions.
- `demo/song-contest/` contains the song-contest demo notes.

## Scope

The project starts with non-binding polling events.

Production identity integrations, encrypted ballots, binding referenda, coercion resistance and chain-specific adapters are outside the first phase.

This repository currently focuses on the model, terminology and architecture.

Implementation artifacts will be added once the verification model is stable.

## License

Apache-2.0

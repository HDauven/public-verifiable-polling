# Privacy Modes

The result should remain publicly verifiable, but the privacy model can vary.

Different use cases need different guarantees, so the protocol should not assume a single privacy model.

## Mode 0 Public Participation

Identity or pseudonym may be public.

Rules are transparent and the tally is independently verifiable.

Useful for public consultations, open association votes, non-sensitive polls and public deliberation.

## Mode 1 Pseudonymous Participation

The participant uses an event-scoped pseudonym.

This avoids linking the event to a permanent public account or wallet. It does not, by itself, provide anonymity from the issuer or backend.

Useful for low-risk polls, community voting and demos.

## Mode 2 Anonymous Eligibility, Public Choice

Eligibility is verified, but the vote is not linked to a real identity or permanent public voting identity.

The choice may still be public.

This is the next privacy target after the basic pseudonymous flow. It is useful for cultural voting, participatory budgeting pilots, non-binding public consultations and association votes where a public tally is acceptable.

## Mode 3 Anonymous Eligibility, Encrypted Ballot

Eligibility is verified and ballot content is hidden. The final tally remains publicly verifiable.

This is later work.

It may be useful for more sensitive votes, higher-stakes polling and serious referendum research.

## First Implementation

The first implementation should start with Mode 1.

That keeps the mechanics simple while the event model, artifact model and verifier semantics are still being defined. Participants use event-scoped pseudonyms, so their activity is not tied to a permanent account or wallet.

Mode 2 is the next target. It keeps the public verification model, but separates eligibility from the public polling identity.

Mode 3 is later research work.

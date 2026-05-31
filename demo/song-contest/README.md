# Song-Contest Demo

The song-contest demo is the first planned demo for the project.

It is useful because the rules are easy to understand while still testing the mechanics of the protocol. Participants are eligible or not, each participant has a vote budget, votes can be spread across options, per-option caps can apply and duplicate voting needs to be rejected.

The final tally should be independently verifiable from the published artifacts.

The demo should sit on top of the core. It should not define the core.

## First Version

The first version can use a mock issuer, a local backend, published vote artifacts, a simple tally and a verifier that recomputes the result.

The demo should be understandable without production identity systems, chains or regulated backends.

## Why This Demo

Song-contest voting is familiar, low-risk and good for explaining multi-vote rules.

It also makes the limits of the first version easier to explain. The issuer is mocked, the event is non-binding and the published artifacts are used to verify the tally. The point is to demonstrate publicly verifiable polling mechanics, not to claim production election readiness.

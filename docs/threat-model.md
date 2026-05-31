# Threat Model

## Main Guarantee

A third-party verifier should be able to check that the published result follows the published event rules and accepted public artifacts.

That is the core guarantee.

## In Scope

The first version is mainly concerned with rule enforcement and tally correctness.

That means checking event configs, option validity, duplicate nullifiers, replayed submissions, vote budgets, per-option caps and tally consistency.

It should also document issuer trust assumptions and privacy limitations clearly.

## Assumptions

The verifier can check rule enforcement and tally consistency. It cannot, by itself, prove that the issuer behaved honestly.

The backend is expected to publish the relevant artifacts. If it withholds data, availability and completeness become separate problems.

The first version is for non-binding polling. It should not be presented as production election software.

## Issuer Trust

The issuer can cheat by issuing too many credentials or by issuing credentials to ineligible people.

The first version does not solve issuer honesty. It should make the issuer trust model explicit and publish basic issuance metadata where possible, such as event id, round id and issuance counts.

Multi-issuer setups, threshold issuance and audited issuance logs are later work.

## Metadata Leakage

Even when real identity and published vote artifacts are separated, timing, IP address, device fingerprinting or backend logs may leak information.

The first version should not claim network anonymity.

Later versions may look at batching, relays, delay windows or other ways to reduce metadata leakage.

## Coercion

Remote voting and polling systems cannot easily prevent coercion, vote selling or forced disclosure.

The first version should be scoped to non-binding polling and explicitly avoid coercion-resistance claims.

## Limits

The first version is limited in a few important ways.

- it does not provide coercion resistance;
- it does not provide network anonymity;
- it does not prove that the issuer only issued credentials to eligible people;
- it does not provide production identity proofing;
- it does not provide encrypted secret ballots;
- it is not designed for binding elections.

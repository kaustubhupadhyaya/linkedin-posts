---
title: "The first production incident I caused"
date: 2026-08-25
pillar: engineering
tags:
  - SoftwareEngineering
  - IncidentResponse
  - EngineeringCulture
---

I once took down production for 40 minutes because of a config flag I was "99% sure" was safe.

It was a Friday afternoon. I flipped a feature flag that had been sitting behind a "low risk" label for two sprints. Nobody re-reviewed it, because it had technically already been reviewed — back when "low risk" meant something different.

Twenty minutes later, error rates spiked. Not because the flag itself was wrong, but because two other services had quietly started depending on the old behavior, and nobody had updated the flag's description to say so.

We rolled back in six minutes. The real fix took three days: every flag now ships with an owner, an expiry date, and a one-line "what breaks if this flips" note — and that note has to be current before merge, not written once and forgotten.

That one rule has caught four risky flags since. None of them made it to a Friday afternoon.

What's one process change your team made after a single bad incident that's still paying off today?

#SoftwareEngineering #IncidentResponse #EngineeringCulture

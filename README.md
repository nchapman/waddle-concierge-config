# waddle-concierge-config

Measured Tinfoil container configuration for the [waddle](https://github.com/nchapman/waddle) **concierge** — the always-on, deliberately dumb lifecycle timer (one primitive: a table of `{instance, action, due}` rows).

The concierge is the one thing that never sleeps: it holds the scoped tinfoil admin key (org secret, injected at deploy — never in this repo) and boots/stops the waddle enclave per the timer table. Memory-only by design: a reboot wipes every row and session token; death is the strongest revocation. Egress is allowlisted to the controlplane alone — an enclave bounds the host, not its own bugs, so the one-verb surface plus the egress wall is the containment.

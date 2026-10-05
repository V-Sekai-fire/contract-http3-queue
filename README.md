# contract-http3-queue

A Lean 4 model of a server's inbound HTTP/3 packet queue and network wake loop, proving which concurrency discipline loses no packets.

## What it is for

The queue's cached length is modelled apart from its contents. Under some concurrent schedule the unlocked queue strands a packet, while a theorem shows the locked queue keeps the two equal on every schedule. A second model shows a network loop woken once per outbound datagram starves both directions, and that coalescing wake-ups to one in flight does not. Property-based testing finds the counterexamples.

## Build and run

```sh
lake build
lake exe queue_demo
```

## Licence

MIT; see `LICENSE`.

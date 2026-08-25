# Turing_Machine.sh

`Turing_Machine.sh` is a compact bounded Turing-machine system program.

It reads three stdin lines:

1. `M`: JSON transition table, or blank for the default unary halt machine.
2. `X`: input tape string.
3. `B`: finite step bound.

Transition format:

```json
{"q0,1":["1",1,"q0"],"q0,_":["_",0,"H"]}
```

Each rule maps `"state,symbol"` to `[write, move, next_state]`.

The program emits `Turing_Machine.clcert` with:

- `TR`: finite trace
- `STATUS`: `HALT`, `OPEN`, or `BOUND`
- `HALT`: existence of a finite halting witness
- `PCC`: proof-carrying certificate flag
- `ZE`: zero-lift residue flag

This is not a global halting-problem decider. It verifies finite traces and reports bounded/open states honestly.

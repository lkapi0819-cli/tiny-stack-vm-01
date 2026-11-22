# tiny-stack-vm-01

[![make.fun · tiny-stack-vm-01-run-20261122](https://make.fun/badge/tiny-stack-vm-01-run-20261122.svg)](https://make.fun/bounty/tiny-stack-vm-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=tiny-stack-vm-01-run-20261122)
[![rank](https://make.fun/badge/tiny-stack-vm-01-run-20261122/lkapi0819-cli/tiny-stack-vm-01/rank.svg)](https://make.fun/bounty/tiny-stack-vm-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-stack-vm-01-run-20261122)
[![reward](https://make.fun/badge/tiny-stack-vm-01-run-20261122/lkapi0819-cli/tiny-stack-vm-01/reward.svg)](https://make.fun/bounty/tiny-stack-vm-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=tiny-stack-vm-01-run-20261122)

A tiny stack virtual machine in a single `main.ts`: an exact interpreter for make.fun's tiny stack ISA v1 — wrapping 32-bit arithmetic (`Math.imul` for MUL, the `-2^31 / -1` and `x % -1` cases, unsigned DIVU/MODU/LTU, shift counts masked to 5 bits, arithmetic vs logical right shift), a 256-value data stack, a 64-deep call stack, 256 words of memory, and every trap with its own exit code (underflow 2, overflow 3, division by zero 4, bad opcode 5, bad memory address 6, call depth 7, empty RET 8, bad pc or truncated immediate 9, step limit 10, output limit 11), keeping the output written before a trap. On the kit's practice set it answers all 40 instances exactly (output bytes and exit code).

## Run it

```sh
MAKEFUN_INPUT_DIR=<dir of i001..i040> MAKEFUN_OUTPUT_DIR=<output dir> node main.ts
```

It reads `/input/<id>/program.bin` and `input.bin` for each instance and writes `/output/<id>/stdout.bin` and `exit.txt`.

---

<sub>Entered on [make.fun](https://make.fun/?ref=nhastfac&utm_source=github&utm_medium=readme&utm_campaign=tiny-stack-vm-01-run-20261122) · AI agents build software for cash rewards</sub>

# winograd convelution on riscv vector extension 1.0

run with arch riscv gcv extension bare metal

## build & run

need to copy pk from riscv toolchain bin folder into repo root dir

```bash
cp ${RISCV}/riscv32-unknown-elf/bin/pk .
```

```bash
cd hello
make run
```
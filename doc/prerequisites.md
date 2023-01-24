# prerequisites

## riscv gnu toolchain

commit id: 65056bdb149c87db4e7223c4e8b5466cf326ff86

```bash
$ git clone https://github.com/riscv/riscv-gnu-toolchain
# or
$ git clone https://gitee.com/mirrors/riscv-gnu-toolchain.git

$ git rm qemu spike pk
$ git submodule update --init --recursive
$ sudo apt-get install autoconf automake autotools-dev curl python3 libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev ninja-build

$ mkdir buid && cd build
$ ../configure --prefix=$RISCV --with-arch=rv32gcv
$ make
```

### spike riscv isa simulator

```bash
$ git clone https://github.com/riscv/riscv-isa-sim.git
# or
$ git clone https://gitee.com/mirrors/riscv-isa-sim.git

$ apt-get install device-tree-compiler
$ mkdir buid && cd build
$ ../configure --prefix=$RISCV
$ make
$ make install
```

### PK

```bash
$ git clone https://github.com/riscv-software-src/riscv-pk.git
# or
$ git clone https://hub.fastgit.xyz/riscv-software-src/riscv-pk.git
$ mkdir buid && cd build
$ ../configure --prefix=$RISCV --host=riscv32-unknown-elf
$ make
$ make install
```
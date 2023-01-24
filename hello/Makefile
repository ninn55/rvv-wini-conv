PREFIX = riscv32-unknown-elf-
CC = $(PREFIX)gcc
CXX = $(PREFIX)g++
AS = $(PREFIX)AS
LD = $(PREFIX)ld
NM = $(PREFIX)nm
GDB = $(PREFIX)gdb
MKDIR = mkdir -p

SRC_DIRS = .
BUILD_DIR = $(SRC_DIRS)/build

INC=\
-I$(SRC_DIRS) \
-I$(SRC_DIRS)/../include

CXXFLAGS = $(INC) -O3 -DNDEBUG --std=c++11 -g
CCFLAGS = $(INC) -O3 -DNDEBUG --std=c99 -g
LDFLAGS = -lm

TARGET_EXEC = hello

SRCS= $(shell find $(SRC_DIRS) -name *.c)
OBJS = $(patsubst %.c,%.o,$(SRCS))
OBJS := $(addprefix $(BUILD_DIR)/, $(OBJS))

all: $(BUILD_DIR)/$(TARGET_EXEC)

$(BUILD_DIR):
	$(MKDIR) $@

$(BUILD_DIR)/%.o: %.c $(BUILD_DIR)
	$(CC) $(CCFLAGS) -c $< -o $@

$(BUILD_DIR)/$(TARGET_EXEC) : $(OBJS) $(BUILD_DIR)
	$(CC) $(LDFLAGS) $(OBJS) -o $@

.PHONY: 
	run clean

run: $(BUILD_DIR)/$(TARGET_EXEC)
	spike --isa rv32gcv ../pk $<

clean:
	rm -rf $(BUILD_DIR)
# SYSC 4001 Assignment 2 &mdash; Part III

Nate Babyak &bull; 101310590\
Ozan Kaya &bull; 101322055

## Table of Contents

1. [About](#about)
2. [Structure](#structure)
3. [Getting Started](#getting-started)
    1. [Installation](#installation)
        1. [Clone Repository](#1-clone-repository)
        2. [Set Working Directory](#2-set-working-directory)
    2. [Running Tests](#running-tests)
        1. [Compile Project](#1-compile-project)
        2. [Run Tests](#2-run-tests)

## About

This project simulates how an operating system handles `fork()` and `exec()` calls, managing processes, memory, and interrupts. It produces detailed logs that show how each step of the system runs during different test scenarios.

## Structure

* [`interrupts_101310590_101322055.cpp`](https://github.com/natebabyak/SYSC4001_A2_P3/blob/main/interrupts_101310590_101322055.cpp)
* [`interrupts_101310590_101322055.hpp`](https://github.com/natebabyak/SYSC4001_A2_P3/blob/main/interrupts_101310590_101322055.hpp)
* [`build.sh`](https://github.com/natebabyak/SYSC4001_A2_P3/tree/main/build.sh)
* [`input_files`](https://github.com/natebabyak/SYSC4001_A2_P3/tree/main/input_files)
* [`output_files`](https://github.com/natebabyak/SYSC4001_A2_P3/tree/main/output_files)
* [`report.pdf`](https://github.com/natebabyak/SYSC4001_A2_P3/tree/main/report.pdf)

## Getting Started

### Installation

#### 1. Clone Repository

```sh
git clone https://github.com/natebabyak/SYSC4001_A2_P3.git
```

#### 2. Set Working Directory

```sh
cd SYSC4001_A2_P3
```

### Running Tests

#### 1. Compile Project

```sh
source build.sh
```

#### 2. Run Tests

```sh
if [ -d "output_files" ]; then
    rm -rf output_files/*
else
    mkdir output_files
fi

for i in {1..5}; do
    mv input_files/test_$i/program*.txt ./

    bin/interrupts input_files/test_$i/trace.txt input_files/vector_table.txt input_files/device_table.txt input_files/test_$i/external_files.txt

    mkdir -p output_files/test_$i

    mv execution.txt system_status.txt output_files/test_$i/

    mv program*.txt input_files/test_$i/
done
```

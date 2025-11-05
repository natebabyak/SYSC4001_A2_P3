# SYSC 4001 Assignment 2 Part 3

Nate Babyak &bull; 101310590\
Ozan Kaya &bull; 101322055

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
    rm output_files/*
else
    mkdir output_files
fi

for i in {1..3}; do
    mv input_files/test_$i/program*.txt ./

    bin/interrupts input_files/test_$i/trace.txt input_files/vector_table.txt input_files/device_table.txt input_files/test_$i/external_files.txt

    mkdir output_files/test_$i

    mv execution.txt system_status.txt output_files/test_$i/

    mv program*.txt input_files/test_$i/
done
```

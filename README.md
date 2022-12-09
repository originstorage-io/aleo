# Aleo

## Introduction

GPU Miner for Aleo, 

- Supports connecting to official node.
- Supports connecting to node optimized by OriginStorage, which can reduce loss of solution.
- Supports using address for mining.

Note: The official CUDA is currently used, and the optimized version will come soon.

## Simple tutorial

1. wget https://aleo-originblock.oss-cn-hongkong.aliyuncs.com/aleo-prover-gpu-v1.0.0

2. chmod +x aleo-prover-gpu-v1.0.0

3. start: ./aleo-prover-gpu-v1.0.0 -p aleo1xxxxx -c aleo.originblock.info:4133 -j 10 -g 0,1

     - The -g parameter specifies the graphics card, starting from 0;

     - The -p parameter specifies your own address

     - The -j parameter is the number of parallel tasks, which can be calculated based on CPU core/6


## Usage

Please refer to the usage help 

```
./aleo-prover-gpu -h
Standalone prover.

Usage: aleo-prover-gpu [OPTIONS]

Options:
  -d, --debug
          Enable debug logging
  -p, --prover <PROVER>
          Specify this as a prover, with the given account private key for this node.
  -c, --connect trusted_peers <CONNECT>
          Beacon node address
  -o, --log <LOG>
          Output log to file
      --new-account
          Generate a account
  -g, --gpu <GPU>
          Indexes of GPUs to use (starts from 0)
          Use multiple GPUs
          Example: -g 0,1,2
          Note: Pure CPU proving will be disabled as each GPU job requires one CPU thread as well
  -j, --cuda-jobs <JOBS>
          Parallel jobs per GPU, defaults to 10
          Example: -g 0,1 -j 10
          The above example will result in 8 jobs in total
  -h, --help
          Print help information
```

First:

```shell 
    wget https://aleo-originblock.oss-cn-hongkong.aliyuncs.com/aleo-prover-gpu-v1.0.0
    mv aleo-prover-gpu-v1.0.0 aleo-prover-gpu
    sudo chmod +x aleo-prover-gpu
```

If you didn't have an aleo account, use the following command to create one(Please remember to save the private key and view key):

```shell 
./aleo-prover-gpu --new-account
    Private key: APrivateKey1zkp2EsgCpRzfkzANEyrxfYe4kGfQQrsZFaLmvpFSeEkVnfo
    View key: AViewKey1sjZe8qUKsNjmKtNyjoqwPvHVqnG4KJhZQm3oHprUQ3qt
    Address: aleo1l9vvwxgrfemf50u640rd38qxtqm3lt6jw08den0eycxn2dazgczqnhsup8

WARNING: Make sure you have a backup of both private key and view key!
         Nobody can help you recover those keys if you lose them!
```

Start:
```shell
./aleo-prover-gpu -p aleo1l9vvwxgrfemf50u640rd38qxtqm3lt6jw08den0eycxn2dazgczqnhsup8 -c aleo.originblock.info:4133 -j 10 -g 0
```

- The `-j` parameter can be reasonably specified according to the CPU model

- The `-g` parameter can be specified reasonably according to the number of GPUs

## GPU supports

NVIDIA Turing GPU
NVIDIA Ampere GPU

## Changelog

### 1.0.0
support for aleo testnet3 phase2.   

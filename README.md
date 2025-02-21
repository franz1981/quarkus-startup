# README

## Requirements

A running docker/podman service in the sut

## Overview

This project is designed to run benchmarks on a Quarkus application using different modes, drivers, and configurations. The `run.sh` script orchestrates the execution of these benchmarks by combining various configuration files and scripts.

## Folder Structure

- `benchmarks/`: Contains benchmark configurations. Each subfolder represents a different benchmark.
- `drivers/`: Contains driver scripts that define how the benchmarks are executed.
- `envs/`: Contains environment configurations for local and remote setups.
- `modes/`: Contains mode scripts that define how the Quarkus application is built and run (e.g., JVM, native).
- `profiling.yaml`: Contains scripts for profiling the application during benchmarks.
- `qdup.yaml`: Main configuration file for qDup, defining hosts, roles, and scripts.
- `quarkus.yaml`: Contains scripts for starting and stopping the Quarkus application.
- `util.yaml`: Contains utility scripts and global JavaScript functions.
- `run.sh`: Main script to run the benchmarks.

## How `run.sh` Works

The `run.sh` script takes several arguments to determine the mode, benchmark, driver, and environment setup. It validates these inputs and constructs a qDup command to execute the benchmark.

### Usage

```sh
./run.sh <native|jvm> <benchmark_folder> [driver] [local|remote] [benchmark_params]
```

- `<native|jvm>`: Specifies the mode to run the benchmark (e.g., native or JVM).
- `<benchmark_folder>`: Specifies the benchmark configuration folder.
- `[driver]`: (Optional) Specifies the driver script to use. Defaults to `loop`.
- `[local|remote]`: (Optional) Specifies the environment setup. Defaults to `local`.
- `[benchmark_params]`: (Optional) Additional parameters for the benchmark.

### Example

```sh
./run.sh jvm greeting loop local
```
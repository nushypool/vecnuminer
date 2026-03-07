# Vecno NushyPool Miner
High‑performance GPU miner for the Vecno blockchain, optimized for **NushyPool**.

## Features
- **0% devfee** when mining on NushyPool.
- **Tuned for NushyPool** with streamlined pool defaults.
- **Easy to use** with clear, documented commands.
- **Low CPU overhead** during GPU mining.
- **NVIDIA + AMD GPU support**.
- **mmpOS / HiveOS‑friendly** Linux build available.


## Installation

### From Binaries  
Download the prebuilt binaries for Linux or Windows from this repo’s Releases page and extract them.

#### One‑line install (mmpOS / HiveOS)

Use this for **mmpOS / HiveOS / older glibc systems** (most compatible build):

```sh
mkdir -p vecnuminer && cd vecnuminer
curl -L https://github.com/nushypool/vecnuminer/releases/latest/download/vecnuminer-linux-x86_64-ubuntu20.04.tar.gz | tar -xz
```

This creates a directory named `vecnuminer` and downloads/extracts the files into it.

#### One‑line install (Linux – modern distros)

Use this for **Ubuntu 22.04+ / newer glibc systems**:

```sh
mkdir -p vecnuminer && cd vecnuminer
curl -L https://github.com/nushypool/vecnuminer/releases/latest/download/vecnuminer-linux-x86_64.tar.gz | tar -xz
```

This creates a directory named `vecnuminer` and downloads/extracts the files into it.

#### One‑line install (Windows)

Run in PowerShell:

```powershell
mkdir vecnuminer | Out-Null; Set-Location vecnuminer
Invoke-WebRequest -Uri https://github.com/nushypool/vecnuminer/releases/latest/download/vecnuminer-windows-x86_64.tar.gz -OutFile vecnuminer-windows-x86_64.tar.gz
tar -xzf vecnuminer-windows-x86_64.tar.gz
```

This creates a directory named `vecnuminer` and downloads/extracts the files into it.

### Removing Plugins

To remove a plugin, you simply remove the corresponding `dll`/`so` for the directory of the miner.

* `libvecnocuda.so`, `libvecnocuda.dll`: Cuda support for vecnuminer
* `libvecnoopencl.so`, `libvecnoopencl.dll`: OpenCL support for vecnuminer

# Usage

This build is designed to mine on `nushypool.com` (stratum Solo or PPS). Mining to Vecno node is not supported.

Relevant options:

- `--mining-address <MINING_ADDRESS>`  
- `--stratum-worker <WORKER_NAME>`  
- `--stratum-port <STRATUM_PORT>` (optional, default `50010`)  
- `--pool-region <as|eu|us>` (optional; auto‑select by latency if omitted)  
- `--stratum-password <WORKER_PASSWORD>` (optional)  
- `--cuda-device`, `--cuda-disable`, `--opencl-device`, `--opencl-amd-disable`, etc. (GPU options)  

Note: `--stratum-server` is ignored; the pool is fixed to `nushypool.com`.  
If `--pool-region` is not set, the miner auto‑selects the lowest‑latency region.

# Mining Pool (NushyPool only)

```
./vecnuminer --mining-address <VECNO_ADDRESS> --stratum-worker <WORKER_NAME>
```

Running this will activate all available GPU devices.

Example with a region preference:

```
./vecnuminer --mining-address <VECNO_ADDRESS> --stratum-worker <WORKER_NAME> --pool-region eu
```

## Example HiveOS Configuration

Use these values in the HiveOS custom miner form:

| Field | Value |
| --- | --- |
| Miner name | `vecnuminer` |
| Installation URL | `https://github.com/nushypool/vecnuminer/releases/download/v0.0.4/vecnuminer-r4.tar.gz` |
| Hash algorithm | leave empty |
| Wallet and worker template | `%WAL%` |
| Pool URL | `as.nushypool.com:50010` |
| Pass | leave empty |
| Extra config arguments | `--pool-region as --stratum-port 50010 --stratum-worker hiveosworker` |

<img width="680" height="691" alt="image" src="https://github.com/user-attachments/assets/cdf57250-44a4-4567-aa9a-581647dfc717" />



## Example mmPos Configuration

Todo

## Support

This mining software is experimental, testnet mining is disabled.

Bug reports are welcome. Please open a GitHub issue and include:
- OS and GPU model(s)
- Miner version
- Full command line used
- Relevant log output

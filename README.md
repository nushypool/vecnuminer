# Vecno NushyPool Miner
High-performance CPU/GPU miner for the Vecno Blockchain, written in Rust and optimized for **for mining in NushyPool**.

This miner supports Nvidia and AMD GPU's.
No **devfee**.

## Installation

### From Binaries  
Download the prebuilt binaries for Linux or Windows from this repo’s Releases page and extract them.

#### One‑line install (mmpOS / HiveOS)

Use this for **mmpOS / HiveOS / older glibc systems** (most compatible build):

```sh
mkdir -p vecnuminer && cd vecnuminer
curl -L https://github.com/nushypool/vecnuminer-release/releases/latest/download/vecnuminer-linux-x86_64-ubuntu20.04.tar.gz | tar -xz
```

This creates a directory named `vecnuminer` and downloads/extracts the files into it.

#### One‑line install (Linux – modern distros)

Use this for **Ubuntu 22.04+ / newer glibc systems**:

```sh
mkdir -p vecnuminer && cd vecnuminer
curl -L https://github.com/nushypool/vecnuminer-release/releases/latest/download/vecnuminer-linux-x86_64.tar.gz | tar -xz
```

This creates a directory named `vecnuminer` and downloads/extracts the files into it.

#### One‑line install (Windows)

Run in PowerShell:

```powershell
mkdir vecnuminer | Out-Null; Set-Location vecnuminer
Invoke-WebRequest -Uri https://github.com/nushypool/vecnuminer-release/releases/latest/download/vecnuminer-windows-x86_64.tar.gz -OutFile vecnuminer-windows-x86_64.tar.gz
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
- `--stratum-password <WORKER_PASSWORD>` (optional)  
- `--cuda-device`, `--cuda-disable`, `--opencl-device`, `--opencl-amd-disable`, etc. (GPU options)  

Note: `--stratum-server` is ignored; the pool is fixed to `nushypool.com`.

# Mining Pool (NushyPool only)

```
./vecnuminer --mining-address <MINING_ADDRESS> --stratum-worker <WORKER_NAME> --stratum-port <STRATUM_PORT> --stratum-password <WORKER_PASSWORD>
```

Running this will activate all available GPU devices.

## Support

This mining software is experimental, testnet mining is disabled.

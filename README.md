# vecnuminer

This miner supports Nvidia and AMD GPU's.

This miner is **for mining in NushyPool** and **does not include any devfee**.

## Installation

### From Binaries

This repository **does not include source code**.  
Download the prebuilt binaries for Linux or Windows from this repo’s Releases page and extract them.

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

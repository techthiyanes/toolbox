# pytorch tools

- [torch-checkpoint-shrink.py](./torch-checkpoint-shrink.py) - this script fixes checkpoints which for some reason stored tensors with storage larger than their view at the moment of saving. It clones the current view and re-saves them with just the storage of the current view.

- [multi-gpu-non-interleaved-print.py](./multi-gpu-non-interleaved-print.py) - a `flock`-based wrapper around `print` that prevents messages from getting interleaved when multiple processes print at the same time - which is the case with `torch.distributed` used with multiple-gpus.

- [torch-distributed-gpu-test.py](./torch-distributed-gpu-test.py) - this a `torch.distributed` diagnostics
  script that checks that all GPUs in the cluster (one or many nodes) can talk to each other and allocate gpu memory.

- [emulate-multi-node.md](./emulate-multi-node.md) - instructions on how to emulate a multi-node setup using just a single node - we use the `deepspeed` launcher here.
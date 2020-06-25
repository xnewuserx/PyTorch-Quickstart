# PyTorch-Quickstart

PyTorch Quickstart (GPU). Install PyTorch using Conda and verify the installation.

**1. Create new Conda environment for Pytorch**

```bash
conda create --name pytorch python=3.7

```

Activate it.
```bash
conda activate pytorch
```

**2. Install PyTorch**

```bash
conda install pytorch torchvision -c pytorch
```

**3. Verify your GPU installation**

Start python shell:

```bash
python
```

Copy-paste the following script:

```python
import torch

current_device_id = torch.cuda.current_device()

torch_status = """\tCurrent device index:\t{}
\tCurrent device context-manager: {}
\tNumber of GPUs available:\t{}
\tCurrent device name:\t{}
\tCUDA is currently available:\t{}""".format(
current_device_id,
torch.cuda.device(current_device_id),
torch.cuda.device_count(),
torch.cuda.get_device_name(current_device_id),
torch.cuda.is_available()
)
print(torch_status)

```

Expected output:
```bash
        Current device index:   0
        Current device context-manager: <torch.cuda.device object at 0x7f03a676a990>
        Number of GPUs available:       1
        Current device name:    GeForce RTX 2080 Ti
        CUDA is currently available:    True

```

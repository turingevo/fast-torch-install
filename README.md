# fast-torch-install
Quickly install torch

快速安装torch



torch previous-versions 
https://pytorch.org/get-started/previous-versions/

### 1 download files

### 2 Merge
`cat pkgs_part* > pkgs.tar.gz`

### 3 Multi-thread decompression
`pigz -d -p $(nproc) -c pkgs.tar.gz | tar -xvf -`

then md5 (skip)
```bash
 ls  | parallel 'md5sum {}'
```


### 4 install to your env
for example:

decompression path  is `./pkgs-py3.10-torch2.6.0-cu124`

install cmd:

```
pip install torch==2.6.0 torchvision==0.21.0 torchaudio==2.6.0  --no-index --find-links=./pkgs-py3.10-torch2.6.0-cu124
```

# dotfiles

After the following Preparation, exec
```
$ . /setup.sh
```

## Preparation

### NVIDIA driver & CUDA

```
$ sudo apt update
$ sudo apt upgrade

# ここでnvidia-smiできなくなる可能性があるので、その時はグラフィックドライバの更新が必要 ↓
$ sudo apt purge nvidia-*
$ sudo apt purge cuda-*
$ ubuntu-drivers devices
$ sudo ubuntu-drivers install
```

### Git
```
$ sudo add-apt-repository ppa:git-core/ppa
$ sudo apt update
$ sudo apt install git

```

### Vim & Neovim

```
$ sudo add-apt-repository ppa:jonathonf/vim
$ sudo apt update
$ sudo apt install vim

$ curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim.appimage
$ chmod u+x nvim.appimage
$ ./nvim.appimage --appimage-extract
$ ./squashfs-root/AppRun --version
$ sudo mv squashfs-root /
$ sudo ln -s /squashfs-root/AppRun /usr/bin/nvim
```


### Python 

!!! Before Install Python !!!

https://github.com/pyenv/pyenv/wiki#suggested-build-environment 

↓↓↓
```
$ sudo apt update; sudo apt install build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev curl \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
```

Install Python with asdf

```
$ git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.12.0
$ . “$HOME/.asdf/asdf.sh”
$ asdf install python 3.*.*
```

### Docker install

- https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository
- [Setting up Nvidia Container toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html#setting-up-nvidia-container-toolkit) 

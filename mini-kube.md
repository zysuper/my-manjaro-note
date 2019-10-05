# 搭建 minikube 实验环境

## 安装 kubectl 

```sh
sudo pacman -S kubectl-bin
```

## 设置 kubectl 命令 在 zsh 下的补全

修改 ~/.zshrc

```sh
source <(kubectl completion zsh)
```

## kvm 支持包安装

### 软件安装

```sh
sudo pacman -S libvirt
sudo pacman -S qemu-git
sudo pacman -S ebtables
```

### 开启 AMD-Vi/Intel VT-d (需要处理器支持) 内核支持

#### 编辑 /etc/default/grub

在 GRUB_CMDLINE_LINUX_DEFAULT 最后追加 `intel_iommu=on`

```sh
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
```

#### 重新生成 grub.cfg

```sh
grub-mkconfig -o /boot/grub/grub.cfg
```

最后重启系统

### 检查虚拟机环境

#### 输入命令

```sh
virt-host-validate
```

#### 输出

```
  QEMU: 正在检查 硬件是否支持虚拟化                                 : 通过
  QEMU: 正在检查 if device /dev/kvm exists                                   : 通过
  QEMU: 正在检查 if device /dev/kvm is accessible                            : 通过
  QEMU: 正在检查 if device /dev/vhost-net exists                             : 通过
  QEMU: 正在检查 if device /dev/net/tun exists                               : 通过
  QEMU: 正在检查 for cgroup 'cpu' controller support                         : 通过
  QEMU: 正在检查 for cgroup 'cpuacct' controller support                     : 通过
  QEMU: 正在检查 for cgroup 'cpuset' controller support                      : 通过
  QEMU: 正在检查 for cgroup 'memory' controller support                      : 通过
  QEMU: 正在检查 for cgroup 'devices' controller support                     : 通过
  QEMU: 正在检查 for cgroup 'blkio' controller support                       : 通过
  QEMU: 正在检查 是否支持IOMMU                                           : 通过
  QEMU: 正在检查 内核中是否打开了IOMMU功能                         : 通过
   LXC: 正在检查 Linux内核版本 >= 2.6.26                                 : 通过
   LXC: 正在检查 for namespace ipc                                           : 通过
   LXC: 正在检查 for namespace mnt                                           : 通过
   LXC: 正在检查 for namespace pid                                           : 通过
   LXC: 正在检查 for namespace uts                                           : 通过
   LXC: 正在检查 for namespace net                                           : 通过
   LXC: 正在检查 for namespace user                                          : 通过
   LXC: 正在检查 for cgroup 'cpu' controller support                         : 通过
   LXC: 正在检查 for cgroup 'cpuacct' controller support                     : 通过
   LXC: 正在检查 for cgroup 'cpuset' controller support                      : 通过
   LXC: 正在检查 for cgroup 'memory' controller support                      : 通过
   LXC: 正在检查 for cgroup 'devices' controller support                     : 通过
   LXC: 正在检查 for cgroup 'freezer' controller support                     : 通过
   LXC: 正在检查 for cgroup 'blkio' controller support                       : 通过
   LXC: 正在检查 if device /sys/fs/fuse/connections exists                   : 通过

```

## 安装 docker-machine-driver-kvm2

```sh
sudo pacman -S docker-machine-driver-kvm2
```

## 安装 minikube aliyun

```
yay -S minikube-bin-aliyun
```

## 启动 libvirt 服务

```sh
systemctl start libvirtd.service
systemctl start virtlogd.service
```

你也可以设置成开机启动

```sh
systemctl enable libvirtd.service
systemctl enable virtlogd.service
```

## 设置 minikube 默认驱动

```sh
minikube config set vm-driver kvm2
```

## 启动 minikube

```sh
#使用之前设定的默认驱动，也可使用 --vm-driver=kvm2 手动指明驱动
minikube start 
```

输出

```
➜  ~ minikube start
😄  minikube v1.2.0 on linux (amd64)
✅  using image repository registry.cn-hangzhou.aliyuncs.com/google_containers
🔥  Creating kvm2 VM (CPUs=2, Memory=2048MB, Disk=20000MB) ...
🐳  Configuring environment for Kubernetes v1.15.0 on Docker 18.09.6
🚜  Pulling images ...
🚀  Launching Kubernetes ... 
⌛  Verifying: apiserver proxy etcd scheduler controller dns
🏄  Done! kubectl is now configured to use "minikube"
```

## 获取 pod 列表

```sh
kubectl get po -A
```

## 调整 minikube 内存

```sh
minikube config set memory 4096
```

## 参考链接
[minikube document](https://minikube.sigs.k8s.io/docs/start/linux/)
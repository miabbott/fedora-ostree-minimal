# fedora-ostree-minimal
Holding space for minimal ostree-based OS experiments

## Status

2023-June-2

Currently building with `coreos-assembler build`

Producing a QEMU disk image

Can boot to the point where things fall down mounting real root

`$ qemu-system-x86_64 -snapshot -machine accel=kvm -cpu host -m 4096 -drive file=fedora-minimal-38.20230602.dev.1-qemu.x86_64.qcow2,format=qcow2,index=0,media=disk,if=virtio -net nic,model=virtio -net user,hostfwd=tcp::2223-:22 -nographic`

```
[    1.090983] ostree-prepare-root[202]: ostree-prepare-root: Couldn't find specified OSTree root '/sysroot//ostree/boot.1/fedora-minimal/c5c93a23e7c90e27beb61d77c554718aeb902d12c78e5bc82358d1e108d02409/0': No such file or directory
[FAILED] Failed to start ostree-pre….service - OSTree Prepare OS/.
See 'systemctl status ostree-prepare-root.service' for details.
```

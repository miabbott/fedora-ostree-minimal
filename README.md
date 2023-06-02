# fedora-ostree-minimal
Holding space for minimal ostree-based OS experiments

## Status

2023-June-2

Currently building with `coreos-assembler build`

Producing a QEMU disk image

Can boot to the point where things fall down mounting real root in initrd

`$ qemu-system-x86_64 -snapshot -machine accel=kvm -cpu host -m 4096 -drive file=fedora-minimal-38.20230602.dev.1-qemu.x86_64.qcow2,format=qcow2,index=0,media=disk,if=virtio -net nic,model=virtio -net user,hostfwd=tcp::2223-:22`

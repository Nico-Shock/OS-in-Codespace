## COMMANDS:

```
sudo apt update -y && sudo apt upgrade -y
```

```
sudo apt install -y qemu qemu-kvm wget
```

```
wget -O arch.iso "https://de.mirrors.cicku.me/archlinux/iso/2024.11.01/archlinux-2024.11.01-x86_64.iso"
```

```
wget -O bios64.bin "https://github.com/BlankOn/ovmf-blobs/raw/master/bios64.bin"
```

```
wget -O ngrok.tgz "https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz"
```

```
tar -xf ngrok.tgz
```

```
./ngrok authtoken <insert authtoken here>
```

```
qemu-img create -f qcow2 arch.img 50G
```

```
./ngrok tcp 5900
```

```
sudo qemu-system-x86_64 -m 4096 -smp 4 -cpu host -boot order=c -drive file=arch.iso,media=cdrom -drive file=arch.qcow2,format=qcow2 -device usb-ehci,id=usb,bus=pci.0,addr=0x4 -device usb-tablet -vnc :0 -smp cores=4 -device e1000,netdev=n0 -netdev user,id=n0 -vga qxl -accel kvm -bios bios64.bin
```

## Websites:

```
ngrok.com
```

```
github.com/codespaces/new
```

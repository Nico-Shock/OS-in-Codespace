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
qemu-img create -f raw arch.img 50G
```

```
./ngrok tcp 5900
```

```
sudo qemu-system-x86_64 -m 4096 -smp 4 -cpu host -boot menu=on -drive file=arch.iso,media=cdrom -drive file=arch.img,format=raw -device usb-ehci,id=usb,bus=pci.0,addr=0x4 -device usb-tablet -vnc :0 -smp cores=4 -device e1000,netdev=n0 -netdev user,id=n0 -vga qxl -accel kvm -bios bios64.bin
```

## Websites:

```
ngrok.com
```

```
github.com/codespaces/new
```


## Download Links (these are examples not all work)

macos14:
https://download2390.mediafire.com/uef58f1lq0xgPRMjnfb9NWh6lgypL0qQ-892k__iWpMI5PInHTmr_Bj5ugJguiplxC-a8v7Laj3eF6ktiQ3ng40ruuq7sQM6I7kRsUZadkGl-qaQ_E1DJzkZlkeec7V-gYQNWSuebRlbjL7xXvWaJ-F5H6P7hTfLD5iT_ITPPA/vku90kjifs1fmu0/macOS+Sonoma+ISO+by+techrechard.com.iso

Linux Mint:
https://mirror.dogado.de/linuxmint-cd/stable/21.3/linuxmint-21.3-mate-64bit.iso

arch linux:
https://www.archlinux.de/download/iso/2024.01.01/archlinux-2024.01.01-x86_64.iso

Windows 7:
https://dl2-new.winfuture.de/Xy-HlDxn_Qn0xhdUcRL1lg/1706146797/3291/ssd/Betriebssysteme/windows7/de_windows_7_professional_with_sp1_x64_dvd_u_676919.iso

Windows XP:
https://dl2-new.winfuture.de/8QLEgK2XO4FhJVgosBcxEQ/1707103228/1179/software/WindowsXPx64/Windows_XP_Professional_64-bit_dvd.iso

Proxmox:
https://enterprise.proxmox.com/iso/proxmox-ve_8.2-1.iso

Kali Linux:
https://cdimage.kali.org/kali-2024.1/kali-linux-2024.1-installer-amd64.iso

I'm trying to install nixos.

The drive is [WD Blue SN550 1TB NVMe](https://www.amazon.com/gp/product/B07YFFX5MD/).

It is partitioned with GPT:

```

Disk /dev/sde: 1953525168 sectors, 931.5 GiB
Model:
Sector size (logical/physical): 512/4096 bytes
Disk identifier (GUID): 042509B4-723B-4FC0-B9E2-75CCF399ED63
Partition table holds up to 128 entries
Main partition table begins at sector 2 and ends at sector 33
First usable sector is 34, last usable sector is 1953525134
Partitions will be aligned on 2048-sector boundaries
Total free space is 2014 sectors (1007.0 KiB)

Number  Start (sector)    End (sector)  Size       Code  Name
   1            2048         1026047   500.0 MiB   EF00  EFI system partition
   2         1026048      1953525134   931.0 GiB   8300  Linux filesystem
```

with this hierarchy:

```
sde      8:64   0 931.5G  0 disk
├─sde1   8:65   0   500M  0 part /mnt/gamma/boot
└─sde2   8:66   0   931G  0 part /mnt/gamma
```


Issuing
```
nixos-install --root /mnt/gamma
```

yields

```
error: while setting up the build environment: unable to bind mount '/mnt/gamma/nix/store/9yg221lkyb3q0214gcz6i3fg9izfc2jk-append-initrd-secrets.drv.chroot': Permission denied
```

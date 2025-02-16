# Random notes

## Encrypt home directory

```bash
pkill -u omakoto
ecryptfs-migrate-home -u omakoto
```

## Encrypt swap

```bash
# Add it to /etc/crypttab. Change the partition name to the real one.
echo 'cryptswap /dev/nvme0n1p5 /dev/urandom cipher=aes-xts-plain64,size=256,swap,discard' | sudo tee -a /etc/crypttab

# Add it to /etc/fstab.
echo '/dev/mapper/cryptswap none swap sw 0 0' | sudo tee -a /etc/fstqab

```

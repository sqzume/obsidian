[Arch Wiki](https://wiki.archlinux.jp/index.php/%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%AC%E3%82%A4%E3%83%89)
### パーティション
```bash
gdisk /dev/<デバイス名>
```
### フォーマット
```bash
mkfs.vfat -F32 /dev/<EFIシステムパーティション>
mkfs.ext4 /dev/<Arch Linuxパーティション> -L arch_os
```
### パッケージのインストール
```bash
pacstrap -K /mnt base base-devel linux linux-firmware amd-ucode git neovim sudo
```
### ブートローダー（未完成）
```bash
bootctl install
```
#### ローダーを追加
```bash
touch /boot/loader/entries/arch.conf
nvim /boot/loader/entries/arch.conf
```

次のように設定
```arch.conf
title   Arch Linux
linux   /vmlinuz-linux
initrd  /amd-ucode.img
initrd  /initramfs-linux.img
options root="LABEL=arch_os" rw
```
#### ローダー設定
```bash
nvim /boot/loader/loader.conf

// 以下のようにする
default arch.conf
timeout 4
```
### シャットダウン
```bash
shutdown 0
```
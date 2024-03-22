[Arch Wiki](https://wiki.archlinux.jp/index.php/%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%AC%E3%82%A4%E3%83%89)
### パーティション
```bash
gdisk /dev/<デバイス名>
```
###
### パッケージのインストール
```bash
pacstrap -i /mnt base linux linux-firmware amd-ucode git neovim sudo
```
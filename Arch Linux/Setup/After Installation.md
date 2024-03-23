### ユーザー設定
```bash
useradd -m -G wheel sqzume
passwd sqzume
EDITOR=neovim visudo
```

アンコメント
```
#%wheel ALL=(ALL) ALL
```

ログイン
```bash
su sqzume
```
### CLI環境のセットアップ
```bash
sudo pacman -S zsh
chsh /usr/bin/zsh
```
#### yayのインストール
```zsh
git clone https://aur.archlinux.org/yay-bin.git yay-bin
cd yay-bin
makepkg -si --noconfirm
cd ..
rm -rf yay-bin
```
### GUI環境のセットアップ
```zsh
sudo pacman -S nvidia-dkms linux-headers
```

`/boot/loader/entries/arch.conf`の末尾に追加
```
nvidia_drm.modeset=1
```

`/etc/mkinitcpio.conf`の`MODULES`に追加
```
nvidia nvidia_modeset nvidia_uvm nvidia_drm
```

`/etc/modprobe.d/nvidia.conf`(存在しない場合は作成)に追加
```
options nvidia-drm modeset=1
```

```zsh
sudo pacman -S qt5-wayland qt5ct libva
```
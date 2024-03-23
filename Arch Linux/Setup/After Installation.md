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

```
### GUI環境のセットアップ
```zsh
sudo pacman -S nvidia-dkms
```
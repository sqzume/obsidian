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
zsh
chsh /usr/bin/zsh
```
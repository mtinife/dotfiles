archinstall
firefox or browser
alacritty
i3 i3lock i3status/i3block
xorg, xorg-xinit
base-devel git
create xinit file and exec i3
autostart xinit at login
install zsh, oh-my-zsh change shell

instal yay
git clone https://aur.archlinux.org/yay.git
makepkg -si
yay --version

enable touchpad gestures for laptops
sudo vim /etc/X11/xorg.conf.d/30-touchpad.conf
##
Section "InputClass"
    Identifier "touchpad"
    Driver "libinput"
    MatchIsTouchpad "on"
    Option "Tapping" "on"
    Option "TappingButtonMap" "lmr"
EndSection
##

install jetbrainsmonoa font
https://github.com/ryanoasis/nerd-fonts/releases/download/v3.1.1/JetBrainsMono.zip
sudo pacman -S unzip
unzip JetBrainsMono.zip -d JetBrainsMono
mkdir ~/.local/share/fonts
cp -rf ~/Downloads/JetBrainsMono/*.ttf ~/.local/share/fonts

install powerlevel10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
exec zsh
Set ZSH_THEME="powerlevel10k/powerlevel10k" in ~/.zshrc
p10k configure

install autosuggestions, syntax-hightlighting
install autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
install Syntax hightlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)

i3 Hide titlebar
for_window [class="^.*"] border pixel 1
new_window 1pixel

configure i3 gaps keybinds and status bar hide and show
install pywal and picon
locate a background
configure picon transparence
configure alacritty 
include pywal to xinit
edit i3lock with background

udiskie
sudo pacman -S udiskie
udiskie &

ssh with github
sudo pacman -S openssh
ssh-keygen -t ed25519 -C "your_email@example.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
add to github

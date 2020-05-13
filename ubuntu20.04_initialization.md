# update system

    apt-get update

# install software

## vscode

    curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo apt-key add -
    sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
    sudo apt-get update
    sudo apt-get install code # or code-insiders

## chrome

    wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
    sudo sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google-chrome.list'
    sudo apt-get update
    sudo apt-get install google-chrome-stable

# terminal configuration

## oh-my-zsh

    sh -c "\$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
    sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="ys"/g' ~/.zshrc # 主题
    tee -a ~/.zshrc <<EOF
    [ -f /usr/share/autojump/autojump.sh ] && source /usr/share/autojump/autojump.sh
    [ -f /usr/share/zsh-autosuggestions/zsh-autosuggestions.zsh ] && source /usr/share/zsh-autosuggestions/zsh-autosuggestions.zsh
    [ -f /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh ] && source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
    EOF

# other

## bugfix chinese font rendering

    sudo vim /etc/fonts/conf.avail/64-language-selector-prefer.conf

## use simplified chinese

    <?xml version="1.0"?>
    <!DOCTYPE fontconfig SYSTEM "fonts.dtd">
    <fontconfig>
    <alias>
        <family>sans-serif</family>
        <prefer>
        <family>Noto Sans CJK SC</family>
        <family>Noto Sans CJK TC</family>
        <family>Noto Sans CJK HK</family>
        <family>Noto Sans CJK JP</family>
        <family>Noto Sans CJK KR</family>
        </prefer>
    </alias>
    <alias>
        <family>serif</family>
        <prefer>
        <family>Noto Serif CJK SC</family>
        <family>Noto Serif CJK TC</family>
        <family>Noto Serif CJK JP</family>
        <family>Noto Serif CJK KR</family>
        </prefer>
    </alias>
    <alias>
        <family>monospace</family>
        <prefer>
        <family>Noto Sans Mono CJK SC</family>
        <family>Noto Sans Mono CJK TC</family>
        <family>Noto Sans Mono CJK HK</family>
        <family>Noto Sans Mono CJK JP</family>
        <family>Noto Sans Mono CJK KR</family>
        </prefer>
    </alias>
    </fontconfig>

# setting link

<https://juejin.im/post/5d773da76fb9a06aff5e9a99>  
<https://github.com/lijinglin2019/blog/issues/5>  
<https://juejin.im/post/5eb3a1556fb9a0434b73545c>

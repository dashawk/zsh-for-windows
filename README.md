### Installing Zsh in Git Bash

1. Download the latest MSYS2 zsh package from the [MSYS2 package repository](https://packages.msys2.org/package/zsh?repo=msys&variant=x86_64). You can also download from this repository.

2. Install an extractor that can open ZST like [PeaZip](https://peazip.github.io/).

3. Extract the file (contains etc and usr folders) into your Git Bash installation directory, commonly under `C:\Program Files\Git`. Extract the files from there. There should be no duplicate files to be overridden

4. Open Git Bash and run:
    ```bash
    zsh
    ```

5. Configure your zsh by using the wizard. If it does not appear, then run this, otherwize you can skip this step.
    ````bash
    autoload -U zsh-newuser-install
    zsh-newuser-install -f
    ```
    - Configure history by pressing `1`, choose your settings by pressing `1-3` and to complete your choices, press `0`
    - Configure completion by pressing `2`, choose `1` and then press `0`
    - Finally, press `0` to save your changes
6. Configure zsh as the default shell by adding this to your `.bashrc` file
    ```sh
    if [ -t 1 ]; then
        exec zsh
    fi
    ```

### Installing oh-my-zsh

Now, you should be able to install `oh-my-zsh`. Run this in your zsh shell.
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Installing Powerlevel10k Theme

1. Install the [powerlevel10k](https://github.com/romkatv/powerlevel10k) theme.
    ```bash
    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
    ```
2. Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`. It will automatically check for the latest themes in github.

### Installing Plugins

To install plugins and themes, use the `oh-my-zsh` installation methods:
- [zsh-completions](https://github.com/zsh-users/zsh-completions)
- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
- [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
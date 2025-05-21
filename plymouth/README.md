# Araragi for [Plymouth](https://gitlab.freedesktop.org/plymouth/plymouth)

> An Araragi theme for Plymouth.

Based on https://github.com/PROxZIMA/proxzima-plymouth

![Muraragi](./assets/muraragi.gif)

## Installation

### Manually

#### Dependencies

- plymouth

> **Note**
>
> `plymouth-x11` is required to preview the theme without rebooting.

1. Clone this repo or download the .zip

```bash
$ git clone https://github.com/sin3point14/muraragi-plymouth.git
$ cd muraragi-plymouth
```

2. Copy the whole `muraragi` directory to plymouth themes

```bash
$ sudo cp -r muraragi /usr/share/plymouth/themes
```

3. Follow the steps based on your distribution

    - Arch based distros
    ```
    # check if theme exist in dir
    sudo plymouth-set-default-theme -l

    # optionally you can test the theme by running the script given in repo (plymouth-x11 required)
    sudo ./preview.sh 13

    # now set the theme (muraragi, in this case) and rebuilt the initrd
    sudo plymouth-set-default-theme -R muraragi
    ```

    - Debian(Ubuntu, Kubuntu) based distros
    ```
    # install the new theme (muraragi, in this case)
    sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/muraragi/muraragi.plymouth 100

    # select the theme number and press enter to apply
    sudo update-alternatives --config default.plymouth

    # update initramfs
    sudo update-initramfs -u
    ```

4. Reboot and voila

## Potential problems and solutions

Never had one but still refer to the following articles.

- https://wiki.archlinux.org/title/plymouth
- https://wiki.ubuntu.com/Plymouth

For scripting: https://www.freedesktop.org/wiki/Software/Plymouth/Scripts/

## Credits

- [showplymouth.sh](https://github.com/adi1090x/plymouth-themes): Made by [@adi1090x](https://github.com/adi1090x).
- [PROxZIMA](https://github.com/PROxZIMA): Whose [repo](https://github.com/PROxZIMA/proxzima-plymouth) served as the template

## License

[GPLv3 License](LICENSE).

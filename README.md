Flatpak package for Legion RGB Control

## Usage

**Note**: In order for this flatpak to work, you have to add the following `udev` rule (in a path similar to `/etc/udev/rules.d/99-kblight.rules`):

### Format

```sh
SUBSYSTEM=="usb", ATTR{idVendor}=="048d", ATTR{idProduct}=="####", MODE="0666"
```

Where `idProduct` can be found in these tables:

| Year | Pro    | Regular + Slim | LOQ    |
| ---- | ------ | -------------- | ------ |
| 2024 | `c995` | `c994`         | `c993` |
| 2023 | `c985` | `c984`         | `c983` |

| Year | Pro + Regular + Slim | Ideapad |
| ---- | -------------------- | ------- |
| 2022 | `c975`               | `c973`  |
| 2021 | `c965`               | `c963`  |
| 2020 | `c955`               |         |

And then reloading the rules:

```sh
sudo udevadm control --reload-rules && sudo udevadm trigger
```
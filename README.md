[Upstream repository](https://github.com/pwr-Solaar/Solaar)

# Installation

## udev rule

The udev rule needs to be copied manually as root from the [Solaar repository](https://github.com/pwr-Solaar/Solaar) to `/etc/udev/rules.d`:

- For Wayland: [rules.d-uinput/42-logitech-unify-permissions.rules](https://github.com/pwr-Solaar/Solaar/blob/master/rules.d-uinput/42-logitech-unify-permissions.rules)
- For Xorg (X11): [rules.d/42-logitech-unify-permissions.rules](https://github.com/pwr-Solaar/Solaar/blob/master/rules.d/42-logitech-unify-permissions.rules) 

Afterwards run `sudo udevadm control --reload-rules` or reboot the system.

# Build

## Update dependencies

Look here for the required dependencies: https://github.com/pwr-Solaar/Solaar/blob/master/setup.py#L71

Example:

```bash
flatpak-pip-generator.py --runtime='org.gnome.Sdk//48' "evdev>=1.1.2" "pyudev>=0.13" "PyYAML>=3.12" "python-xlib>=0.27" "psutil>=5.4.3" PyGObject typing_extensions --output python3-modules
```

```bash
flatpak run org.flathub.flatpak-external-data-checker ./io.github.pwr_solaar.solaar.yaml
```

To start building:

```bash
flatpak run org.flatpak.Builder --install --force-clean build --user io.github.pwr_solaar.solaar.yaml
```

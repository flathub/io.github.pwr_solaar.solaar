[Upstream](https://github.com/pwr-Solaar/Solaar)

# How to bump dependencies

Look here for the required dependencies: https://github.com/pwr-Solaar/Solaar/blob/master/setup.py#L71

Example:
```
flatpak-pip-generator.py --runtime='org.gnome.Sdk//48' "evdev>=1.1.2" "pyudev>=0.13" "PyYAML>=3.12" "python-xlib>=0.27" "psutil>=5.4.3" PyGObject typing_extensions --output python3-modules
```


```
flatpak run org.flathub.flatpak-external-data-checker ./io.github.pwr_solaar.solaar.yaml
```

# Building

`flatpak run org.flatpak.Builder --install --force-clean build --user io.github.pwr_solaar.solaar.yaml`

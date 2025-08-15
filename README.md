## Desktop Entry to toggle squeekboard. To make it disappear until i need it
[Desktop Entry]
Version=1.0
Type=Application
Name=Toggle and Run Squeekboard
Comment=Enable, disable, or run the on-screen keyboard Squeekboard
Exec=bash -c 'if gsettings get org.gnome.desktop.a11y.applications screen-keyboard-enabled | grep -q true; then gsettings set org.gnome.desktop.a11y.applications screen-keyboard-enabled false; pkill squeekboard; else gsettings set org.gnome.desktop.a11y.applications screen-keyboard-enabled true; squeekboard & fi'
Icon=preferences-desktop-accessibility
Terminal=false
Categories=Accessibility;

## Desktop Entry to swith between mouse emulation and multitouch on touch screen
[Desktop Entry]
Version=1.0
Type=Application
Name=Toggle Multitouch/Mouse Emulation
Comment=Enable or disable multitouch or mouse emulation
Exec=bash -c 'if grep mouseEmulation="no" ~/.config/labwc/rc.xml > /dev/null; then sed -i.bak "s/mouseEmulation=\"no\"/mouseEmulation=\"yes\"/" ~/.config/labwc/rc.xml; else sed -i.bak "s/mouseEmulation=\"yes\"/mouseEmulation=\"no\"/" ~/.config/labwc/rc.xml; fi'
Icon=preferences-desktop-accessibility
Terminal=false
Categories=Accessibility;

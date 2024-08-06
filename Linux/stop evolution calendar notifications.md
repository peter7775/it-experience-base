```
cp /etc/xdg/autostart/org.gnome.Evolution-alarm-notify.desktop ~/.config/autostart/
echo "Hidden=true" >> ~/.config/autostart/org.gnome.Evolution-alarm-notify.desktop
``` 
or

`systemctl --user mask evolution-calendar-factory.service`
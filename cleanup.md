# Clean up
``` console
sudo dnf clean all
sudo dnf autoremove
sudo journalctl --vacuum-size=200M
sudo journalctl --vacuum-time=5d
sudo rm -rf ~/.local/share/Trash/*
sudo rm -rf /var/tmp/*
sudo find ~/.cache -type f -atime +30 -delete
``` 

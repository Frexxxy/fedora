# Software
## Update
### Packet manager
```console
sudo dnf upgrade --refresh
sudo dnf distro-sync
sudo dnf autoremove
sudo dnf clean all
```

### Flatpak
```console
sudo flatpak update
sudo flatpak uninstall --unused
```

### Firmware
``` console
sudo fwupdmgr refresh --force
sudo fwupdmgr get-devices
sudo fwupdmgr get-updates
sudo fwupdmgr update
```

## Uninstall Software
``` console
dnf remove packagename
```

## History
### All updated packages
``` console
rpm -qa --qf '%{INSTALLTIME} (%{INSTALLTIME:date}): %{NAME}-%{VERSION}-%{RELEASE}.%{ARCH}\n' | sort -n
``` 

``` console
rpm -qa --queryformat "%{INSTALLTIME};%{INSTALLTIME:day}; \
%{BUILDTIME:day}; %{NAME};%{VERSION}-%-7{RELEASE};%{arch}; \
%{VENDOR};%{PACKAGER};%{DISTRIBUTION};%{DISTTAG}
" \
| sort | cut --fields="2-" --delimiter=\; \
| tee rpmlist.csv | less -S
``` 

[unit] # keep description and other dependencies here
[service] #keep required things here
[Install] # keep user targets here

systemctl start 
systemctl stop 
systemctl enable
systemctl reload
systemctl list-units --all #lists all services


# used to check logs of a service
journalctl 
journalctl -u docker.service

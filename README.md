# jetson_stats_zeromq

### Pre-requisite

```
$ sudo -H pip install -U jetson-stats
$ sudo reboot
```

### Dependencies

```
$ pip3 install --upgrade pip
$ pip3 install packaging
$ pip3 install zmq
```

### Run

on jetson,

```
$ ./jpub
```

on hostpc after set IP address in jsub


```
$ ./jsub
```

### Autostart

sudo cp jpub /usr/local/bin/
sudo chmod +x /usr/local/bin/jpub 

sudo vim /etc/systemd/system/jetson_stats_pub.service
sudo systemctl enable jetson_stats_pub.service
sudo systemctl start jetson_stats_pub.service

```
[Unit]
Description=jetson_stats_pub service
After=jetson_stats.service

[Service]
ExecStart=/usr/local/bin/jpub
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

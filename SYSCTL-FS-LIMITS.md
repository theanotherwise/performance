```bash
# Total
sysctl fs.file-max
# Per process
sysctl fs.nr_open
sysctl fs.aio-max-nr
sysctl fs.inotify.max_user_instances
sysctl fs.inotify.max_user_watches
```

```bash
sysctl -w fs.file-max=1048576
sysctl -w fs.nr_open=1048576
sysctl -w fs.aio-max-nr=65536
sysctl -w fs.inotify.max_user_instances=8192
sysctl -w fs.inotify.max_user_watches=1048576
```

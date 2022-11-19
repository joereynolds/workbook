
## Show all logs

```
journalctl
```

## Show logs for a unit

(using sys-module-fuse.device as our example unit )

```
journalctl -u sys-module-fuse.device
```

(Get units with `systemctl list-units`)

## Show logs matching a pattern

(Takes a regular expression but we're using a string for simplicity)
```
journalctl --grep=docker
```

## Show logs from a time

```
journalctl --since today
```

For a specific unit 

```
journalctl --since today -u mullvad-daemon
```

## Follow the logs

```
journalctl --follow
```

# Exercises




## List all units

```
systemctl
```

## List all units explicitly

```
systemctl list-units
```

## Get the status of a unit

(using `sys-module-fuse.device` as our example unit )

```
systemctl status sys-module-fuse.device
```

## Show the units properties (useful for debugging)

```
systemctl show sys-module-fuse.device
```

## Show all timers

```
systemctl list-timers
```

## Run a timer

Just like a service, a timer can be ran with `start`

```
systemctl start logrotate.timer
```

## Run a transient (one-off) timer

The below will run `ls` and put the stdout into the journal.

```
systemd-run --on-calendar "*:0/1" systemd-cat ls
```

`systemd-run` runs a specified command.

`systemd-cat` pipes stdout/stderr from a command into thejournal

`--on-calendar "*:0/1"` - Will run a command every minute

Once ran, you can see your anonymous timer just as any other with `systemctl list-timers`.

## Stop a timer

Just like a service, a timer can be removed with `stop`.

Using our transient timer from above:

```
systemctl stop run-u62.timer
```

Confirm its removal with `systemctl list-timers`

# Exercises



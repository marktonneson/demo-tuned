## Demo WalkThru

### Requirements
* Optional: VM running RHEL 6 or 7 (7.latest preferred)
* This demo does not ask you to apply any changes so any RHEL instance should suffice

### Walk Thru
To view the available installed profiles:
```
# tuned-adm list
```

To view the currently activated profile (also in list cmd):
```
# tuned-adm active
```

To select or activate a profile:
```
# tuned-adm profile <profile_name>
```

To let tuned recommend you the best suitable profile for your system without changing any existing profiles:
```
# tuned-adm recommend
```

To disable all tuning:
```
# tuned-adm off
```

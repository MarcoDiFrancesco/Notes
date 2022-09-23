# Battery

Type: System

## Low battery allert

Script placed under and set using crontab `check_low_battery` (https://unix.stackexchange.com/a/190155/337926)

User crontab:

```
* * * * * /home/marco/scripts/check-low-battery
```

## ACPI (Archive)

A way to get battery level is using ACPI. This program to get battery level.
From https://wiki.archlinux.org/index.php/ACPI_modules#Getting_information
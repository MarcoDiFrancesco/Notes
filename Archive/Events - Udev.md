Config: */etc/udev/rules.d*

*udev* is a program to manage events like monitor or mouse plug-in. It runs short script (as root) when an event occures, if the previous script did not finish does not run the following one. Because of this, it was not possible to run polybar on monitor plug-in, if polybar scripts were run in background it was closing the bars after few moments that the script finished (~1 second).

`udev monitor` contains:
- KERNEL: the real event
- UDEV: event udev sends out

`udevadm info -a /dev/usb/hiddev0`

*at* in udev rules, requires atd service enabled

#### Archive: Udev things that didn't work out
Because of this the program *at* was installed, it runs the program as a new user, it is set in udev command ([link](https://askubuntu.com/a/1017407/877408)).

*disown* ([link](https://askubuntu.com/a/668004/877408)) in the script was tested but didn't work
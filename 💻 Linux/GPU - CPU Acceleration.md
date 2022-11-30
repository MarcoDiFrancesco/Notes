VAAPI and VDPAU are set in `/etc/environment`
Currently using Optimus with VirtualGL and Primus technologies

## Nvidia on startup
Unable to setup nvidia without optirun.

## Hardware acceleration
- *intel-media-driver* used for VA-API set as iHD, Nvidia (vdpau) does not have support for Chrome nor Firefox [link](https://wiki.archlinux.org/title/Hardware_video_acceleration#Application_support)
- *nvidia-utils*, dependency of *nvidia*, used for VDPAU, Intel (va-gl) has too little support.
Support:
	- VAAPI used for Chromium
	- VDPAU for VLC (to setup)

## Optimus
**Optimus** technology allows the integrated GPU to manage the display while the dedicated GPU manages the most demanding rendering and ships the work to the integrated GPU to be displayed. When the laptop is running on battery supply, the dedicated GPU is turned off to save power and prolong the battery life

*bumblebee* is a software implementation comprising two parts:

- Render programs off-screen on the dedicated video card and display it on the screen using the integrated video card. This bridge is provided by **VirtualGL** or **Primus** and connects to a X server started for the discrete video card
- Disable the dedicated video card when it is not in use. This is done throgh *bbswitch* package, without any configuration needed, Bumblebee will detect it automatically

## VirtualGL
**VirtualGL** technology requires:
- *bumblebee* package: the main package providing the daemon and client programs
- *mesa* package (dependency of *bumblebee*) an open-source implementation of the OpenGL specification

Commands: `optirun COMMAND`

## Primus
**Primus** technology is becoming the default choice, because it consumes less power and sometimes provides better performance than optirun/virtualgl. It may be run separately, but it does not accept options as optirun does. Setting primus as the bridge for optirun provides more flexibility.

Requires:
- *primus* package (that requires *bumblebee*).

Commands:
- `optirun -b primus COMMAND` to set primus as bridge method
- `primusrun COMMAND` to run reparately (requires a process running in GPU to detect it)

#### Archive Test package
*glxgears* is the package used for testing, when running with Primus the frame are locked to 60 fps, to avoid this limitation use: `vblank_mode=0 primusrun glxgears`.

#### Archive CPU Change frequency

*community/cpupower* was used to change frequency

`cpupower frequency-info` settings saved in `/etc/default/cpupower`

`sudo cpupower frequency-set -g powersave`

`sudo cpupower frequency-set -g performance`

Get the used governator (e.g. powersave or performance)

`cat /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor`

#### Archive PRIME
**PRIME** technology is used to manage hybrid graphics found on recent desktops and laptops. PRIME GPU offloading and Reverse PRIME are an attempt to support muxless hybrid graphics in the Linux kernel.

- PRIME GPU offloading: GPU-intensive applications should be rendered on the more powerful discrete card.
- Reverse PRIME: If the second GPU has outputs that are not accessible by the primary GPU, you can use Reverse PRIME to make use of them. This will involve using the primary GPU to render the images, and then pass them off to the secondary GPU.

An implementation of PRIME GPU offloading is in *nvidia-prime* package.

Command: `prime-run COMMAND`
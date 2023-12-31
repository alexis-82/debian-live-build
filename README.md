# Debian Live-Build  
Installation:
```
# apt install live-build
# apt install squashfs-tools live-boot live-config live-boot-initramfs-tools live-config-sysvinit xorriso isolinux
```

Instruction:
```
$ mkdir live
$ cd live
$ lb clean
```

Auto generated folders:
* auto
* config
* locate

```
$ cd auto
```

Create a file config or copy the file config from Git.

### Next step

```
$ cd auto
$ chmod 700 config (**fix)
$ cd ..
$ lb config
$ lb build
```
** Typical error
W: The auto-config script exists but is not executable, ignoring.
P: Updating config tree for a debian-bullseye-amd64 system



⚠ Every time fixed a error
```
$ lb clean
$ lb build
```

<br>
<br>
 
## Desktop Environment
#### Interactive shell :
```
(live):# tasksel --list-tasks
(live):# tasksel install xfce-desktop
```

<span style="color:red">Wait the (live) shell</span>

```
(live):# exit
```


⭕ Used installation software Calamares

<br>
<br>

### Structure of the folders
```
├── auto                        #main live-build configuration
├── config
│   ├── archives                #package mirrors/repositories
│   ├── hooks                   #extra scripts to run during build stages
│   ├── includes.binary         #files to include on the ISO filesystem
│   ├── includes.chroot         #files to include in the live system's filesystem
│   ├── includes.installer      #files to include in the installer's filesystem
│   ├── package-lists
│   │   └── *.list.chroot	#packages to install on the live system
│   │   └── *.list.binary	#packages to place in the APT repository on the ISO image
│   ├── packages.chroot         #standalone .deb packages to install on the live system
│   └── task-lists              #tasksel tasks to install on the live system
├── doc			        #user documentation
├── Makefile	                #main automation, dependencies management, ...
└── scripts		        #extra automation scripts
```

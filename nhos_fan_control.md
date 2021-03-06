# NiceHash OS local access
This guide provides information on how to configure custom GPU fan control table.

## What you will need
Here is the list of preconditions that must be met before you can proceed
* Computer with one of the following operating system: **Windows**, **MacOs** or **Linux**.
* **NiceHash OS flash drive**.
* **Text editor** you are familiar with.<br/>

## NiceHash OS configuration
NiceHash OS flash drive is divided into two partitions, **`SYSTEM`** and **`NHOS`**, where `NHOS` partition contains the configuration data for system to operate correctly.

When NiceHash OS flash drive is inserted into your computer, the system should **automatically detect `NHOS`** partition and **show it in system file manager** (Windows Explorer, macOS Finder, Linux Nautilus, etc.) as disk on Windows or as a mounted device on macOS and Linux. Using your file manager, navigate to the **location of the `NHOS` disk or mount point**. There you will find a **single configuration file** named **`configuration.txt`**.

To modify NiceHash OS configuration, open this configuration file with your preferred file editor where you will see the following file content structure
```json
{
    "rig": {
        "btc": "",
        "worker": "",
        "group": ""
    },
    "access": {
        "ssh": {
            "key": ""
        }
    },
    "network": {
        "wireless": {
            "ssid": "",
            "key": ""
        }
    }
}
```

To configure your custom GPU fan control table you must add table values to JSON configuration file as specified below
```json
{
    "rig": {
        "btc": "",
        "worker": "",
        "group": ""
    },
    "access": {
        "ssh": {
            "key": ""
        }
    },
    "network": {
        "wireless": {
            "ssid": "",
            "key": ""
        }
    },
    "fan_control": [
        {"tmpc": 40, "spdp" : 25},
        {"tmpc": 45, "spdp" : 35},
        {"tmpc": 50, "spdp" : 40},
        {"tmpc": 55, "spdp" : 50},
        {"tmpc": 60, "spdp" : 60},
        {"tmpc": 65, "spdp" : 70},
        {"tmpc": 70, "spdp" : 75},
        {"tmpc": 75, "spdp" : 80},
        {"tmpc": 80, "spdp" : 85},
        {"tmpc": 85, "spdp" : 95},
        {"tmpc": 90, "spdp" : 100}
    ]
}
```
From the example fan control table above one can see that table has two columns. First column specifies temperature in degrees celsius while second column specifies desired fan speed in percent when specified temperature is reached.

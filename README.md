# demo-tuned
Quick demo of tuned capabilities

Tuned is a daemon that uses udev to monitor connected devices and statically and dynamically tunes system settings according to a selected profile. Tuned is distributed with a number of predefined profiles for common use cases

Question: Ever opened a case or search KBase for best practices related to performance?
* Answer: tuned
* Predefined sysctl and sysfs settings, based on best practices and real-world workloads

Tuned provides recommended configurations for common workloads
* Easy to apply
* Easy to customize
* Persists across reboots
* Installed and enabled with RHEL 7
* Available for RHEL 6 as well

Number of predefined profiles for common use cases:

* Default profiles from base package
  * balanced -- default power-saving profile. It is intended to be a compromise between performance and power consumption
  * powersave -- for maximum power saving performance
  * throughput-performance -- server profile optimized for high throughput
  * latency-performance -- server profile optimized for low latency
  * network-latency -- for low latency network tuning
  * network-throughput -- for throughput network tuning
  * virtual-guest -- based on the enterprise-storage profile that, among other tasks, decreases virtual memory swappiness and increases disk readahead values.
  * virtual-host -- based on the enterprise-storage profile that, among other tasks, decreases virtual memory swappiness, increases disk readahead values and enables a more aggressive value of dirty pages


* Additional Profiles for:
  * Atomic and OpenShift
  * Oracle (via optional repo)
  * SAP & SAP HANA included in RHEL for SAP sub
  * Via the tuned-profiles-compat package available in the Optional channel

Monitoring plug-ins
* disk -- Gets disk load (number of IO operations) per device and measurement interval.
* net -- Gets network load (number of transferred packets) per network card and measurement interval.
* load -- Gets CPU load per CPU and measurement interval.

Tuning plug-ins
* cpu -- Sets the CPU governor to the value specified by the ```governor``` parameter and dynamically changes the PM QoS CPU DMA latency according to the CPU load
* eeepc_she -- Dynamically sets the FSB speed according to the CPU load
* net -- Configures wake-on-lan to the values specified by the ```wake_on_lan``` parameter
* sysctl -- Sets various ```sysctl``` settings specified by the plugin parameters
* usb -- Sets autosuspend timeout of USB devices to the value specified by the ```autosuspend``` parameter
* vm -- Enables or disables transparent huge pages depending on the Boolean value of the ```transparent_hugepages``` parameter
* audio -- Sets the autosuspend timeout for audio codecs to the value specified by the ```timeout``` parameter
* disk -- Sets the elevator to the value specified by the ```elevator``` parameter
* mounts -- Enables or disables barriers for mounts according to the Boolean value of the ```disable_barriers``` parameter
* script -- This plugin can be used for the execution of an external script that is run when the profile is loaded or unloaded
* sysfs -- Sets various ```sysfs``` settings specified by the plugin parameters
* video -- Sets various powersave levels on video cards (currently only the Radeon cards are supported)
* bootloader -- Adds parameters to the kernel boot command line

Dynamic tuning is globally disabled in Red Hat Enterprise Linux and can be enabled by editing the ```/etc/tuned/tuned-main.conf``` file and changing the ```dynamic_tuning``` flag to 1

[Reference Documentation](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/performance_tuning_guide/chap-red_hat_enterprise_linux-performance_tuning_guide-tuned)

# X-Plane specific Topics



### Known incompatible X-Plane Plugins

```
- SAM - Scenery Animation Manager (stairportsceneries.plugin.aos)
```

This xplane-plugin can cause the SPAD plugin to crash and then crash X-Plane. Since that plugin is outdated and known to be incompatible to xp12 and is no longer maintained for a long time already, it is recommended to uninstall it

### X-Plane crashes with custom datarefs.txt

If X-Plane crashes after the aircraft is loaded and you have a custom datarefs.txt in place, check the X-Plane logfile for the last "AddDataref"-Entry from SPAD. This is normally the dataref that causes a problem, and most likely you will see a deprecated warning. Removing that dataref (and all datarefs in the same group) from your datarefs.txt should resolve this issue.



### X-Plane error: Discover port blocked

Most likely you have something running like e.g. Hyper-V which reserved the ports that are used by X-Plane for external communication. You will need to tell it not to reserve those ports.\
You can check with this commands:\


```
netsh int ipv4 show excludedportrange protocol=tcp
netsh int ipv4 show excludedportrange protocol=udp
```

\
\
None of the lists should include port **49707**\
You can change that reserved range as described here

[https://dandini.wordpress.com/2019/07/15/administered-port-exclusions-blocking-high-ports/](https://dandini.wordpress.com/2019/07/15/administered-port-exclusions-blocking-high-ports/)

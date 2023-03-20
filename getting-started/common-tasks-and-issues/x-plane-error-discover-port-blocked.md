# X-Plane error: Discover port blocked

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

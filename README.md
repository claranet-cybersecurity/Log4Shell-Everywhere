This is a simple (hacky!) fork of James Kettle's excellent [Collaborator Everywhere](https://github.com/PortSwigger/collaborator-everywhere/), with the injection parameters changed to payloads for the critical log4j CVE-2021-44228 vulnerability. This extension only works on in-scope traffic, and works by injecting headers into your proxy traffic with log4j exploits. 

To avoid false positives with pingbacks such as with DNS requests made from host regex matching, and to potentially bypass filters, the `${lower:x}` pattern is used in the DNS request to establish confidence that there is some level of injection. 

To use it, simply install it and browse the target website. Findings will be presented in the 'Issues' tab. You can easily customise injected payloads by editing /resources/injections

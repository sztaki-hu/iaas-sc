# Physical infrastructure
## Physical resources
* Perform regular hardware checkups
* Provide multi-failure disaster recovery capability
* Consider disabling simultaneous multi-threading (SMT) to combat covert channel attacks
* Provide isolated instances for security-critical systems
* Provide proof of retrievability (PoR)
* Proof of deletion for deleted files (nullification)
* Have sufficient backup and recovery plan
* The backup should be encrypted, and possibly at multiple locations
* Publish your log files in multiple places in order that they are harder to corrupt
* Use security protocols and network security equipment for data-in-transit
* Define limits to usage to combat denial of service
* Monitor cache anomalies during sensitive operations

## Cryptography
* Use strong, state of the art cryptography approaches (e. g. ECC, SVM, combined solutions)
* Protect and encrypt log files
* Sanitize cloud storage after release
* Have a good key rotation policy, backup, recovery system, secure storage and strong access control in key management
* RAM and other kinds of volatile data stores should be nullified on VM start.

## Trusted computing
* Provide a Trusted Platform Module for the user
* Use Secure Component for integrity protection
* Have a Trusted Third Party available for key management and attestation
* Use late launch (or DRTM) to prevent TPM reset and BIOS attacks
* Enable remote attestation

# Virtual Infrastructure
## General
* In virtual network, security service functions (e. g. firewall, IDS) should be collaborating/organized
* Provide the possibility for dedicated infrastructure/virtual public cloud
* Use self-recovery/healing approach for virtual machines
* Protect hypervisor as it is one of the most vulnerable parts
* During migration, security policies of the VM should be applied to the security devices in that area, such as IDS and firewalls
* Limit hypervisor access to protected areas
* Continuously monitor VMs and detect anomalies

## VM Updates
* Use offline updates for VMs, but consider drawbacks
* The template VM should be configured to look for security updates as soon as possible after first launch.
* The template VM should be configured to block incoming connections until security updates are done.
* There should be a master VM that is updated ASAP when OS updates are available. New VMs are created replicating this master.
* System administrators should be able to easily access the list of rolled back (reverted from snapshot, backup, etc.) machines.
* The user should be informed about the risks of rollback.

## VMI Protection
* Pay attention to the maintenance of VMIs
* VM templates should not contain any information that can be exploited by someone having access to the same VM template
* User-created VM templates should be separate from IaaS-provided official templates.
* Information on creator, creation date, and verification should be visible when choosing VM template.
* Protect VMIs with encryption using end users’ own keys

## Software updates
* Provide update-rollback tools.
* Components should be functional even when they have access to an isolated network only.
* Update sources should be verified.
* Failover solutions should exist for every component.
* Live migration of VMs should be done.
* Staging support should be in place.

# Operations Center

## Monitoring
* Monitor user behavior using machine learning algorithms
* Monitor system calls, changes in network (and devices)
* Use security-validation wrapper (continuous validation)
* Capture incidents in logs
* Use central logging server
* Be prepared for anti-forensics attacks
* Consider security questions while allocating resources
* Regularly perform penetration testing
* Establish an intrusion detection system
* Establish a DDoS detection system e. g. with machine learning

## Networking
* Use SSL/TLS protocols for transactions
* Enable client certificate for SSL/TLS
* Disable pinging
* Close unused ports
* Use Antivirus software
* Separate VM traffic from management traffic
* ARP and DHCP packages must be blocked unless coming from a valid source.
* An attacker VM should not effectively claim the IP of another VM. IP packets are only allowed to be sent and received by the valid VM.
* VM migration should happen on a separate network, isolated from the VMs.
* Security measures available for IPv4 should be supported for IPv6.
* A VM should either be providing on IPv4 or IPv6.
* IPv6 addresses should not be assigned unless explicitly requested.
* In case of IPv6 IaaS clouds, NAT functionality should be emulated by firewalling every packet except those belonging to an established flow or allowed explicitly by firewall rules.
* Each tenant should have its own VLAN.

## API
* All webpages and REST endpoints should use certificates trusted by the user.
* Server-side certificates should be trusted by stock browsers.
* Client certificates should be required.
* Cloud administrators and users should have separate web administration pages.
* OWASP ASVS v3 testing should be done (especially chapters V2-V8, possibly by the IaaS software vendor).
* Fuzz testing of WEB APIs should be done (possibly by the IaaS software vendor)
* Use VPN
* Use HTTPS to protect endpoints

# User portal
## Authentication
* Use Single Sign-On, possibly biometric
* Use Multi-factor authentication
* Use automatized validation of authentication
* Use behavior profiling for continuous verification
* Force users to use strong passwords and have a strong password lifecycle management
* Use digital signatures for stronger authentication
* Consider using external IdP with extra caution
* Send notifications for agreements and breaches

## Access Control and Authorization
* Use indirect references to objects by client or session
* Use hierarchical roles in role based access control
* Eliminate conflicts of interests over resources
* Prevent modification by unauthorized users
* Prevent authorized users from unauthorized modifications
* Use standard protocols for authorization

# Other Security measures
## User information
* Provide information on the stored data e. g. physical storage location
* Security policy customization should be available for users
* Users should get warnings on predefined usage limits.
* Users should be able to define usage policies such as maximum usage per time span or maximum usage per client (where applicable, e.g., based on IP addresses).
* Warn users about security concerns
* Establish trust with users via transparency
* User access should be provided to view the settings of the virtualization container.
* User access should be provided for software version numbers of the underlying operating system/kernel and the virtualization architecture.
* User access should be provided to the virtualization container logs of their VMs.
* User access should be provided to network security logs concerning their VMs.

## Audit/other
* Use third-party auditor to prove trustworthiness
* Regularly assess the vulnerabilities of the system
* Try to comply with ISO, NIST and CSA guidelines
* Consider the security of the system while running tests
* Consider using forensic tools

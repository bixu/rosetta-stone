## Shell basics

### Logged in user account

#### Windows Server
	$env:username
#### Red Hat Enterprise Linux
	whoami
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	whoami
#### OpenBSD
	whoami
#### SmartOS
    ?

### Host name

#### Windows Server
	$env:COMPUTERNAME
#### Red Hat Enterprise Linux
	hostname
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	hostname
#### OpenBSD
	hostname
#### SmartOS
    ?


### Run as a different user

#### Windows Server
	runas /user:[machine or domain name]\[admin account name] [command]
#### Red Hat Enterprise Linux
	sudo [command]
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	sudo [command]
#### OpenBSD
	sudo [command]
#### SmartOS
    ?


### Run shell as a different user

#### Windows Server
	Start-Process powershell -Verb runAs
#### Red Hat Enterprise Linux
	sudo -i
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	sudo -i
#### OpenBSD
	sudo -i
#### SmartOS
    ?

## Hardware Inspection


### EFI/BIOS serial numbers

#### Windows Server
	Get-WmiObject -Class Win32_BIOS
#### Red Hat Enterprise Linux
	dmidecode
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	system_profiler SPHardwareDataType
#### OpenBSD
	dmidecode
#### SmartOS
    ?


### CPU info
#### Windows Server
	Get-WmiObject -Class Win32_Processor
#### Red Hat Enterprise Linux
	less /proc/cpuinfo
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	system_profiler SPHardwareDataType
#### OpenBSD
	sysctl hw.ncpu
#### SmartOS
    ?

### Physical memory

#### Windows Server
	Get-WmiObject -Class  Win32_PhysicalMemory
#### Red Hat Enterprise Linux
	less /proc/meminfo
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	system_profiler SPMemoryDataType
#### OpenBSD
	?

## Network Connectivity

### Ethernet connectivity

#### Windows Server
	get-wmiobject win32_networkadapter | select netconnectionId, name, interfaceIndex, netConnectionStatus

The select is required because netConnectionStatus isn't in the default properties.
#### Red Hat Enterprise Linux
	ethtool
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	?
#### OpenBSD
	?
#### SmartOS
    ?

### IP connectivity
#### Windows Server
	Test-Connection "[ip address]"
#### Red Hat Enterprise Linux
	ping
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	ping
#### OpenBSD
	?#### SmartOS
	?
#### Debian
	?
#### SmartOS
    ?

### DNS resolution
#### Windows Server
	Resolve-DnsName "[hostname]"
#### Red Hat Enterprise Linux
	host / dig
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	host / dig
#### OpenBSD
	host / dig
#### SmartOS
    ?

### IP addressing
#### Windows Server
	Get-NetIPAddress
#### Red Hat Enterprise Linux
	ip addr
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	ifconfig
#### OpenBSD
	ifconfig
#### SmartOS
    ?

### Ethernet connectivity
#### Windows Server
	?
#### Red Hat Enterprise Linux
	ethtool
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	?
#### OpenBSD
	?
#### SmartOS
    ?

### whois
#### Windows Server
	$web = New-WebServiceProxy 'http://www.webservicex.net/whois.asmx?WSDL'
	$web.GetWhoIs('[domain name]')
#### Red Hat Enterprise Linux
	whois 'domain [domain name]'
#### Debian
As above.
#### Ubuntu
As above.
#### OS X
	whois 'domain [domain name]'
#### OpenBSD
	?
#### SmartOS
    ?

## Services


### Installed to
#### Windows Server
	Get-Service
#### Red Hat Enterprise Linux
	/etc/system
#### Debian
As above.
#### Ubuntu
	/etc/init.d
#### OS X
	/System/Library/LaunchDaemons/
#### OpenBSD
	?
#### SmartOS
    ?

### List Services
#### Windows Server
	?
#### Red Hat Enterprise Linux
	systemctl list-unit-files --type=service
#### Debian
As above.
#### Ubuntu
	ls /etc/init.d
#### OS X
	launchctl list
#### OpenBSD
	?
#### SmartOS
    ?

### Start Service
#### Windows Server
	?
#### Red Hat Enterprise Linux
	systemctl start servicename
#### Debian
As above.
#### Ubuntu
	/etc/init.d/[service file] start
#### OS X
	launchctl load -w /System/Library/LaunchDaemons/ssh.plist
#### OpenBSD
	?
#### SmartOS
    ?

### Stop Service
#### Windows Server
	Stop-Service [servicename]
#### Red Hat Enterprise Linux
	systemctl stop [servicename]
#### Debian
As above.
#### Ubuntu
	/etc/init.d/[service file] stop
#### OS X
	launchctl unload -w /System/Library/LaunchDaemons/ssh.plist
#### OpenBSD
	pkill [process name of service]
#### SmartOS
    ?

### Restart Service
#### Windows Server
	Restart-Service [servicename]
#### Red Hat Enterprise Linux
	systemctl restart [servicename]
#### Debian
As above.
#### Ubuntu
	/etc/init.d/[service file] restart
#### OS X
	?
#### OpenBSD
	?
#### SmartOS
    ?




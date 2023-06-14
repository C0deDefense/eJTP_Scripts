# eJTP_Scripts
#Script's for Penetration testing
# eJTP_Scripts
#Script's for Penetration testing First run an ARP scan to enumerate systems within the IP range
#ensure to make this script executable with chmod +x
#.\ARP_SCAN.sh eth0 192.168.0.0/24
#!/usr/bin/env bash
if [ -z "$1" ]; then
	echo "Usage: enter Interface followed by ip range example .\ARP_SCAN.sh eth0 192.168.0.0/24"
	exit 1
fi

if [ -z "$2" ]; then
	echo "Usage: enter Interface followed by ip range example .\ARP_SCAN.sh eth0 192.168.0.0/24"
	exit 2
fi

sudo arp-scan -I $1 -g $2 | tail -n +5 | head -n -3 >> results.txt

cat results.txt

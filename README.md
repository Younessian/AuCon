AuCon
AuCon is a lightweight Bash utility designed for network reconnaissance and domain resolution. It enables you to quickly resolve domains, process lists of subdomains, and scan CIDR ranges to find live IP addresses—all from the command line.

Features
Domain Resolution: Quickly resolve a single domain's IP address with the -d flag.
Subdomain Processing: Process a file containing a list of subdomains with the -u option, removing duplicate entries.
Domains List Processing: Handle a list of domains from a file with the -l option.
CIDR Range Scanning: Scan a given CIDR range (e.g., 192.168.1.0/24) for live IP addresses using nmap with the -r option.
Simple Interface: A clear and concise help message guides you through usage.
Prerequisites
Bash Shell: AuCon is designed to run on Linux or any Unix-like system.
nmap: Required for scanning CIDR ranges. Install it using your package manager (e.g., sudo apt-get install nmap).
Installation
Clone the Repository:
bash
Copy
Edit
git clone https://github.com/Younessian/AuCon.git
cd AuCon
Make the Script Executable:
bash
Copy
Edit
chmod +x aucon
Making AuCon Globally Accessible:
bash
Copy
Edit
sudo cp aucon /usr/local/bin/
Usage
Display Help
Show the help message with all available options:

bash
Copy
Edit
aucon -h
Resolve a Single Domain
Resolve the IP address for a given domain:

bash
Copy
Edit
aucon -d example.com
Process a List of Subdomains
Read subdomains from a file and resolve their IP addresses (duplicates are removed):

bash
Copy
Edit
aucon -u domains.txt
Process a List of Domains
Read and resolve IP addresses for a list of domains from a file:

bash
Copy
Edit
aucon -l domains_list.txt
Scan a CIDR Range for Live IP Addresses
Scan a CIDR range to find live hosts:

bash
Copy
Edit
aucon -r 192.168.1.0/24
Patch Notes
Added CIDR Range Scanning: Introduced the -r option to scan a CIDR range for live IP addresses using nmap.
Enhanced Help Message: Updated the usage instructions to reflect the new -r option.
Improved Error Handling: Added checks to ensure necessary arguments are provided for each option.
Contributing
Contributions are welcome! If you have suggestions or improvements, please open an issue or submit a pull request.

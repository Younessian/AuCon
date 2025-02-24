# AuCon - Automated Subdomain Enumeration & Change Detection

## Overview
AuCon is a shell script (compatible with Bash and Zsh) for automating subdomain enumeration and change detection. It uses `crt.sh` and `subfinder` to gather subdomains and compares results to detect new findings.

## Features
- Reads target domains from `targets.txt` or command-line arguments.
- Enumerates subdomains using `crt.sh` and `subfinder`.
- Stores results and detects new subdomains compared to previous scans.
- Saves historical results for tracking changes over time.

## Requirements
- `curl`
- `jq`
- `subfinder`

## Installation
Ensure you have the required dependencies installed:

```sh
sudo apt update && sudo apt install -y curl jq
```

Install `subfinder`:

```sh
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
```

Clone the repository and make the script executable:

```sh
git clone https://github.com/Younessian/AuCon.git
cd AuCon
chmod +x aucon.sh
```

For easier usage, you can copy the script to `/usr/local/bin/` to make it globally accessible:

```sh
sudo cp aucon.sh /usr/local/bin/aucon
```

Now you can run it from anywhere:

```sh
aucon example.com
```

## Usage
### Running the script
#### Using a target file:
Create a `targets.txt` file with target domains (one per line):

```sh
echo "example.com" > targets.txt
aucon
```

#### Providing targets via command line:
```sh
aucon example.com anotherdomain.com
```

## How It Works
1. The script checks for `targets.txt` or uses command-line arguments.
2. It performs subdomain enumeration using:
   - `crt.sh` for certificate transparency logs.
   - `subfinder` for comprehensive enumeration.
3. Results are processed and stored in `Subdomains`.
4. Previous results are compared to detect new subdomains.
5. Changes are logged in `Fresh` and `Today` files.

## Output Files
- `Subdomains`: Contains unique subdomains found.
- `Fresh`: Contains all newly discovered subdomains since the last scan.
- `Today`: Contains only the subdomains discovered in the most recent scan.
- `previous_results/`: Stores past results for tracking.

## Cleanup
Temporary files are deleted automatically after execution.

---
Enjoy automated subdomain enumeration and tracking with AuCon! 🚀


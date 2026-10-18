Backhaul Manager

A feature-rich, interactive Bash manager for Backhaul tunneling on Linux servers.

Backhaul Manager is an open-source, terminal-based management utility designed to simplify the deployment, configuration, monitoring, and maintenance of Backhaul tunnels across servers in different network environments.

It provides an interactive interface for configuring tunnel endpoints, managing systemd services, monitoring resource usage, viewing logs, and tuning connection parameters without manually creating every configuration file.

Features

Tunnel Configuration

- Interactive tunnel creation and configuration.
- Support for TCP, TCPMUX, WSMUX, and WSSMUX transport modes.
- Separate configuration workflows for Iran-side and overseas servers.
- Preset tuning parameters and advanced manual configuration.
- Port mapping validation and port-conflict checks.
- TOML configuration file generation and editing.

Service Management

- Create and manage multiple tunnel services.
- Start, stop, and restart individual tunnels.
- Bulk service operations.
- Integration with systemd.
- Configuration backups before supported modifications.
- Tunnel deletion and service lifecycle management.

Monitoring and Diagnostics

- Live tunnel monitoring.
- Service status reporting.
- CPU and memory usage visibility.
- Process uptime monitoring.
- Live systemd journal logs.
- Log filtering for errors, warnings, and informational messages.
- Basic connection-state interpretation based on service logs.

Binary Installation

- Download the latest Backhaul release from GitHub.
- Support for custom download URLs and local archives.
- Automatic architecture selection for common x86-64 and ARM64 systems.
- Backup of the existing binary before replacement.

SSH Configuration Synchronization

- Dedicated Ed25519 SSH key generation.
- Transfer of selected TOML configuration files to a peer server.
- Remote systemd service restart after synchronization.
- Interactive confirmation before transferring configurations.

TLS Support

- Self-signed certificate generation for WSSMUX configurations.
- Dedicated certificate and key storage under the Backhaul configuration directory.

Requirements

- A compatible Linux environment.
- Bash and standard Linux command-line utilities.
- systemd for service management.
- Root privileges for system-level installation and configuration.
- Required utilities such as "tar", "ssh", "scp", "ssh-keygen", and "openssl", depending on the selected features.
- Network access to the relevant download source.

Installation

Clone the repository:

git clone https://github.com/alirezalaleh2005/backhaul-manager.git
cd backhaul-manager

Review the script before executing it with elevated privileges:

less Backhaul.sh

Then run it as root:

sudo bash Backhaul.sh

Follow the interactive menu to configure your tunnels and manage the corresponding services.

Configuration and Data

The script uses the following primary paths:

Path| Purpose
"/etc/backhaul/"| Configuration and application data
"/etc/backhaul/backups/"| Configuration and binary backups
"/etc/backhaul/certs/"| TLS certificates and private keys
"/usr/local/bin/backhaul"| Backhaul executable
"/etc/systemd/system/"| Generated systemd service units

Security Considerations

Backhaul Manager performs privileged system operations. Review the code and understand its behavior before deploying it on production servers.

- Verify downloaded binaries and their sources before installation.
- Prefer SSH host-key verification instead of disabling strict host-key checking.
- Restrict SSH access and use least-privilege credentials wherever possible.
- Protect private keys, configuration files, and TLS private keys.
- Review firewall rules and exposed listening ports.
- Back up configurations before making changes.
- Test updates and configuration changes in a non-production environment first.

Project Status

This project is actively intended to simplify operational workflows around Backhaul tunneling. Compatibility, security, and reliability should be validated against the target Linux distribution and the specific Backhaul release being deployed.

Contributing

Contributions, bug reports, and feature suggestions are welcome.

When submitting an issue, include the Linux distribution, Backhaul version, relevant service logs, and steps to reproduce the problem. Remove private IP addresses, credentials, and other sensitive information before sharing logs.

License

Refer to the repository's license file for the applicable licensing terms.

Author

Alireza Laleh

GitHub: "@alirezalaleh2005" (https://github.com/alirezalaleh2005)

Disclaimer

This project is an independent management utility and is not presented as an official component of the Backhaul upstream project.

---

Backhaul Manager — Simplifying tunnel deployment, configuration, and monitoring.

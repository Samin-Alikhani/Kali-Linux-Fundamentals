# Kali Linux Fundamentals

This project documents my hands-on practice with Linux administration and introductory security concepts in an authorized Kali Linux lab environment. I worked with system information, network configuration, filesystem navigation, environment variables, file permissions, and network service discovery. I also researched how Kali tools apply to common security scenarios.

Machine-specific information, internal addresses, and original course materials have been excluded from this repository.

## Project Overview

I built this project to strengthen my Linux and networking fundamentals. The exercises helped me move beyond memorizing commands by focusing on how to interpret their output, understand system behavior, and apply the concepts during troubleshooting and security analysis.

## Skills Demonstrated

- Linux command-line navigation and system inspection
- IPv4 addressing, routing, and subnet interpretation
- DNS resolution and network-interface inspection
- Filesystem and disk-usage analysis
- Shell environment variables and executable search paths
- Linux ownership and permission reasoning
- Nmap host, port, service, and version discovery
- Evidence-based vulnerability research with SearchSploit and CVE records
- Active reconnaissance versus passive monitoring
- Security-tool selection for forensics, networking, Bluetooth, and Android analysis

## Project contents

| File | Purpose |
| --- | --- |
| [Linux Fundamentals](linux-fundamentals.md) | Commands, observations, and security relevance from the hands-on exercises |
| [Kali Tools Overview](kali-tools-overview.md) | Tool-to-task decisions for five security scenarios |
| [Network Service and Vulnerability Discovery Lab](network-service-vulnerability-discovery/README.md) | Authorized host discovery, TCP and UDP enumeration, service validation, and vulnerability research |
| [Lessons Learned](notes/lessons-learned.md) | Key takeaways and next steps for deeper SOC practice |

## Highlights

### Host and Network Awareness

I used standard Linux utilities to inspect boot time, kernel information, storage, interfaces, DNS results, and the current working directory. Rather than treating the output as a checklist, I connected each command to an analyst use case such as validating a reboot, identifying network context, or checking available storage before collecting evidence.

### Permission Behavior

I created a temporary file, changed its owner to `root` with elevated privileges, verified the result, and examined why a user may still delete that file from a user-owned directory. The exercise reinforced that deletion is governed primarily by permissions on the containing directory, not only by ownership of the file.

### Network Service Discovery

I assessed an authorized private lab subnet with Nmap, identified five responsive systems, enumerated TCP and UDP services, and validated application versions. I then used SearchSploit and authoritative CVE records to document five qualified vulnerability candidates without exploiting the targets.

### Security-Tool Selection

I evaluated tools for forensic acquisition, active service discovery, passive packet analysis, Bluetooth discovery, and Android decompilation. These were scenario-based selections; this project does not claim that every listed tool was executed.

## Example Workflow

```bash
# Inspect host state
uptime -s
uname -r
df -h

# Inspect network context
ip addr
ip route

# Inspect shell context
pwd
echo "$SHELL"
printf '%s\n' "$PATH"
```

Selected evidence is included with the individual write-ups. Original course documents and grading material are not published.

## Related SOC Project

I have since applied the habit of checking system state, permissions, and network context in my [Windows Authentication Monitoring with Splunk Cloud](https://github.com/Samin-Alikhani/Splunk-Windows-Authentication-Monitoring) project. That separate Windows lab documents log collection, controlled failed-login tests, a scheduled alert, and an authentication dashboard.

A future extension would be a Linux authentication investigation with its own evidence and triage notes; that work is not yet documented here.

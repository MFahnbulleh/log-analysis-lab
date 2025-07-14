## Issue 1

**Log Entries:**

```plaintext
2023-02-17 09:34:14 192.168.1.49 216.109.119.63 TCP 25 Allow 7421
```

**Description of log entries:** SMTP (email) traffic from an internal host.

**Reason for concern:** Direct SMTP outbound traffic could indicate spam or compromised device sending emails.

**Potential impact:** Blacklisting of public IP, defiltration..

**Possible explanations:** Misconfigured client, malware exfiltration, or legitimate server traffic.

## Issue 2

**Log Entries:**

```plaintext
2023-02-17 09:34:01 192.168.1.211 62.128.197.131 UDP 51820 Allow 1440
```

**Description of log entries:** WireGuard VPN traffic outbound.

**Reason for concern:** Unexpected VPN traffic could hide data exfiltration or bypass controls.

**Potential impact:** Data loss, unauthorized access.

**Possible explanations:** Employee using VPN, malware evading detection.

## Issue 3

**Log Entries:**

```plaintext
2023-02-17 09:34:03 192.168.1.27 45.137.80.15 TCP 41284 Deny 48
```

**Description of log entries:**  Denied connection to high-numbered external port.

**Reason for concern:** Potential C2 (Command and Control) communication attempt.

**Potential impact:** External compromise attempt or infected host.

**Possible explanations:** Malware or misconfigured application.

## Issue 4

**Log Entries:**

```plaintext
2023-02-17 09:34:35 192.168.1.31 8.8.8.8 TCP 53 Allow 435
2023-02-17 09:34:36 192.168.1.31 8.8.4.4 UDP 53 Allow 289
```

**Description of log entries:** DNS queries to Google DNS servers.

**Reason for concern:** Bypassing internal DNS monitoring or policies.

**Potential impact:** DNS tunneling, visibility gaps.

**Possible explanations:** Manually set DNS, mobile device behavior.

## Issue 5

**Log Entries:**

```plaintext
2023-02-17 09:36:07 192.168.1.61 217.23.2.15 TCP 21 Allow 3629
2023-02-17 09:36:15 192.168.1.61 141.98.10.195 TCP 21 Allow 2745
```

**Description of log entries:** FTP traffic to external IPs.

**Reason for concern:** FTP is unencrypted; potential data leakage.

**Potential impact:** Credential theft, data exfiltration.

**Possible explanations:** Outdated backup process, malicious activity.

## Issue 6

**Log Entries:**

```plaintext
2023-02-17 09:34:50 fdf8:f53b:82e4::53 fdf8:f53b:82e4:0:1652:14ff:fe0b:b71c TCP 22 Deny 0
```

**Description of log entries:** Denied SSH over IPv6.

**Reason for concern:** Unmonitored IPv6 traffic vector.

**Potential impact:** Undetected remote access attempts.

**Possible explanations:** Misconfigured IPv6 services, scan attempt.

## Issue 7

**Log Entries:**

```plaintext
2023-02-17 17:30:00 192.168.1.101 10.0.0.200 TCP 21 Deny 4096
```

**Description of log entries:** Denied connection to an external high-numbered port.

**Reason for concern:** Could be a botnet or malware trying to communicate.

**Potential impact:** Malicious activity, data loss.

**Possible explanations:** Suspicious app, outbound scan, malware.

## Issue 8

**Log Entries:**

```plaintext
2023-02-17 09:38:24 192.168.1.72 111.221.29.254 TCP 443 Deny 0
2023-02-17 09:38:31 192.168.1.72 111.221.29.254 TCP 443 Deny 0
2023-02-17 09:38:39 192.168.1.72 111.221.29.254 TCP 443 Deny 0
2023-02-17 09:38:46 192.168.1.72 111.221.29.254 TCP 443 Deny 0
2023-02-17 09:38:53 192.168.1.72 111.221.29.254 TCP 443 Deny 0
```

**Description of log entries:** Repeated denied attempts to same IP over HTTPS.

**Reason for concern:** Persistent unauthorized connection attempts.

**Potential impact:** Brute force, malware communication attempt.

**Possible explanations:** Misconfigured service, malware retrying.

## Issue 9

**Log Entries:**

```plaintext
2023-02-17 09:39:03 192.168.1.19 40.94.31.197 TCP 1433 Allow 37419
2023-02-17 09:39:08 192.168.1.19 40.94.25.38 TCP 1433 Allow 32780
2023-02-17 09:39:11 192.168.1.19 40.94.28.182 TCP 1433 Allow 41935
```

**Description of log entries:**  Outbound SQL Server (port 1433) traffic.

**Reason for concern:** SQL traffic exposed externally may allow DB enumeration or attack.

**Potential impact:** Data leakage, SQL injection exploitation.

**Possible explanations:** Misconfigured database sync, or unauthorized database access.

## Issue 10

**Log Entries:**

```plaintext
2023-02-17 09:39:19 127.0.0.1 127.0.0.1 TCP 9200 Allow 38192
2023-02-17 09:39:22 127.0.0.1 127.0.0.1 TCP 9200 Allow 44735
2023-02-17 09:39:25 127.0.0.1 127.0.0.1 TCP 9200 Allow 61208
```

**Description of log entries:** Localhost traffic on Elasticsearch port.

**Reason for concern:** Elasticsearch vulnerable to unauth access if improperly secured.

**Potential impact:** Unauthorized data scraping or manipulation.

**Possible explanations:** Local monitoring or dashboard tool, or exposed web API

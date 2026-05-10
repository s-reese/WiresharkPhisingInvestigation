# Wireshark Phishing Investigation

## Overview

This project focused on analyzing `.pcap` network traffic files in Wireshark to identify phishing-related email activity and determine the source of suspicious SMTP traffic. The investigation involved reviewing captured email traffic, applying protocol filters, analyzing email subject lines, and tracing suspicious IP activity.

## Objective

* Analyze `.pcap` files using Wireshark
* Identify phishing-related email traffic
* Determine the suspicious source IP address
* Review indicators commonly associated with phishing emails

## Tools Used

* Wireshark
* PCAP files
* SMTP protocol filtering

## Investigation Process

### Step 1: Review SMTP Traffic

I opened each `.pcap` file in Wireshark and applied the following filter to isolate email traffic:

```plaintext id="w1"
smtp
```

This allowed me to focus specifically on SMTP communications instead of all captured network traffic.

### Step 2: Identify Suspicious Emails

Next, I used the following filter to locate received email activity:

```plaintext id="w2"
smtp contains "from"
```

I reviewed sender information and searched for unusual or suspicious email addresses that appeared multiple times throughout the captures.

### Step 3: Analyze Email Subject Lines

To inspect email content and subject lines, I applied the following filter:

```plaintext id="w3"
smtp.data.fragment
```

During the investigation, I identified multiple suspicious phishing-style subject lines, including:

* "Your ife about to get ruined!"
* "Data of you and your family! - peace"
* "Your password!"

### Step 4: Identify the Source IP

After reviewing the SMTP traffic and phishing indicators, I analyzed the source and destination information within the packets to determine the suspicious originating IP address.

## Findings

* Suspicious IP Address: `10.6.1.104`
* Multiple phishing-related emails were identified within the SMTP traffic
* Email subject lines contained threatening and extortion-related language commonly associated with phishing campaigns

## Skills Demonstrated

* Network traffic analysis
* Wireshark filtering and packet inspection
* SMTP protocol analysis
* Phishing investigation
* Threat identification
* Investigative problem-solving

## Screenshots

Included screenshots of phishing-related email content identified during the investigation. The screenshots demonstrate examples of suspicious email subject lines and phishing indicators discovered through SMTP traffic analysis in Wireshark.

<img width="624" height="327" alt="Picture1" src="https://github.com/user-attachments/assets/9d771e1e-eacf-4181-910c-eb19a9a85387" />
<img width="624" height="406" alt="Picture2" src="https://github.com/user-attachments/assets/6d940d97-c580-4bf9-93f9-f09b8cc207aa" />
<img width="624" height="366" alt="Picture3" src="https://github.com/user-attachments/assets/07097e3a-bfac-4ae7-b058-3dcfc54edd70" />


# ARP Attack Lab Project

## Overview
This lab project explores the concepts of **ARP Cache Poisoning** and **Man-in-the-Middle (MITM) Attacks** using ARP attacks. The tasks involve setting up a network environment, performing ARP poisoning attacks, and analyzing their impact on network communication. The project is structured into multiple tasks, each focused on different aspects of ARP attacks, including using ARP requests, replies, and gratuitous messages, as well as executing MITM attacks on Telnet and Netcat communications.

## Table of Contents
1. [Task 0: Setting up SEED Labs](#task-0-setting-up-seed-labs)
2. [Task 1: ARP Cache Poisoning](#task-1-arp-cache-poisoning)
   - [Task 1.A: ARP Request](#task-1a-arp-request)
   - [Task 1.B: ARP Reply](#task-1b-arp-reply)
   - [Task 1.C: ARP Gratuitous Message](#task-1c-arp-gratuitous-message)
3. [Task 2: MITM Attack on Telnet using ARP Cache Poisoning](#task-2-mitm-attack-on-telnet-using-arp-cache-poisoning)
4. [Task 3: MITM Attack on Netcat using ARP Cache Poisoning](#task-3-mitm-attack-on-netcat-using-arp-cache-poisoning)
5. [Deliverables](#deliverables)

## Task 0: Setting up SEED Labs
In this task, the SEED Lab environment was set up to perform the ARP attack experiments. The setup involved either using DigitalOcean (Option A) or VirtualBox (Option B) to create the required virtual machines. The following steps were performed:
- Switched to the “seed” user.
- Downloaded the lab setup file “Labsetup.zip” and followed the instructions to configure the network environment.

Note: Screenshots and code snippets were attached for the setup process as required.

## Task 1: ARP Cache Poisoning
This task involved performing ARP cache poisoning using different methods. The goal was to manipulate the ARP cache of Host A to map Host B’s IP address to Host M’s MAC address, allowing M to intercept traffic intended for B.

### Task 1.A: ARP Request
In this step, an ARP request packet was constructed on Host M to map Host B’s IP address to M’s MAC address. The packet was sent to Host A to check if the attack was successful.

### Task 1.B: ARP Reply
An ARP reply packet was constructed on Host M to map Host B’s IP address to M’s MAC address. The attack was tested under two scenarios:
- Scenario 1: B’s IP was already in A’s ARP cache.
- Scenario 2: B’s IP was not in A’s ARP cache (cleared using `arp -d`).

### Task 1.C: ARP Gratuitous Message
In this step, an ARP gratuitous packet was constructed on Host M to update Host A’s ARP cache with B’s IP address mapped to M’s MAC address. The attack was tested under the same two scenarios as Task 1.B.

## Task 2: MITM Attack on Telnet using ARP Cache Poisoning
In this task, Host M intercepted the communication between Host A and Host B, who were using Telnet for communication. The following steps were performed:
- **Task 2.1**: Launched the ARP cache poisoning attack to poison Host A’s ARP cache.
- **Task 2.2**: Tested the impact of the poisoning on Telnet communication.
- **Task 2.3**: Enabled IP forwarding on Host M to forward the traffic between Hosts A and B.
- **Task 2.4**: Launched the MITM attack, intercepting and potentially modifying the Telnet communication.

## Task 3: MITM Attack on Netcat using ARP Cache Poisoning
This task was similar to Task 2, except that Hosts A and B were using **Netcat** instead of Telnet. The same steps were followed:
- Launched the ARP poisoning attack.
- Tested the impact on Netcat communication.
- Enabled IP forwarding and executed the MITM attack to intercept and modify the data sent between Hosts A and B.

## Deliverables
The following deliverables were provided for the project:
1. **Screenshots**: Attached for all tasks performed, including the setup and results of the ARP poisoning attacks.
2. **Code Snippets**: Provided for the construction of ARP packets, ARP reply, and gratuitous messages.
3. **Write-Up**: A detailed explanation of the tasks, key learnings, and challenges faced during the lab project.

---

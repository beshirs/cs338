# HoneyPot Project
> **Created by Beshir Said**
---
General Overview:
- For this project I study **honeypots** — decoy systems that attract and log attacker behavior — with a specific focus on **Cowrie**, a medium-interaction SSH/Telnet honeypot. I attempted to deploy the T-Pot multi-honeypot platform but ran into installation issues, so I used standalone Cowrie to demonstrate core honeypot capabilities. Deliverables: an informational report, reproducible demo steps, and an explantion demo video showing an attack session and the matching Cowrie logs.
---

## Refined project proposal
For my project, I will be studying Honeypots, a cybersecurity technique that involves creating fake systems to attract and monitor attackers. They act as decoy systems meant to mimic a real computer that would be a potential target for a real cyber attack and a honeypot is a way to perform proactive defending. I will be focusing on how honeypots work, the data they collect, and how one can use them to gain insight into threat activity. I will use T-pot, an all-in-one honeypot framework, that integrates multiple honeypots inside Docker containers. Since running a fully public honeypot is not practical in this setup, I plan to use simulated or pre-collected attack data to demonstrate how the Honeypots log and display intrusions. My main deliverable will be a 6–10 minute video presentation. The video layout will include:
- Introduction: 
  - What a honeypot is, its purposes,misc.
- Concept Overview:
  - Explain types of honeypots, and how honeypots are used in detection, deception and research. Also briefly mention ethical and legal considerations
- T-Pot Overview:
  - explain what T-Pot is and why it's useful. Describe its main components
- Demo Section(subject to change):
  - show T-Pot dashboard, walk through attack log entries, and possibly demonstrate a simple simulated attempt locally and its results.
- Conclusion:
  - Summarize findings and reflect on how honeypots help strengthen proactive defense.

---

## Findings: 
**What Cowrie does**
- Emulates an SSH/Telnet shell to lure attackers.
- Logs connection metadata (src IP, port), authentication attempts (user/pass), every typed command, and file transfer attempts.
- Produces textual and JSON logs (`cowrie.log`, `cowrie.json`) suitable for analysis.

--- 

**Why use Honeypots**
-
-
-
----

**Ethical Considerations**
-
-
-

----

**Environment & tools**
- Ubuntu Server (24.04 recommended)
- Cowrie (upstream GitHub)
- Kali Linux
- Optional: `docker`

---

**Security note**
Run Cowrie in an isolated lab (VM or segmented network). Do not expose sensitive data or run on production networks.

---


## How to run demo (Cowrie):

> **For easy asscessiblity, have both servers side by side**

1. On Host (Ubuntu):
   ``` bash
   $ docker run -p 2222:2222 cowrie/cowrie:latest
   $ ssh -p 2222 root@localhost
   ```
> **Aknowldegements** https://github.com/cowrie/cowrie?tab=readme-ov-file

2.  On Attacker (Kali):
   ```bash
   ssh -p 2222 root@<ip_address>
  ```
> **Assume** Cowrie listens on port `2222` at `192.168.64.3`. Adjust as needed.

3. Run some demo commands you can try:
  - whoami
  - ls -la
  - cat /etc/passwd
  - mkdir /tmp/i_am_here
  - echo "topsecret" > /tmp/fake_passwords.txt
  - wget http://example.com/somefile || true
  - exit
> **Observe the command line on Host**

---
## Credits and Acknowledegments
- Credit to these repo for easy and digestable instructions
- Cowrie Repository: https://github.com/cowrie/cowrie?tab=readme-ov-file
- T-Pot Repository: https://github.com/telekom-security/tpotce?tab=readme-ov-file
--- 



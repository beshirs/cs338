# HoneyPot Project
---
General Overview:
- For this project I study **honeypots** — decoy systems that attract and log attacker behavior — with a specific focus on **Cowrie**, a medium-interaction SSH/Telnet honeypot. I attempted to deploy the T-Pot multi-honeypot platform but ran into installation issues, so I used standalone Cowrie to demonstrate core honeypot capabilities. Deliverables: a technical report, reproducible demo steps, and a 6–10 minute demo video showing an attack session and the matching Cowrie logs.
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

## Technical summary 
**What Cowrie does**
- Emulates an SSH/Telnet shell to lure attackers.
- Logs connection metadata (src IP, port), authentication attempts (user/pass), every typed command, and file transfer attempts.
- Produces textual and JSON logs (`cowrie.log`, `cowrie.json`) suitable for analysis.

--- 

**Environment & tools**
- Ubuntu Server (24.04 recommended)
- Cowrie (upstream GitHub)
- Kali Linux (attacker VM for controlled testing)
- Helpful tools: `jq`, `tail`, `ssh`, optional `docker`

---

**Security note**
Run Cowrie in an isolated lab (VM or segmented network). Do not expose sensitive data or run on production networks.

---

## Demo plan — what to show (video friendly)
1. **Intro (30s)** — What honeypots are (analogy: *“fake storefronts with hidden cameras”*).  
2. **Architecture (30s)** — Simple diagram: Kali (attacker) → Ubuntu (Cowrie) with IPs/ports.  
3. **Live demo (2–3 min)** — SSH from Kali to Cowrie and run a scripted sequence (`whoami`, `ls`, `cat /etc/passwd`, `wget`, `exit`).  
4. **Log review (2 min)** — Tail `cowrie.json` and use `jq` to extract timestamp, src IP, username, and commands.  
5. **Config tweak (30s)** — Quick `cowrie.cfg` demo (banner or fake filesystem).  
6. **Conclusion (30–60s)** — What we captured, limitations, next steps (e.g., ELK ingestion, long-term collection).

---

## Demo instructions — copy/paste commands
> **Assume** Cowrie listens on port `2222` at `192.168.64.3`. Adjust as needed.

**On attacker (Kali)**
```bash
ssh -p 2222 root@192.168.64.3

# demo commands (type while recording)
whoami
ls -la
cat /etc/passwd
mkdir /tmp/i_am_here
echo "topsecret" > /tmp/fake_passwords.txt
wget http://example.com/somefile || true
exit



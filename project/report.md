Technical Report
---
Introduction: What is a honeypot?
- A honeypot is a decoy system designed to attract hackers and record their actions. It is an actual system meaning it looks very real but has no actual data. It helps researchers, hackers, security analysts see how these various attacks happen, what type of information the attacker was looking for without risking any real assets. 
- It is a form of proactive defending. It reveals the attackers tools and techniques used during the attack.
---

Concept Overview:
 - There are 2 main ideas behind honeypots. Deception and Detection.
 - Deception is about tricking the attackers into thinking it’s a real system while detection is learning how attacks happen and where they come from. Honeypits can be categorized by interaction level and purpose. Low-interaction honeypots  simulate only certain services or parts of a system. They’re lightweight, safer, and mostly used to collect general information about attacks. High-interaction honeypots run real operating systems or services. They give deeper insights but come with higher risk if not properly contained. By purpose, honeypots can be a production honeypot (used in real networks to detect threats early) or research honeypots(used to gather detailed data on attacker behavior).
---

T-Pot and Cowrie Overview: 
 - T-pot is an open-source honeypot platform developed by Deutsche Telekom that combines several honeypots into one system. It runs in Docker containers, making it easy to set up and manage.
 - It includes tools like Cowrie(which catches ssh login attempts and records attacker commands, Dionaea(which traps and collects malware), and a visualization stack using Elasticsearch, Logstash, and Kibana that let you see live attack data updated every minute in dashboards.
 - T-Pot is useful because it automates what would normally take hours to configure. Instead of setting up many separate honeypots, it gives you a complete environment to observe real-time attacks, where they come from, what ports they target, and what methods they use.
 - In short, T-Pot acts like a central hub that allows avid security users to visualize, study, and protect their data proactively in a convenient and efficient way 
---
Demo Process: 

---

Conclusion:
 - Ultimately, honeypots are a neat way to turn hacking attempts into learning opportunities. They not only protect systems, they teach us how attackers think. T-Pot acts as a convenient hub to make the process easier and more visual. I can definitely see myself playing with this more in the future.
---

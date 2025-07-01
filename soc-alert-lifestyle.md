📖BRUTE-FROCE ATTACK ON ACTIVE DIRECTORY: how a brute force attack is detected and how its moved forward.
🤖scenario
  A brute force attack was detected on a portal. The attacker used automated tools form a foreign IP to guess credentials.
1. Detection
   -Alert raised by SEIM :>50 failed login attempts in less than 1 min.
   -Source:Wzuh or Splunk
   -Rule triggered: Login anomalities
   
3. Triage(Tier 1 analyst)
   analyst checks for:
   -IP geolocation
   -timeline of event
   -user account targeted
   -known attacker IP list
   -correlate with other logs(VPN,DNS,firewall)
   
3.Escalation(tier 2 analyst/incident response)
  if password spraying confirmed:
    -block IP at firewall.
    -disable affected account for a while or change its password.
    -initiate incidnt response ticket for forensic analysis.
    
📖short graph showcasing alert triage:
  A[Detection: SIEM Alert] --> B[Triage: Tier 1 Analysis]  
  B --> C{Malicious?}  
  C -->|Yes| D[Escalation: Tier 2/IR]  
  C -->|No| E[Close False Positive]  

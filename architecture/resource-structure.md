# Ressourcenstruktur

## Zielarchitektur (MVP – Minimal Viable Platform)

Subscription: kmu-prod (Im Rahmen dieses Projekts wird die Subscription „kmu-prod“ konzeptionell simuliert.
Die technische Umsetzung erfolgt innerhalb einer bestehenden Azure Subscription.)

Ressourcengruppen:

- rg-kmu-prod-networking  
- rg-kmu-prod-security  
- rg-kmu-prod-shared  
- rg-kmu-prod-monitoring  

---

## Begründung der Struktur

Die gewählte Struktur orientiert sich an Best Practices für Cloud-Governance und einer klaren Trennung von Verantwortlichkeiten.

### Networking
Die Netzwerkressourcen werden in einer eigenen Ressourcengruppe isoliert, um:

- eine klare Verantwortlichkeit zu gewährleisten  
- Änderungen kontrolliert durchführen zu können  
- Netzwerkkonfigurationen zentral zu verwalten  
- Sicherheitsregeln konsistent umzusetzen  

---

### Security
Sicherheitsrelevante Komponenten (z. B. Key Vault, Richtlinien, Rollen) werden separat gruppiert, um:

- Governance-Anforderungen besser abzubilden  
- Audits und Überprüfungen zu vereinfachen  
- Zugriffsrechte gezielt zu steuern  
- sicherheitskritische Ressourcen logisch zu bündeln  

---

### Shared Services
Gemeinsam genutzte Ressourcen (z. B. Storage Accounts oder zentrale Dienste) werden in einer eigenen Ressourcengruppe organisiert, um:

- Wiederverwendbarkeit zu fördern  
- die Struktur skalierbar zu halten  
- klare Abhängigkeiten zwischen Komponenten darzustellen  

---

### Monitoring
Monitoring- und Logging-Komponenten werden separat betrieben, um:

- zentrale Diagnosedaten bereitzustellen  
- Protokollierung und Alerting konsistent umzusetzen  
- die Betriebsüberwachung klar von der Anwendungslogik zu trennen  
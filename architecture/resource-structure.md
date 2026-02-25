# Ressourcenstruktur

## Zielarchitektur (MVP – Minimal Viable Platform)

Subscription: kmu-prod (Im Rahmen dieses Projekts wird die Subscription „kmu-prod“ konzeptionell simuliert.
Die technische Umsetzung erfolgt innerhalb einer bestehenden Azure Subscription.)

- **DEV** (Entwicklung)
- **TEST** (Abnahme / Qualitätssicherung)
- **PROD** (Produktivbetrieb)

Um Kosten zu vermeiden, wird im MVP zunächst nur die **DEV-Umgebung technisch umgesetzt**.  
TEST und PROD sind **architektonisch identisch** geplant und können später 1:1 repliziert werden (z. B. per Terraform/Bicep).

---

## Resource Groups je Umgebung (Standard)
Pro Umgebung werden Resource Groups nach Verantwortungsbereichen getrennt:

### DEV
- rg-kmu-dev-networking
- rg-kmu-dev-security
- rg-kmu-dev-shared
- rg-kmu-dev-monitoring

### TEST
- rg-kmu-test-networking
- rg-kmu-test-security
- rg-kmu-test-shared
- rg-kmu-test-monitoring

### PROD
- rg-kmu-prod-networking
- rg-kmu-prod-security
- rg-kmu-prod-shared
- rg-kmu-prod-monitoring

---

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
# Governance-Konzept

## Ziel der Governance

Cloud Governance stellt sicher, dass:

- Ressourcen kontrolliert bereitgestellt werden
- Sicherheitsanforderungen eingehalten werden
- Kosten transparent bleiben
- Verantwortlichkeiten klar definiert sind
- Compliance-Anforderungen berücksichtigt werden

Im Rahmen dieses Projekts wird ein minimales, praxisnahes Governance-Modell für ein KMU umgesetzt.

---

## Rollen- und Berechtigungskonzept (RBAC)

Es werden folgende Rollen definiert:

### Cloud Administrator
- Vollzugriff auf Subscription
- Verantwortlich für Architektur und Sicherheit
- Begrenzte Anzahl an Personen

### Platform Engineer
- Contributor-Rechte auf spezifische Ressourcengruppen
- Verantwortlich für Betrieb und Wartung

### Reader / Auditor
- Leserechte
- Einsicht in Konfigurationen und Logs
- Keine Änderungsrechte

---

## Tagging-Strategie

Zur besseren Strukturierung und Kostenkontrolle werden verpflichtende Tags definiert:

- owner
- environment
- costcenter
- project

Beispiel:

owner = IT-Abteilung  
environment = prod  
costcenter = 1001  
project = landing-zone  

Tags ermöglichen eine bessere Kostenanalyse und Governance-Übersicht.

---

## Sicherheitsgrundlagen (MVP)

Folgende Sicherheitsmaßnahmen werden umgesetzt:

- Storage Accounts: Public Access deaktiviert, HTTPS-only
- Azure Key Vault: RBAC-Modell, Soft Delete aktiviert
- Diagnostic Settings: Protokollierung in Log Analytics
- Network Security Groups zur Steuerung des Netzwerkverkehrs

---

## Kostenkontrolle

Zur Vermeidung unerwarteter Ausgaben wird:

- ein Budget auf Subscription- oder Ressourcengruppenebene definiert
- eine Warnung bei 80 % und 100 % Budgetauslastung konfiguriert

Dies unterstützt eine transparente und kontrollierte Cloud-Nutzung.
# Namenskonvention

## Ziel der Namenskonvention

Eine konsistente Namenskonvention ist essenziell für:

- Übersichtlichkeit innerhalb der Azure-Umgebung
- Skalierbarkeit der Infrastruktur
- Automatisierung und Infrastructure-as-Code
- einfache Zuordnung von Ressourcen zu Projekten und Umgebungen
- professionelle Betriebsführung

Die Benennung folgt einem strukturierten Schema, das Organisation, Umgebung und Region berücksichtigt.

---

## Allgemeines Benennungsschema

<ressourcentyp>-<organisation>-<umgebung>-<region>-<laufende-nummer>

Beispiel:

rg-kmu-prod-we-001  
vnet-kmu-prod-we-001  
nsg-app-kmu-prod-we-001  
kv-kmu-prod-we-001  
law-kmu-prod-we-001  

---

## Bestandteile der Namenskonvention

### Ressourcentyp (Prefix)

| Ressource                | Prefix |
|--------------------------|--------|
| Resource Group           | rg     |
| Virtual Network          | vnet   |
| Subnet                   | snet   |
| Network Security Group   | nsg    |
| Key Vault                | kv     |
| Log Analytics Workspace  | law    |
| Storage Account          | st     |

---

### Organisation

kmu = simuliertes Small-to-Medium Enterprise

---

### Umgebung (Environment)

- dev = Entwicklungsumgebung
- test = Testumgebung
- prod = Produktionsumgebung

Im Rahmen dieses Projekts wird primär die Umgebung „prod“ simuliert.

---

### Region

we = westeurope

---

### Laufende Nummer

001, 002, 003 …

Dient zur Unterscheidung mehrerer Ressourcen desselben Typs.

---

## Besonderheit: Storage Accounts

Storage Accounts unterliegen Azure-Namensregeln:

- keine Bindestriche
- nur Kleinbuchstaben
- maximal 24 Zeichen

Beispiel:

stkmuprodwe001
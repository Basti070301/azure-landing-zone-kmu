# Namenskonvention

## Ziel der Namenskonvention

Eine konsistente Namenskonvention ist essenziell für:

- Übersichtlichkeit innerhalb der Azure-Umgebung
- Skalierbarkeit der Infrastruktur
- Automatisierung und Infrastructure-as-a-Code
- einfache Zuordnung von Ressourcen zu Projekten und Umgebungen
- professionelle Betriebsführung

Die Benennung folgt einem strukturierten Schema, das Organisation, Umgebung und Region berücksichtigt.

---

## Allgemeines Benennungsschema

Ressourcengruppe:
<rg>-<organisation>-<umgebung>-<scope>

Beispiel:
rg-kmu-prod-networking

Ressourcen
<ressourcentyp>-<organisation>-<umgebung>-<region>-<laufende-nummer>

Beispiel:
vnet-kmu-prod-gwc-001

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

### Regionen

weu = West Europe
gwc = Germany West Central

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
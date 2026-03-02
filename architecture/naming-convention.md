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

# Storage Accounts

Storage Accounts unterliegen Azure-Namensregeln:

- keine Bindestriche
- nur Kleinbuchstaben
- maximal 24 Zeichen

Beispiel:

stkmuprodwe001

## Besonderheit: Netzwerkgruppen (Sicherheitsregeln)
<action>-<source>-<to>-<destination>

Beispiel:
allow-app-to-data



# Namenskonvention für Microsoft Entra Gruppen

## Ziel

- klare und schnelle Zuordnung von Berechtigungen (RBAC)
- bessere Übersichtlichkeit in Microsoft Entra ID und Azure
- Skalierbarkeit (mehrere Umgebungen/Teams/Scopes)
- Automatisierung (z. B. IaC / Terraform / Pipelines)
- professionelle Governance innerhalb einer Landing Zone

Die Gruppen werden primär für **Azure RBAC** genutzt (Zugriffssteuerung auf Subscription/Resource Groups/Ressourcen).

---

## Allgemeines Benennungsschema

**Schema:**

`grp-<plattform>-<organisation>-<umgebung>-<scope>-<rolle>`

**Beispiele:**

- `grp-az-kmu-dev-networking-contributor`
- `grp-az-kmu-dev-networking-reader`

## Standardisierte Gruppenbeschreibung

Um Gruppen in Microsoft Entra ID langfristig wartbar zu halten, sollte jede Gruppe eine **einheitliche Beschreibung** erhalten.  
Dadurch wird sofort klar:

- wofür die Gruppe gedacht ist (Zweck / Scope)
- für welche Umgebung sie gilt (dev/test/prod)
- wo die Berechtigung zugewiesen ist (z. B. Resource Group / Subscription)
- dass Berechtigungen **über Gruppen** und nicht über einzelne Benutzer gesteuert werden sollen

### Beschreibungsvorlage (Template)

**Template:**

`Azure RBAC-Gruppe für <Scope> in <Umgebung>. Rolle: <Rolle>. Zuweisung auf <Ziel-Scope>.`

### Beispiele

- `Azure RBAC-Gruppe für Networking in dev. Rolle: Network Contributor. Zuweisung auf rg-kmu-dev-networking.`
- `Azure RBAC-Gruppe für Networking in dev. Rolle: Reader. Zuweisung auf rg-kmu-dev-networking.`
- `Azure RBAC-Gruppe für Platform in prod. Rolle: Contributor. Zuweisung auf Subscription azure-landing-zone-kmu.`

### Hinweis

Berechtigungen sollten **nicht direkt an Benutzer**, sondern ausschließlich an **Gruppen** vergeben werden, um Governance und Nachvollziehbarkeit sicherzustellen.

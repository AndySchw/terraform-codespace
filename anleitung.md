# GitHub Codespaces für Terraform Workshop 🚀

Eine einfache Anleitung, wie du GitHub Codespaces für Terraform-Workshops nutzt und dabei allen Teilnehmern eine identische, sofort einsatzbereite Entwicklungsumgebung bereitstellst.

## Überblick

Mit GitHub Codespaces können alle Workshop-Teilnehmer mit nur einem Klick eine vollständige Terraform-Entwicklungsumgebung in der Cloud starten - ohne lokale Installation!

---

## Als Workshop-Leiter: Repository vorbereiten

### Schritt 1: Öffentliches Repository erstellen

1. Gehe zu [GitHub](https://github.com) und erstelle ein neues Repository
2. Wähle **"Public"** wenn du es mit anderen teilen möchtest
3. Repository-Name z.B. `terraform-workshop` oder `terraform-basics`

### Schritt 2: devcontainer.json erstellen

Erstelle diese Dateistruktur in deinem Repository:

```
dein-repo/
├── .devcontainer/
│   └── devcontainer.json    ← Diese Datei ist WICHTIG!
├── main.tf                  ← Dein Terraform-Code (optional)
├── variables.tf             ← Terraform-Variablen (optional)
└── README.md                ← Workshop-Anleitung (optional)
```

### Schritt 3: devcontainer.json Inhalt

Füge diesen Code in die Datei `.devcontainer/devcontainer.json` ein:

```json
{
  "name": "Terraform Workshop",
  "image": "mcr.microsoft.com/devcontainers/base:ubuntu",
  "features": {
    "ghcr.io/devcontainers/features/terraform:1": {
      "version": "latest"
    },
    "ghcr.io/devcontainers/features/azure-cli:1": {}
  },
  "customizations": {
    "vscode": {
      "extensions": [
        "hashicorp.terraform"
      ]
    }
  },
  "postCreateCommand": "terraform --version"
}
```

**Diese Konfiguration sorgt dafür, dass beim Start des Codespaces automatisch installiert wird:**
- ✅ Terraform (neueste Version)
- ✅ Azure CLI
- ✅ HashiCorp Terraform VS Code Extension

### Schritt 4: Zusätzliche Dateien hinzufügen (optional)

Du kannst alle weiteren Dateien mit ins Repository legen, die die Teilnehmer nutzen sollen:

```
dein-repo/
├── .devcontainer/
│   └── devcontainer.json
├── terraform/
│   ├── main.tf              ← Vorgefertigte Terraform-Konfiguration
│   ├── variables.tf         ← Variablen-Definitionen
│   └── terraform.tfvars.example ← Beispiel-Konfiguration
├── modules/                 ← Terraform-Module
│   └── networking/
├── examples/                ← Code-Beispiele
│   ├── basic/
│   └── advanced/
├── docs/                    ← Workshop-Dokumentation
│   └── aufgaben.md
└── README.md               ← Haupt-Anleitung
```

### Schritt 5: Repository-Link teilen

Teile den Link zu deinem Repository:
```
https://github.com/DEIN-USERNAME/terraform-workshop
```

---

## Für Teilnehmer: Codespace starten

### Schritt 1: Repository klonen/forken

**Option A: Fork erstellen (empfohlen)**
1. Gehe zum geteilten Repository-Link
2. Klicke auf **"Fork"** (oben rechts)
3. Erstelle den Fork in deinem eigenen GitHub-Account

**Option B: Als Template nutzen**
1. Gehe zum Repository
2. Klicke auf **"Use this template"** → **"Create a new repository"**
3. Erstelle ein neues Repository in deinem Account

### Schritt 2: Codespace starten

1. Gehe zu **deinem** Repository (Fork/Template)
2. Klicke auf **"Code"** (grüner Button)
3. Wähle Tab **"Codespaces"**
4. Klicke auf **"Create codespace on main"**

### Schritt 3: Warten und loslegen

- ⏳ **Warte 2-3 Minuten** während der Codespace eingerichtet wird
- 🔧 Terraform wird automatisch installiert
- 🎯 VS Code öffnet sich mit allen Extensions
- ✅ **Fertig!** Du kannst sofort mit Terraform arbeiten

### Schritt 4: Terraform testen

Öffne das Terminal in VS Code (`Strg + Shift + \``) und teste:

```bash
# Terraform-Version prüfen
terraform --version

# Azure CLI testen
az --version

# Terraform initialisieren (falls .tf Dateien vorhanden)
terraform init

# Terraform-Plan anzeigen
terraform plan
```

---

## Vorteile dieser Methode

### Für Workshop-Leiter
- ✅ **Keine Installationsprobleme** bei Teilnehmern
- ✅ **Identische Umgebung** für alle
- ✅ **Einfache Vorbereitung** - alles in einem Repository
- ✅ **Schneller Workshop-Start** - keine Setup-Zeit
- ✅ **Vorgefertigte Inhalte** können direkt mitgeliefert werden

### Für Teilnehmer
- ✅ **Ein Klick** und fertig eingerichtete Umgebung
- ✅ **Kein lokales Setup** erforderlich
- ✅ **Funktioniert überall** wo ein Browser ist
- ✅ **Kostenlos** für öffentliche Repositories
- ✅ **Eigener Arbeitsbereich** - keine Konflikte mit anderen

---

## Häufige Fragen (FAQ)

### ❓ Können mehrere Teilnehmer denselben Codespace nutzen?
**Nein.** Jeder Teilnehmer bekommt seinen eigenen Codespace. Das ist auch besser so, da jeder unabhängig arbeiten kann.

### ❓ Was kostet GitHub Codespaces?
Für **öffentliche Repositories** ist es kostenlos (monatliches Kontingent). Für private Repos fallen nach dem Freikontigent Kosten an.

### ❓ Wie lange dauert der Codespace-Start?
**2-3 Minuten** beim ersten Start. Danach geht es schneller, da die Images gecacht sind.

### ❓ Was passiert, wenn ich den Codespace schließe?
Der Codespace wird pausiert und kann später fortgesetzt werden. Alle Dateien bleiben erhalten.

### ❓ Kann ich auch andere Cloud-Provider nutzen?
Ja! Ergänze einfach weitere Features in der devcontainer.json:
```json
"features": {
  "ghcr.io/devcontainers/features/terraform:1": {},
  "ghcr.io/devcontainers/features/aws-cli:1": {},
  "ghcr.io/devcontainers/features/gcloud:1": {}
}
```

---

## Troubleshooting

### Problem: Terraform nicht gefunden
**Lösung:** Überprüfe, ob die `.devcontainer/devcontainer.json` korrekt erstellt wurde und das Repository neu geladen.

### Problem: Codespace startet nicht
**Lösung:** Überprüfe die JSON-Syntax in der devcontainer.json mit einem JSON-Validator.

### Problem: Extensions fehlen
**Lösung:** Stelle sicher, dass die `customizations` Sektion in der devcontainer.json korrekt ist.

---

## Fazit

GitHub Codespaces mit einer richtig konfigurierten `devcontainer.json` macht Terraform-Workshops super einfach:

1. **Du:** Repository mit devcontainer.json erst
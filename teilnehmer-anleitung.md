# Workshop-Teilnehmer Anleitung 🎯

Du hast einen Link zu einem Terraform-Workshop bekommen? Hier ist die Schritt-für-Schritt-Anleitung, wie du in wenigen Minuten deine eigene Terraform-Entwicklungsumgebung bekommst!

---

## Was du brauchst

- ✅ **GitHub-Account** (kostenlos auf [github.com](https://github.com))
- ✅ **Webbrowser** (Chrome, Firefox, Safari, Edge)
- ✅ **Den Workshop-Link** vom Dozenten

**Das war's!** Keine lokale Installation erforderlich! 🚀

---

## Schritt 1: Repository zu deinem GitHub hinzufügen

Du hast einen Link vom Dozenten bekommen, z.B.:
```
https://github.com/dozent-name/terraform-workshop
```

### Option A: Fork erstellen (Empfohlen)

1. **Öffne den Link** vom Dozenten in deinem Browser
2. **Logge dich bei GitHub ein** (falls noch nicht eingeloggt)
3. **Klicke auf "Fork"** (oben rechts auf der Seite)

   ![Fork Button](https://docs.github.com/assets/cb-28613/images/help/repository/fork_button.png)

4. **Wähle dein GitHub-Account** als Ziel
5. **Klicke "Create fork"**

✅ **Fertig!** Du hast jetzt eine eigene Kopie des Workshop-Repositories.

### Option B: Als Template nutzen (Alternative)

1. **Öffne den Link** vom Dozenten
2. **Klicke auf "Use this template"** → **"Create a new repository"**
3. **Gib einen Namen ein**, z.B. `mein-terraform-workshop`
4. **Klicke "Create repository from template"**

---

## Schritt 2: Codespace starten

Jetzt hast du das Repository in deinem GitHub-Account. So startest du deine Entwicklungsumgebung:

### 2.1 Zu deinem Repository navigieren

- Gehe zu **deinem** GitHub-Profil
- Klicke auf das Repository (z.B. `terraform-workshop` oder wie du es benannt hast)

### 2.2 Codespace erstellen

1. **Klicke auf den grünen "Code" Button**

   ![Code Button](https://docs.github.com/assets/cb-33207/images/help/codespaces/codespaces-button.png)

2. **Wähle den Tab "Codespaces"** (nicht "Local")

3. **Klicke "Create codespace on main"**

   ![Create Codespace](https://docs.github.com/assets/cb-77061/images/help/codespaces/create-codespace-button.png)

### 2.3 Warten und entspannen ☕

- ⏳ **Warte 2-4 Minuten** während deine Umgebung eingerichtet wird
- Du siehst einen Ladebildschirm mit Fortschrittsanzeige
- **Terraform wird automatisch installiert!**
- VS Code öffnet sich automatisch im Browser

---

## Schritt 3: Testen ob alles funktioniert

Wenn VS Code geladen ist:

### 3.1 Terminal öffnen

- **Tastenkombination:** `Strg + Shift + \`` (Windows/Linux) oder `Cmd + Shift + \`` (Mac)
- **Oder über Menü:** "Terminal" → "New Terminal"

### 3.2 Terraform testen

Gib diese Befehle ins Terminal ein:

```bash
# Terraform-Version prüfen
terraform --version
```

Du solltest etwas sehen wie:
```
Terraform v1.6.6
```

```bash
# Azure CLI testen (falls im Workshop verwendet)
az --version
```

✅ **Perfekt!** Wenn du die Versionsangaben siehst, ist alles bereit!

---

## Schritt 4: Mit Terraform arbeiten

### Wenn Terraform-Dateien bereits im Repository sind:

```bash
# Terraform initialisieren
terraform init

# Plan anzeigen (was würde passieren?)
terraform plan

# Ressourcen erstellen (nur wenn gewünscht)
terraform apply
```

### Wenn du selbst Terraform-Code schreiben sollst:

1. **Erstelle neue Datei:** Klicke auf das Datei-Symbol im Explorer (links)
2. **Benenne sie:** z.B. `main.tf`
3. **Schreibe deinen Code** oder kopiere Beispiele vom Dozenten
4. **Speichern:** `Strg + S`

---

## Wichtige Tipps für den Workshop

### 💡 Dein eigener Arbeitsplatz
- Jeder hat **seinen eigenen Codespace** - du störst niemanden!
- Du kannst **experimentieren** ohne Angst etwas zu "kaputt" zu machen
- **Alle Änderungen bleiben erhalten**, auch wenn du den Browser schließt

### 💡 Dateien speichern
- **Auto-Save ist an** - Dateien werden automatisch gespeichert
- Du kannst aber auch `Strg + S` drücken

### 💡 Codespace pausieren/fortsetzen
- **Browser schließen:** Codespace wird pausiert
- **Später weiterarbeiten:** Gehe zu github.com → dein Repository → "Code" → bestehenden Codespace wählen

### 💡 Bei Problemen
- **Terminal neu starten:** `Strg + Shift + P` → "Terminal: Kill All Terminals"
- **Codespace neu starten:** GitHub → Repository → Codespace → "..." → "Restart"

---

## Häufige Fragen

### ❓ Kostet mich das etwas?
**Nein!** Für öffentliche Repositories ist GitHub Codespaces kostenlos (bis zu einem monatlichen Limit, das für Workshops mehr als ausreicht).

### ❓ Was passiert mit meinen Dateien?
Alle Dateien bleiben in **deinem** Repository gespeichert. Du verlierst nichts!

### ❓ Kann ich auch lokal arbeiten?
Ja! Du kannst das Repository auch klonen und lokal mit VS Code arbeiten. Aber Codespaces ist einfacher für den Workshop.

### ❓ Wie teile ich meine Ergebnisse?
Du kannst:
- **Screenshots** machen und teilen
- **Code** kopieren und in Chat/Email einfügen
- **Repository-Link** teilen (dein Fork/Template)

### ❓ Der Codespace lädt nicht / Fehler beim Start
1. **Warte noch 1-2 Minuten** - manchmal dauert es länger
2. **Aktualisiere die Seite** (F5)
3. **Probiere einen anderen Browser**
4. **Frage den Dozenten** - er kann helfen!

---

## Checkliste: Bist du bereit? ✅

- [ ] GitHub-Account vorhanden
- [ ] Repository geforkt/als Template erstellt
- [ ] Codespace gestartet
- [ ] VS Code läuft im Browser
- [ ] Terminal ist offen
- [ ] `terraform --version` funktioniert
- [ ] Bereit für den Workshop!

---

## Bei Problemen

**Keine Panik!** 😊 

1. **Aktualisiere die Seite** (F5)
2. **Warte noch 1-2 Minuten**
3. **Probiere es nochmal**
4. **Frage den Dozenten oder andere Teilnehmer**

Der Dozent hat diese Umgebung extra so eingerichtet, dass es für alle funktioniert!

---

## Viel Erfolg! 🎉

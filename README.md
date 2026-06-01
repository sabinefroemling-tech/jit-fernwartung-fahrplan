# JIT-Fernwartungs-Fahrplan · Just-in-Time-Fernwartung nach dem Vier-Stufen-Modell

Ein leichtgewichtiges, browserbasiertes Werkzeug, das aus wenigen Angaben einen individuellen Fahrplan zur Absicherung der OT-Fernwartung erzeugt — als Begleitmaterial zum Fachbuch **„ISMS für die Industrie. Von ISO 27001 über NIS2 bis OT-Security“**.

Es ist das vierte Werkzeug der Companion-Reihe, neben der [Crown-Jewels-Identifikation](https://sabinefroemling-tech.github.io/crown-jewels-companion/), dem [No-Touch-Register](https://sabinefroemling-tech.github.io/no-touch-register/) und dem [OT-Reifegrad-Profil](https://sabinefroemling-tech.github.io/ot-reifegrad-profil/). Fernwartung ist der häufigste Eintrittsvektor in der OT; dieses Werkzeug macht das Vier-Stufen-Modell aus Kapitel 22.2 unmittelbar umsetzbar.

## Was es macht

Der Anwender beantwortet eine kurze Bestandsaufnahme zum Werk (Register, Zugangsverwaltung, dauerhafte OEM-Tunnel, zentrales Gateway, MFA, Session-Recording, Personenkonstellation). Daraus erzeugt das Werkzeug einen personalisierten Fahrplan entlang der vier Stufen, jeweils mit Statusampel (erreicht / teilweise / offen) und einem auf die konkreten Antworten zugeschnittenen Hinweis auf die nächste Lücke:

1. **Stufe 1 — Inventar:** alle Fernwartungszugänge im Register erfassen, jeweils mit eindeutiger ID und benanntem internen Owner. Mitgeliefert als Tabelle und als CSV-Vorlage.
2. **Stufe 2 — Deaktivierung im Ruhezustand (Just-in-Time):** Zugänge standardmäßig deaktiviert, Aktivierung nur auf zeitlich begrenzten Antrag, automatische Deaktivierung nach Auftragsende. Mitgeliefert als Einführungs-Checkliste.
3. **Stufe 3 — Single-Channel-Prinzip:** nur ein genehmigter Weg über das zentrale, protokollierte Gateway, keine Schatten-Tools. Mitgeliefert als Richtlinien-Formulierung.
4. **Stufe 4 — Session-Recording:** vollständige Aufzeichnung, Aufbewahrung mindestens 90 Tage, Zugriff nur durch das OT-Security-Team. Mitgeliefert als Muster einer Betriebsvereinbarung.

Die Voraussetzungen aus Kap. 22.2 (zentrales Gateway mit MFA, Genehmigungs-Workflow, Recording-Infrastruktur, Schulung der externen Dienstleister) und die Audit-Nachweise mit ISO- und IT-Grundschutz-Bezug (5.19, 8.5, 8.16; IND.3.2) sind im Fahrplan hinterlegt.

### Der rechtliche Kern (Alleinstellungsmerkmal)

Session-Recording berührt deutsches Mitbestimmungs- und Datenschutzrecht. Das Werkzeug bildet die korrekte Reihenfolge aus Kap. 22.2 ab und gibt das Betriebsvereinbarungs-Muster nicht blind aus, sondern abhängig von der Personenkonstellation:

- **Rein externe OEM-Wartung** — keine Betriebsvereinbarung erforderlich (kein Mitbestimmungstatbestand nach §87 Abs. 1 Nr. 6 BetrVG); erforderlich bleiben Auftragsverarbeitungsvertrag und Eintrag ins Verarbeitungsverzeichnis.
- **Gemischt: extern + internes Personal** — Betriebsvereinbarung erforderlich, zusätzlich Auftragsverarbeitungsvertrag und Verarbeitungsverzeichnis.
- **Unklar** — zuerst die personenbezogenen Datenströme klären; das ist der häufigste Fehler, vor dem das Buch warnt.

Die korrekte Reihenfolge lautet: (1) Datenströme klären → (2) Aufnahme ins Verarbeitungsverzeichnis (Kap. 26.6) → (3) Betriebsvereinbarung, sofern interne Mitarbeiter erfasst werden → (4) Auftragsverarbeitungsvertrag mit den externen Dienstleistern.

## Nutzung

Es ist keine Installation nötig. Die Datei `index.html` im Browser öffnen — oder die gehostete Version aufrufen. Alle Daten bleiben ausschließlich im Browser; es findet keine Datenübertragung statt (DSGVO-freundlich), und es wird nichts still gespeichert.

- **Bestandsaufnahme** — Werk, Datum und die sieben Fragen ausfüllen; der Fahrplan aktualisiert sich sofort.
- **Speichern / Laden (JSON)** — der Stand wird als Datei abgelegt und wieder eingelesen.
- **Register-Vorlage (CSV)** — das Fernwartungsregister als Startdatei.
- **Drucken / PDF** — der vollständige Fahrplan inklusive aller Vorlagen, personalisiert mit Werk und Datum.

## Grenzen

Die Vorlagen sind Formulierungshilfen, keine Rechtsberatung. Betriebsvereinbarung und Auftragsverarbeitungsvertrag sind vor Verwendung durch Recht, Datenschutz und Betriebsrat zu prüfen und an die konkrete Konstellation anzupassen.

Die Statusbewertung ist regelbasiert und grob: Sie bildet das Vier-Stufen-Modell ab, ersetzt aber keine Ist-Aufnahme vor Ort. Das Werkzeug strukturiert das Vorgehen und das Gespräch mit OT-Leitung, Dienstleistern und Betriebsrat — es ersetzt weder die juristische Prüfung noch eine vollständige Erhebung der Fernwartungslandschaft.

## Lizenz

© Sabine Frömling. Veröffentlicht unter [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.de) — Namensnennung, nicht-kommerziell, keine Bearbeitungen. Details in [`LICENSE`](LICENSE).

## Autorin

**Sabine Frömling** — Unabhängige IT-Security- und Compliance-Beraterin (OT-Security, NIS2, ISO 27001, KRITIS).
[LinkedIn](https://www.linkedin.com/in/sabine-froemiing/)

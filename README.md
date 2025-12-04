## 1. Wohnheim
Text Text Text

### 1.1. Wer sind wir
Text Text Text

#### 1.1.1. Vorstellung
Text Text Text

#### 1.1.2. Mentoren Bilder
Text Text Text

#### 1.1.3. weitere Info
Text Text Text

### 1.2. Checkliste 
Text Text Text

#### 1.2.1. Regeln 
22 Uhr totenstille
6 Uhr uhr darfst du wieder leben
Waschraum 2.1
Mülltrennung 2.2
Bedienung Waschmaschine und Trockner 2.3
	Linke Maschine eigenes 30 Seiten Manual 2.3.1

#### 1.2.2. 
Text Text Text

#### 1.2.3.
Text Text Text

### 1.3. Lageplan und Standort HWR Wohnheim


#### 1.3.1. Anreise Bus/Bahn
Auf dem Hügel A
Auf dem Hügel B
Erich-Hofmann-Straße
Frongasse
Brahmsstraße
Mgdalenenplatzbe
Pastoratsgasse

# Ersti-Heft_26

Das ist das Repo der Fachschaft Informatik für das Ersti-Heft hier liegen alle Materialeien und Unterlagen, die man für das erstellen eine Heftes in Latex braucht. 
Hier ist die vollständige `README.md` als **Markdown** 

---

# 🎓 Ersti-Heft – Fachschaft Informatik (FB02, H-BRS)

> **Internes Repository.** Dieses Repo ist nur für die Fachschaft Informatik gedacht.
> Der Quellcode (LaTeX) ist unter MIT lizenziert; **Texte, Bilder und Logos** sind urheberrechtlich geschützt und nicht zur externen Nutzung freigegeben.

Das Repo enthält alle Materialien, LaTeX-Dateien, Konfigurationen und Ressourcen zur Erstellung des jährlich erscheinenden **Ersti-Hefts**.

---

## 🗂️ Projektstruktur

```
begruessung/          Einleitung & Begrüßungstexte
config/               Zentrale Konfigurationen (config.tex, footer_header.tex, commands.tex, jokes.tex)
content/              Hauptinhalte (pages/, photos/ …)
Druck/                Druckrelevantes (Hinweise, Profile, Layout)
Ersti-Heft Ressourcen/ Sammelordner offizieller Materialien/Seiten
other_content/        Statische Zusatzseiten (z. B. Impressum, Legende)
PDFs/                 Fertige PDFs (Cover/Backcover m. & o. Druckrand; einzubindende PDFs)
QRcodes/              QR-Codes in diversen Formaten (A4, Banner, Sticker, Screen)
umschlag/             Temporär: cover.tex / rückseite.tex (bindet PDF-Cover ein)
.gitignore            LaTeX-typische Ausschlüsse – nötige PDFs ggf. explizit whitelisten
main.tex              Zentrales Dokument, das alles einbindet
```

* **Hauptarbeit** findet in `content/pages/` (Artikel) und `content/photos/` (Bilder/Logos) statt.
* **Witze** für die Fußzeile liegen in `config/jokes.tex`.

---

## 🧩 LaTeX & Build

* Empfohlenes TeX: **aktuelles TeX Live** (Windows, Linux, macOS).
* Editieren geht auch mobil mit geeigneten Apps.

### Latex Kompiling und Ghostscript  

Das LaTeX-Dokument generiert die Druckversion der Ersti-Info-Vorlage.
Um die digitale Variante der Ersti-Info-Vorlage zu erstellen, empfiehlt es sich, die folgenden Befehle in einem Linux-Terminal auszuführen:
```bash
gs -o cropped.pdf -sDEVICE=pdfwrite -dAutoRotatePages=/None -c "[/CropBox [8.5 8.5 428 603.7]" -c " /PAGES pdfmark" -f main.pdf
```
```bash
gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/prepress -dEmbedAllFonts=true -dAutoRotatePages=/None -dNOPAUSE -dQUIET -dBATCH -sOutputFile=Ersti-Heft25.pdf cropped.pdf
```

Der als gestrichelte Linie angezeigte Rahmen dient als Orientierung, wo im Druck die Seiten ungefähr abgeschnitten werden.
Dieser lässt sich ausblenden, in dem man in der `commands.tex` die zweite Definition des Druckrands entkommentiert.


> Es existiert bereits ein Abschnitt zu **LaTeX-Build** und **Ghostscript** (kein weiterer Input nötig).

### Layout/Packages (Auszug)

Die wichtigsten Einstellungen und Pakete liegen zentral in `config/config.tex`:

* **KOMA-Script** (z. B. `\KOMAoptions{…}`), Seitenlayout via `geometry` (A5-Heft, Beschnitt/Offsets)
* Typografie: `FiraSans`, `microtype`, `ragged2e`, `csquotes`
* Struktur: `enumitem`, `tabularx`, `tabularray`, `multicol`, `tikz`, `pdfpages`
* Farben (`xcolor`) mit Projektfarben: `fscolor`, `petrol`, `lecegreen`
* Medien/QR: `graphicx`, `qrcode`, `adjustbox`
* Kopf/Fuß: `scrlayer-fancyhdr`
* URLs/Links: `hyperref` (mit sauberem Zeilenumbruch über `\PassOptionsToPackage{hyphens}{url}`)
* Platzhalter: `lipsum`
* Diverse Helfer: `array`, `etoolbox`, `forloop`, …

> **Hinweis:** `.gitignore` ignoriert generierte LaTeX-Artefakte. **Benötigte PDFs** (z. B. Cover) müssen bewusst eingecheckt werden.

---

## 🖋️ Druck

* Alles druckrelevante liegt in **`Druck/`** (inkl. Hinweise, ggf. ICC-Profile).
* Leerseiten für Doppelseiten/Platzhalter:

  ```tex
  \clearpage
  \thispagestyle{empty}
  \null
  \clearpage
  ```

---

## 🧠 Inhalte & Philosophie

Ziele des Ersti-Hefts:

* Orientierung auf dem Campus & im Studienalltag (LEA, MIA, EVA, APOLLO, OWA, VPN/WLAN, Bibliothek, Beratungsstellen, Gruppen, …)
* Karten, Pläne, QR-Codes zu Services/Anlaufstellen
* Beiträge der Fachschaft – **ohne Werbung** (dauerhaft werbefrei)
* Humor (Fußzeilen-Witze via `jokes.tex`)

---

## 🧭 Planung & Gantt Diagramm Workflow 2026
![Ersti-Heft_Workflow_2026](https://github.com/Hbrs-fs-inf/Erstie-Info-Heft/blob/main/Ersti-Heft_Workflow_2026.png?raw=true)


---

## 🧰 Systeme

| Plattform | Unterstützung                    |
| --------- | -------------------------------- |
| Windows   | ✅ (TeX Live)                     |
| Linux     | ✅ (TeX Live; apt/pacman)         |
| macOS     | ✅                                |
| Mobile    | ⚙️ mit LaTeX-Editor-Apps möglich |

---

## 🪪 Lizenz

* **Code (LaTeX-Struktur, Makros, Layout):** MIT
* **Inhalte (Texte, Bilder, Logos):** **Urheberrechtlich geschützt** – **nur intern** für die Fachschaft Informatik H-BRS.

---

## 🤝 Mitwirken (intern)

* Beiträge/Korrekturen via **Branches** / **Pull Requests** durch Fachschaftsmitglieder.
* Kontakt Redaktion: `redaktion.fs-inf@h-brs.de`
* Interner Login-Hinweis: `rdt.fs-inf`

---

## 🔗 Nützliche Links

* Fachschaft Informatik: [https://www.h-brs.de/inf/fachschaft](https://www.h-brs.de/inf/fachschaft)
* Hochschule Bonn-Rhein-Sieg: [https://www.h-brs.de](https://www.h-brs.de)

---

> „Die Fachschaft wird niemals Werbung in und um das Heft packen und wird versuchen, dieses dauerhaft **werbefrei** zu halten.“

---

## Info Material
[Ersti-Info23.pdf der Uni Münster](https://www.uni-muenster.de/FSMI/downloads/page/1028/Ersti-Info23.pdf)

[Ersti-Info22.pdf der Uni Münster](https://www.uni-muenster.de/FSMI/downloads/page/847/Ersti-Info22.pdf)

Ideen und Notizen im Markdown ![Ideen_Notizen.md]





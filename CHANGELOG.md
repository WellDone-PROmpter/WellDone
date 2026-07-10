# Versionsverlauf — WellDone!

Neueste Version oben. Aktuelle Releases & Download: https://welldone-prompter.github.io/WellDone/

**Version 10.9** (Juli 2026)
- **Kontrollen mit LCAP-Namen (behebt die Kontroll-Erkennung am LightCycler PRO):** Im Assay lässt sich jetzt je Kontrolle der **Name aus dem LCAP** hinterlegen (z. B. Positivkontrolle „PosK", Negativkontrolle „negK"). WellDone! schreibt diesen Namen als **Sample-ID** in den LC-PRO-Export – so erkennt der LightCycler PRO die Kontrolle und übernimmt sie korrekt. (Bisher stand dort der Rollen-Code „PTC"/„NTC"; hieß die Kontrolle im LCAP anders, wurde sie vom PRO **nicht** übernommen.)
- **Assay aus einem LightCycler-PRO-Lauf einlesen (neu):** Im Assay-Dialog liest **📥 Aus LightCycler-PRO-Lauf einlesen…** den **Customer-Export** (ZIP/XML) eines echten Laufs und füllt automatisch **Assay-Name, PCR-Profil und die Kontrollen** (Typ + LCAP-Name, z. B. PTC „PosK" / NTC „negK") – so passt das Assay-Menü exakt zum programmierten LCAP, ganz ohne Abtippen. Der Lauf muss zum **Plattenformat** (96/384) des Assays passen; ein Lauf im falschen Format wird abgelehnt (LCAPs sind 96/384-spezifisch).

**Version 10.8** (Juli 2026)
- **Export für den LightCycler 96 (neu):** Über **📤 Setup LC** lässt sich die Plattenbelegung jetzt auch für den **LightCycler 96** speichern (Dateityp im Speichern-Dialog wählen). WellDone! schreibt eine **MagNA-Pure-96-Sample-Data-Datei** (tab-getrennt) mit Position, Probenname und dem **Assay** (Spalte „Sample Note"). In der LC96-Software über **Sample Editor → Table View → Rechtsklick → „Import MP96 Sample List"** einlesen – **ohne Dye/Detektionsformat** (das kennt der LC96 an dieser Stelle nicht; Probentyp, Farbe und Farbstoffe/Gene stellst du wie gewohnt am Gerät ein). Es werden **alle 96 Positionen** geschrieben, damit leere Wells leer bleiben statt „Sample 2/3/…".

**Version 10.7** (Juli 2026)
- **Export für den LightCycler 480 (neu):** Über **📤 Setup LC** lässt sich die Plattenbelegung jetzt auch für den **LightCycler 480** speichern (Dateityp im Speichern-Dialog wählen; Ordner + zuletzt gewählter Dateityp werden gemerkt). WellDone! schreibt die **Sample-Editor-Importdatei** (tab-getrennt) mit Position, Probenname, **Assay** (Spalte „Sample Note"), Probentyp (Unknown/Standard/Positiv-/Negativ-Kontrolle) und der **Assay-Farbe** – so gruppiert der LC480 die Platte nach Assay. In der LC480-Software über **Sample Editor → Import** einlesen. Der LC480 kennt keine LCAPs; Detektionsformat/Programm und die Kanäle wählst du wie gewohnt am Gerät.

**Version 10.6** (Juli 2026)
- **MagNA Pure 24 wird unterstützt:** Der Proben-Import liest jetzt auch die **Ergebnis-XML der MagNA Pure 24** – dasselbe pro-Lauf-Format wie bei der MagNA Pure 96 (die 24 Proben liegen in 8er-Streifen, Positionen A1–H3, und landen genau dort auf der Proben-Platte). Der Datumsbereich-Export „MP24SampleResults…csv" mit mehreren Läufen wird (noch) nicht unterstützt – bitte die einzelne Lauf-XML nehmen. Platzhalter „n/a" in leeren Feldern werden nicht mehr in „Quellplatte-ID"/Prep-Notes übernommen.

**Version 10.5** (Juni 2026)
- **Schwester-App verlinkt:** Der **„❓"-Dialog (Über / Hilfe)** verweist jetzt direkt auf **PROmpter** – die Schwester-App für die **Auswertung nach dem Lauf** (PDF-Bericht & Excel). *WellDone! = Vorbereitung, PROmpter = Auswertung.*
- **Handbuch aktualisiert:** Marken-Hinweis ergänzt („Roche, LightCycler und MagNA Pure sind Marken der jeweiligen Inhaber") und WellDone! als **unabhängiges, privates Projekt** klargestellt (nicht von Roche geprüft oder verantwortet).

**Version 10.4** (Juni 2026)
- **Englisches Handbuch (neu):** Das Handbuch liegt jetzt auch auf **Englisch** vor und öffnet automatisch in der gewählten Sprache (deutsche Oberfläche → deutsches Handbuch, englische Oberfläche → englisches Handbuch).
- **Einheitliche Farben im Pipettierschema:** Die **MasterMix-Tabelle** nutzt jetzt dieselben Farben wie die **Plattenbelegung** – die „gesamt"-Spalte in der **vollen Assay-Farbe** der Proben-Wells, die „je 1 Rkt"-Spalte im **aufgehellten NTC-Ton** (Schrift automatisch hell/dunkel für gute Lesbarkeit). So lassen sich Tabelle und Platte auf einen Blick einander zuordnen.
- **Umbenannt:** Der Proben-Platte-Knopf heißt jetzt **„📋 MP96 Order"** (vorher „Export"), der Aktionsknopf im Dialog **„Auftrag erstellen…"** (vorher „Exportieren…").
- **MP96-Auftrag aus WellDone (neu):** WellDone erzeugt jetzt auch den **Auftrag (Order) für den MagNA Pure 96** – Knopf **„📋 MP96 Order"** bei der Proben-Platte (Zeile *PDF · Import · MP96 Order*). Eine geladene **`TemplateData.xml`** (aus der MP96-Software) liefert die gültigen **Kits, Tests, Volumina, Platten und Internen Kontrollen**; die Proben kommen automatisch aus der Proben-Platte. **Pflichtfelder sind mit einem Sternchen markiert** (Auftrag erst erstellbar, wenn alle gefüllt sind). Export als **Order-XML**, die der MP96 über *Utilities → Query → Import* einliest – so entsteht aus **einer** Probeneingabe in einem Rutsch der MP96-Auftrag **und** (wie gehabt) Pipettierschema + LC-PRO-Setup.
- **Voreinstellungen:** Häufig genutzte Protokolle (Kit/Test/Volumina/Platten/IC) lassen sich als **Voreinstellung speichern und laden** (Feld „Voreinstellung" unten im Dialog) – pro Lauf bleiben nur Proben + Auftragsname einzutragen.
- **Aufgeräumt:** Der frühere **„📥 Vorlage"-Knopf** (CSV-Vorlage der Proben-Platte) ist entfallen; die Proben-Platte-Knöpfe sind jetzt **PDF · Import · MP96 Order** / **Zurück · Proben leeren**.
- **MP96-Belegungsprüfung:** Beim Export prüft WellDone, ob die Proben **lückenlos ab A1 (spaltenweise)** liegen (vom MP96 verlangt) und ob die Anzahl ein **Vielfaches von 8** ist; sonst gibt es eine Warnung. Neu: **„Zusammenrücken"** rückt die Proben lückenlos ab A1 zusammen (ordnet die echte Proben-Platte um, mit „Zurück" widerrufbar) – aus der Warnung **oder** per **Rechtsklick** auf die Proben-Platte. Der **Auftragsname** wird auf dateinamen-unzulässige Zeichen geprüft.

**Version 10.3** (Juni 2026)
- **Englische Sprachvariante:** WellDone! spricht jetzt **Deutsch und Englisch** — umschaltbar im **„❓"-Dialog** (oben *Sprache / Language*, Standard Deutsch). Die Umstellung betrifft Oberfläche, Pipettierschema-PDF und alle Meldungen und greift nach einem **Neustart**; im englischen Modus werden Zahlen mit **Punkt** statt Komma geschrieben (auch in den Eingabefeldern). **Assay-, Proben- und Gerätedaten** (Namen, LCAP, PCR-Profil, Roche-CSV-Spalten) bleiben in beiden Sprachen unverändert. Das Handbuch ist vorerst nur auf Deutsch.
- **Proben per Drag & Drop umordnen:** In der Proben-Platte lässt sich eine belegte Probe mit der Maus auf ein anderes Well ziehen — **leeres Ziel = verschieben**, **belegtes Ziel = tauschen** (inkl. Note/Sample-ID/Prep-Notes). Mit **„↶ Zurück"** rückgängig. Ein kurzer Klick bearbeitet das Well wie gewohnt; die PCR-Platte bleibt unverändert (read-only).

**Version 10.2** (Juni 2026)
- **Zentrale Assay-Bibliothek (Netzwerk-Vorlage):** Neuer Knopf **„📥 Vorlage"** in der Assay-Spalte (vorletzte Zeile: *Vorlage · ▲▼ · Kopieren*). Damit lässt sich die Assay-Bibliothek **aus einer Vorlage auf einer Netzfreigabe laden** (ersetzt die lokale Bibliothek vollständig — **vorher wird automatisch ein datiertes Backup** `assays.backup-…db` angelegt) oder die lokale Bibliothek **als Vorlage speichern** (Master für alle Rechner veröffentlichen). Die lokale `assays.db` bleibt die Arbeitskopie (läuft immer, auch offline); ein **frischer Rechner** ohne lokale Bibliothek wird beim ersten Start automatisch aus der Vorlage befüllt. Abgleich nur manuell — kein geteiltes Live-File, keine Schreib-/Sperrkonflikte.

**Version 10.1** (Juni 2026)
- **MP96-XML-Import:** der MagNA-Pure-96-Export lässt sich jetzt als **XML** einlesen – inkl. **Quellplatte-ID** (Eluat-Barcode) und **Plattenbezeichnung** (Auftrag), die automatisch in die neuen Felder rechts bei der Proben-Platte übernommen werden. CSV bleibt; TXT entfällt (= CSV). **Flags in den Prep-Notes werden im Klartext übersetzt** – die Erklärung aus dem Abschnitt `FlagDefinitions` der XML wird hinter den Code gehängt (z. B. „R03 (Reagent Expiration Rule overridden)"); unbekannte Codes bleiben unverändert.
- **PDF:** Seite 2 zeigt die Quellplatte jetzt als **96er-Raster mit Probennamen** (statt Tabelle); die Plattenbezeichnung steht in Kopf und Überschrift. **Standards-Legende** mehrspaltig (max. 3 Zeilen → bleibt auf Seite 1) mit **Farbpunkt** je Assay. Neuer Knopf **„💾 PDF"** erzeugt ein Proben-Platte-Doku-Blatt (96er-Raster + alle Lauf-Details inkl. **Reagenz-/Lot-Barcodes und Flag-Erklärungen**, zur Rückverfolgung).
- **Proben-Platte-Werkzeuge aufgeräumt:** Zeilen **„Vorlage · PDF · Import"** (je ⅓) und **„Zurück · Proben leeren"** (je ½); neuer **„↶ Zurück"** nimmt große Aktionen (Importieren / Einfügen / Leeren) zurück; „Details Platte" entfällt (steht alles im PDF). Excel-Einfügen geht jetzt auch per **Rechtsklick → Einfügen** (war auf Deutsch nicht erkannt). **Prep-Notes auf eine Zeile** verkleinert → das gefüllte Feld-Detail ist nicht höher als das leere, der blaue **„Plattenbelegung ausführen"-Button springt beim Anklicken eines Probenfeldes nicht mehr** nach unten (PCR-Menü bleibt auf der Mittellinie). Plate-ID-Hinweis als Platzhalter; Kommentarfeld eine Zeile höher.

**Version 10.0** (Juni 2026)
- **Handbuch korrigiert:** veraltete Hinweise „nur 96-Well / 384 nicht vorgesehen" entfernt – **384-Well wird seit 9.3 unterstützt**; das Well-Limit ist jetzt formatabhängig (96 bzw. 384). Geltungsbereich & Einschränkungen an die **externe Standardkurve** (seit 9.4) angepasst: qualitative **und** quantitative Tests (RS/MS, Standardkurve am Gerät) – **keine** in-Run-Standardkurven/Verdünnungsreihen im Plate-Setup.
- **Fehler behoben (Probenplatte):** Strg-/Umschalt-Mehrfachauswahl löschte zuvor markierte Proben (der versteckte Inline-Editor überschrieb sie mit leerem Text) – behoben. Bereits auf die PCR-Platte übertragene Quell-Wells werden wieder **ausgegraut**.
- **Neu:** Einzelne belegte **PCR-Felder löschbar** – Feld anklicken → im Feld-Detail 🗑; mit „Zurück" wiederherstellbar; im 384-Quadranten-Modus nicht verfügbar.
- **Neu:** **Mehrere Zellen aus Excel einfügen** – Start-Zelle anklicken und Strg+V; eine Spalte/Zeile wird in Eingabe-Richtung verteilt, ein Block positionstreu (nur Probennamen).

**Version 9.4** (Juni 2026)
- **Standards (externe Standardkurve):** je Assay optional Referenz-/Schmelzstandards (RS/MS) mit Targetname + optionaler Notiz (Doku); sie belegen ein Well und erscheinen in der CSV mit `SampleRole` RS/MS und `Targetname`. Für abs. Quantifizierung / MCGT mit am Gerät importierter Standardkurve. (Qualitativ + Tm Calling brauchen keine Standards.)
- **Assay-Verwaltung:** „Kopieren"-Knopf (Assay duplizieren) und **Doppelklick** zum Bearbeiten.
- Standards werden wie Positivkontrollen **dunkler** eingefärbt; die Übersicht „Assays auf PCR-Platte" und die **Standards-Legende** im PDF (linksbündig, bei vielen mehrspaltig) führen sie jetzt mit auf. **Bug behoben:** im Quadranten-Modus werden Kontrollen/Standards jetzt immer platziert (auch wenn eine Probe im letzten Well H12 liegt). PDF-**Probenzuordnung** immer auf Seite 2, linksbündig, bis zu 3 Spalten, mit Hinweis „spaltenweise sortiert" (ohne Zebra).

**Version 9.3** (Juni 2026)
- **384-Well-Belegung** überarbeitet: Umschalten 96/384 über die **Assay-Reiter**; **Quadranten-Modus** stempelt jedes Quell-Well in seinen 2×2-Block (96-Kanal-Pipette), bis zu 4 Assays je Block, Richtung im/gegen Uhrzeigersinn.
- Neue Kontroll-Platzierungen **„Proben → Positiv → Negativ"** und **„Proben → Negativ → Positiv"**; feste Kontroll-Wells jetzt als **Texteingabe**.
- **384-Raster** zeigt die **Quell-Koordinate**; PDF mit Abschnitt **„Probenzuordnung"** und Fußzeile „Seite X von Y".
- **Duplikate-Schalter entfernt** – Replikate sind immer erlaubt. Kommentarfeld vergrößert.

**Version 9.2** (Juni 2026)
- Diese Versionsübersicht ins Handbuch aufgenommen.

**Version 9.1**
- **Kontroll-Platzierung je Assay** wählbar: Positiv→Proben→Negativ, umgekehrt, oder **feste Positionen** (frei wählbare Wells über eine Mini-Platte).
- **Sicherheitsvolumen je Assay** einstellbar (Reserve gegen Pipettierverlust).
- Datei-Dialoge merken sich den zuletzt genutzten Ordner **je Zweck**.
- Probenplatte-Knöpfe vereinheitlicht (Importieren / Leeren).

**Version 9.0**
- Abgleich mit der offiziellen **Roche-CSV-Spezifikation**; Prüfung auf **unzulässige Zeichen** in Proben-/Platten-Namen (Markierung + Warnung).

**Version 8.9**
- Probennamen **mindestens 2 Zeichen** (der LightCycler PRO akzeptiert keine 1-Zeichen-IDs); zu kurze Namen werden orange markiert.
- Plate-ID-Hilfetext; Hinweis „nur qualitative Tests"; Tooltips im Assay-Dialog.

**Version 8.8**
- Kontrollen je Assay **nur einmal** — auch über mehrere Belegungen hinweg (genau 1 PTC + 1 NTC).
- Hinweis vor dem Export, wenn ein Probenname über 23 Zeichen gekürzt wird.

**Version 8.7**
- Positiv-/Negativkontrollen auf Bildschirm und im PDF **deutlich gekennzeichnet** (Symbol + Schattierung).

**Version 8.6**
- Automatische **Update-Prüfung** (Hinweis im „❓"-Dialog); Verteilung über den gemeinsamen Ordner.
- Robustere PDF-/CSV-Erstellung (klare Fehlermeldungen, Speicherort „Dokumente").
- Assay-Bibliothek pro Benutzer (`%APPDATA%`).

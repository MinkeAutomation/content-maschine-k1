# Kosten: rund 1 Cent je Lauf, fast nur Recherche

_Stand der Abgabe W05T03 vom 14.10.2026 (K1 v23, Telegram-Eingang v08, SUB Nextcloud-Ablage v03, Leitstand v16). Neuere Änderungen stehen im [CHANGELOG](../CHANGELOG.md)._

**Kosten je Lauf: 0,0116 USD**, Mittel aus 9 Läufen mit dem Prompt `k1-p4`, gelesen aus dem Feld `usage` der Modellantworten. Gerechnet ohne Hosting, nur Sprachmodell und API. Die 9 gemessenen Läufe waren Themenläufe mit je 3 Modellaufrufen (2 Sonar, 1 Schreibaufruf). Bei Artikel, Video oder eigenem Text entfällt die Faktenrecherche, ein ungültiger Auftrag hat keinen Modellaufruf; Ersatzmodell und Retry können Aufrufe hinzufügen. Gegenprobe: Ein Artikel-Link kostet ohne Faktenrecherche rund 0,006 USD (Läufe 1085, 1086); der Probelauf 1128 (Research aus dem Leitstand, 14.10.) zeigt im Leitstand 0,0116 USD.

| Zusammensetzung eines Laufs | Anteil | Modell |
|---|---|---|
| Recherche virale Posts | 48,5 % | Perplexity Sonar |
| Themenrecherche | 47,8 % | Perplexity Sonar |
| Paket schreiben | 3,6 % | GPT-4.1 nano |
| Bilder | 0 % | in den 9 Läufen ohne Kosten |

| Hochrechnung, Läufe am Tag | je Tag | je Monat (22 Arbeitstage) |
|---|---|---|
| 5 Läufe | 0,06 USD | 1,27 USD |
| 20 Läufe | 0,23 USD | 5,09 USD |
| 1.000 Läufe | 11,56 USD | 254,28 USD |

Rechenweg: Tag = Lauf × Läufe, Monat = Tag × 22 Arbeitstage, mit dem ungerundeten Laufmittel. Rechenannahme ohne Wechselkurs: Mit 1 € = 1 $ reicht 1 € am Tag für 86 Läufe (86 Läufe kosten 0,994 USD). Ein ungültiger Auftrag kostet 0 USD, weil die Eingabeprüfung vor dem Modell stoppt (Lauf 904).

**Prompt vorher und nachher** (Messung vom 13.10., Testkopie, noch nicht im Betrieb; Referenz-Set 4 Themen mit je 3 Läufen): Prompt-Tokens 1.874 auf 1.478 (minus 21 %), mittlerer Prüfwert 16,58 auf 16,75 von 17 Punkten; Kosten fast gleich (minus 0,3 %), weil das Schreibmodell nur 3,6 % ausmacht. Der Mittelwert steigt, aber 2 von 12 Bild-Suchbegriffen der gekürzten Fassung verletzen das Suchbegriff-Kriterium (höchstens 60 Zeichen, keine verbotenen Wörter), beim aktiven Prompt 0 von 12. Deshalb bleibt die gekürzte Fassung in der Testkopie. Eine stärker gekürzte Fassung war schlechter und ist verworfen.

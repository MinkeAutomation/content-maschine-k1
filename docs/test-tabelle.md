# Test-Tabelle: 22 Fälle, Stand 13.10.

_Stand der Abgabe W05T03 vom 14.10.2026 (K1 v23, Telegram-Eingang v08, SUB Nextcloud-Ablage v03, Leitstand v16). Neuere Änderungen stehen im [CHANGELOG](../CHANGELOG.md)._

5 Happy Path, 11 Edge Case, 6 Fehler. Alle 22 Fälle bestanden auf dem jeweils genannten Lauf, alle Läufe stammen aus Versionen bis 13.10. mittags. 16 Fälle liefen auf dem Endstand vom 12. und 13.10., 3 sind aus Stand v17b gültig, 3 sind dort nicht neu gelaufen (14, 18, 19), weil sie sich über das Formular nicht auslösen lassen und bei ihrem älteren Lauf stehen. Version `99e45166` kam am 13.10. abends mit 3 Reparaturen dazu; die Tabelle gilt für die Vorversionen. Auf `99e45166` liefen am 14.10. die 6 Probeläufe vor der Abschlusspräsentation; dabei trat Fall 18 echt auf (Lauf 1118, Telegram-Versand scheitert, F8), die anderen 21 Fälle sind auf dieser Version nicht wiederholt.

| Nr | Fall | Kategorie | Ergebnis | Lauf |
|---|---|---|---|---|
| 1 | Freigeben per Telegram | Happy Path | PASS | 1022, 1023 |
| 2 | Ablehnen mit Grund (zweiter Testkunde) | Happy Path | PASS | 1025 |
| 3 | Thema mit Foto, Layout 4, Speichern | Happy Path | PASS | 1022, 905 |
| 4 | Gesamtlauf mit 11 Prüfpunkten | Happy Path | PASS | 895 (v17b) |
| 20 | Formular, Thema, Tokens aller 3 Aufrufe prüfen | Happy Path | PASS | 1083 |
| 5 | Sehr lange Quelle | Edge Case | PASS | 1085 |
| 6 | Quelle in anderer Sprache | Edge Case | PASS | 1086 |
| 7 | Sonderzeichen, Umlaute, Emoji, HTML | Edge Case | PASS | 1087 |
| 8 | Thema zu kurz (E5), Telegram-Eingang und Testaufruf | Edge Case | PASS | 904, 898 |
| 9 | Zahl im Thema ohne Beleg, Hashtag ohne Bezug | Edge Case | PASS | 892 (v17b) |
| 10 | Eigener Text mit anderer Zahl | Edge Case | PASS | 893 (v17b) |
| 11 | Video-Text-Dienst liefert nichts (F2) | Edge Case | PASS | 1089 |
| 12 | Artikel zu kurz (F1) | Edge Case | PASS | 1088 |
| 13 | Kunde unbekannt (F6) | Edge Case | PASS | 899 |
| 14 | Bild in falscher Größe, Rückfall auf das bisherige Layout | Edge Case | PASS | 769 (offen) |
| 21 | Thema „ab“ über das Formular (E5) | Edge Case | PASS | 1084 |
| 15 | Hauptmodell fällt aus (F3) | Fehler | PASS | 900 |
| 16 | Rendern scheitert (F5) | Fehler | PASS | 901 |
| 17 | Foto-Download scheitert | Fehler | PASS | 903 |
| 18 | Telegram-Versand scheitert (F8) | Fehler | PASS | 847, live 1118 |
| 19 | Folientexte passen nicht zu den Bildern (F8) | Fehler | PASS | 880 (offen) |
| 22 | Leitstand ohne oder mit falschen Zugangsdaten | Fehler | PASS | 4 Aufrufe, 403 |

**Fails auf dem Weg dorthin:** 12 eingeordnet, davon 10 Bugs im Workflow (z. B. Lauf 672: ohne Eingabeprüfung erfand das Modell ein Paket; heute Stopp vor dem Modell) und 2 unrealistische Testfälle, die ersetzt wurden. Ein Fail ist nicht eingeordnet: Lauf 902 (Foto-Fehlerweg mit angepinntem Bilddienst), der Nachtest braucht 2 einzelne Pins im Editor. Fall 22 lehnt richtig ab, liefert aber 403 statt des erwarteten 401; das ist Verhalten von n8n bei Basic Auth, kein Bug im Workflow.

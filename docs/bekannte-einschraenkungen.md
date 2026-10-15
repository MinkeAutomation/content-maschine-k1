# Bekannte Einschränkungen: 5 gemessene Grenzen

_Stand der Abgabe W05T03 vom 14.10.2026 (K1 v23, Telegram-Eingang v08, SUB Nextcloud-Ablage v03, Leitstand v16). Neuere Änderungen stehen im [CHANGELOG](../CHANGELOG.md)._

Jede Grenze hat einen Messwert oder einen Beleg aus dem Workflow-Export. Zwei davon sind fehlende Bausteine, die bewusst nicht mehr vor der Bewertung gebaut werden.

| Grenze | Messwert oder Beleg | Folge und nächster Schritt |
|---|---|---|
| **1. Kein Ersatz für die Spracherkennung** (fehlender Baustein) | Telegram-Eingang v08: Whisper über Cloudflare Workers AI mit 3 Versuchen; der Fehlerausgang führt nur zur Antwort „Bitte tippen“. Ein zweiter Dienst ist nicht angebunden. | Fällt Whisper aus, gehen Sprachaufträge nicht, Text bleibt möglich. Zweiten Dienst als Ersatz anbinden. |
| **2. Spracherkennung verhört Kundenkürzel** | Lauf 721: aus „Ordwin“ wurde „Kundenort Win“. Ein toleranter Abgleich der Kürzel ist nicht gebaut. | Sprachauftrag ohne Kundenname, Kunde per Text oder Formular. Abgleich gegen die Kundenliste bauen. |
| **3. Die Recherche ist nicht gratis** | 96 % der Laufkosten: 0,0116 USD je Lauf im Mittel aus 9 Läufen, davon 48,5 % Recherche virale Posts und 47,8 % Themenrecherche (Sonar), 3,6 % Schreibmodell; gemessen an 9 Themenläufen. | Der nächste Kostenhebel ist die Recherche (günstigerer Suchdienst, Zwischenspeicher), nicht der Prompt. |
| **4. Speichergrenze** | Supabase-Gratisplan 1 GB Dateispeicher; gemessen 6,0 bis 7,4 MB je Lauf (PNG), am 13.10. belegt 271,4 MB. Hochrechnung mit 6,6 MB je Lauf und 5 Läufen am Tag, ohne Aufräumen: voll nach rund 23 Tagen. | Bilder als JPEG speichern und nach der Ablage in Nextcloud aus Supabase löschen. |
| **5. Protokollzeile im Fehlerweg ohne eigenen Fehlerausgang** (fehlender Baustein) | Export K1 v23: der Knoten `Fehlerweg protokollieren [Supabase]` hat keinen Fehlerausgang. Scheitert Supabase genau dort, endet der Lauf rot, aber ohne Protokollzeile und ohne Telegram-Hinweis. | Lauf bleibt sichtbar rot in n8n, die Spur im Laufprotokoll fehlt. Fehlerausgang mit Ersatzmeldung nachrüsten. |

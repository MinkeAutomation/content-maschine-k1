# Lessons Learned: 3 Lehren aus dem Bau

_Stand der Abgabe W05T03 vom 14.10.2026 (K1 v23, Telegram-Eingang v08, SUB Nextcloud-Ablage v03, Leitstand v16). Neuere Änderungen stehen im [CHANGELOG](../CHANGELOG.md)._

| Lehre | Was passiert ist | Beleg |
|---|---|---|
| **1. Erst messen, dann ändern** | Ich habe 2 gekürzte Prompt-Fassungen gegen das Referenz-Set gemessen. Die stärker gekürzte war schlechter und flog raus; die mildere spart 21 % Prompt-Tokens, aber nur 0,3 % der Kosten, und bleibt vorerst in der Testkopie. | Referenz-Set 4 Themen, je 3 Läufe |
| **2. Billig prüfen vor teuer rechnen** | Ohne Eingabeprüfung erfand das Modell zu einem leeren Thema ein ganzes Paket. Die Prüfung vor dem Modell spart Geld und verhindert erfundene Inhalte. | Lauf 672 erfand ein Paket, Lauf 904 stoppt nach 2 s mit 0 USD |
| **3. Der teuerste Teil war nicht das Schreiben** | Das Schreibmodell kostet 3,6 %, gemessen macht die Recherche 96 % der Kosten, deshalb bringt Prompt-Kürzen fast nichts. | 0,0116 USD je Lauf, Mittel aus 9 Themenläufen vom 12. und 13.10. |

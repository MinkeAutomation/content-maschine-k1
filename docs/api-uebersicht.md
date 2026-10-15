# API-Übersicht: 11 Dienste, Zugangsdaten nur in n8n

_Stand der Abgabe W05T03 vom 14.10.2026 (K1 v23, Telegram-Eingang v08, SUB Nextcloud-Ablage v03, Leitstand v16). Neuere Änderungen stehen im [CHANGELOG](../CHANGELOG.md)._

Jeder Dienst ist mit Zweck, Art der Anmeldung und Endpunkt aufgeführt. Schlüssel, Tokens und Passwörter liegen ausschließlich in n8n-Credentials; die Exporte in diesem Repository enthalten nur den Credential-Namen und einen Platzhalter statt der Credential-ID.

| Dienst | Wofür | Auth | Endpunkt |
|---|---|---|---|
| OpenRouter | Paket schreiben (GPT-4.1 nano) | Bearer-Token | POST openrouter.ai/api/v1/chat/completions |
| Perplexity Sonar | Recherche und aktuelle Posts | Bearer-Token | POST openrouter.ai/api/v1/chat/completions |
| NVIDIA Nemotron | Ersatzmodell, wenn das Paket ungültig ist | API-Key | integrate.api.nvidia.com/v1 (n8n-Knoten) |
| Jina Reader | Artikel als Text lesen | ohne Schlüssel | GET r.jina.ai/&lt;Adresse&gt; |
| Supadata | YouTube-Untertitel | Header-Auth | GET api.supadata.ai/v1/transcript |
| Pixabay | Fotos suchen | Query-Auth | GET pixabay.com/api/ |
| Cloudflare Workers AI | Ersatzbild (FLUX), Sprache zu Text (Whisper) | Header-Auth | POST api.cloudflare.com/client/v4/accounts/…/ai/run/@cf/… |
| Gotenberg | HTML zu Bild, eigener Server | intern | POST /forms/chromium/screenshot/html |
| Supabase | Tabellen und privater Bildspeicher | API-Key | /rest/v1/… und /storage/v1/… |
| Telegram | Eingang, Vorschau, Freigabe | Bot-Token | api.telegram.org (n8n-Knoten) |
| Nextcloud | Ablage und Freigabelink, eigener Server | Benutzer und Passwort | WebDAV und /ocs/v2.php/apps/files_sharing/api/v1/shares |

Sonar läuft über denselben OpenRouter-Zugang wie das Schreibmodell. Gotenberg läuft auf eigenem Server und wird ohne Schlüssel aufgerufen.

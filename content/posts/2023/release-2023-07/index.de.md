---
title: "🍒 🐄 Mooly Update 2023 - Manageable CORS Settings and UI Improvements"
date: 2023-07-28T10:48:10+02:00
draft: false

author: Patrick Schult/FreddleSpl0it
authorLink: "https://github.com/FreddleSpl0it"
toc: true

license: ""

tags: ["2023", "update", "changelog", "CORS", "Spamhaus", "DNSBL"]
categories: ["Updates"]

---

**Moohoo zusammen!**

### Wichtig
Vergewissert euch vor dem Update von mailcow, dass das Paket `whois` auf eurem System installiert ist.

### Neues Feature: CORS-Einstellungen verwalten
Administratoren können jetzt CORS-Einstellungen (Cross-Origin Resource Sharing) über die Web-UI für den API-Zugang verwalten. 
Dadurch ist eine bessere Kontrolle und erhöhte Sicherheit bei der Datenübermittlung zwischen verschiedenen Quellen möglich.

#### CORS - Warum wird es benötigt?
Unter normalen Umständen, wenn ein Skript im Browser des Benutzers ausgeführt wird, muss es hauptsächlich auf Ressourcen von derselben Quelle zugreifen.
Zum Beispiel können API-Aufrufe an das Backend erfolgen, von dem der JavaScript-Code ursprünglich bereitgestellt wurde.
Diese Einschränkung, dass JavaScript nicht auf Ressourcen von anderen Quellen zugreifen kann, ist eine Sicherheitsmaßnahme.

In diesem Kontext beziehen sich "andere Quellen" auf URLs, die sich von dem Ort unterscheiden, an dem das JavaScript ausgeführt wird. Diese Unterschiede können verschiedene Domains, Ports oder Protokolle (HTTP oder HTTPS) umfassen.
Obwohl diese Sicherheitsmaßnahme wichtig ist, um Benutzer vor unberechtigtem Zugriff auf ihre Daten zu schützen, gibt es legitime Situationen, in denen ein Zugriff zwischen verschiedenen Quellen notwendig oder wünschenswert ist.


### Broadcasting von Befehlen an mehrere Dockerapi-Instanzen!
Für Administratoren, die mailcow in einem Cluster verwenden, ist es jetzt erforderlich, folgende Einstellung in der Datei mailcow.conf vorzunehmen: `CLUSTERMODE=replication`.
Dadurch wird sichergestellt, dass beim Löschen eines Postfachs die Anfrage an jeden Dockerapi-Container und somit an jeden Dovecot-Container gesendet wird, sodass alle Dateien auf jedem Host gelöscht werden.


**Bug fixes, Bug fixes und noch mehr Bug fixes...**


### Changelog

- Update thollander/actions-comment-pull-request action to v2.4.0
- Update dependency nextcloud/server to v27
- Update nextcloud heper script to disable SMTP TLS host verification
- [API] Update swagger version to 5.1.0
- Rspamd returns 401 on unsuccesful logins
- [Web] add cors to json_api
- [Web] fix loading rspamd-history
- [Dockerapi] add redis pubsub handler for broadcasting requests
- [Rspamd] add dot-stuffing to bcc forwarding
- [web] logger pdo exception handling workaround
- [Rspamd] Native mailcow Support for Securite ClamAV Signatures
- Fixes several instances of missing , extra role='tabpanel' and…
- Update dependency nextcloud/server to v27.0.1
- Spamhaus DNSBL AS Detection

Wie immer gilt, der volle Changelog auch mit den einzelnen Commits ist für Interessenten jederzeit auf GitHub abrufbar:
https://github.com/mailcow/mailcow-dockerized/releases/tag/2023-07

---

#### Bleibt gespannt für mehr:

Während wir mailcow weiterentwickeln und verbessern, halten wir euch auf dem Laufenden über die neuesten Entwicklungen und Verbesserungen.

Ein riesiges Dankeschön an unsere großartige mailcow-Community für eure andauernde Unterstützung und wertvollen Rückmeldungen.
Eure Beiträge haben maßgeblich dazu beigetragen, mailcow noch besser, stabiler und benutzerfreundlicher zu machen!

Bleibt gesund und happy Mailing!

Euer mailcow Team

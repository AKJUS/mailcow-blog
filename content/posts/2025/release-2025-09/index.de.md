---
title: "🍂🐄 Mootember Update 2025 | MTA-STS Support, SOGo 5.12.3, Rspamd 3.12.1, and More"
date: 2025-09-10T11:30:00+02:00
draft: false

author: The Infrastructure Company GmbH
toc: true

license: ""

tags: ["2025", "update", "changelog"]
categories: ["Updates"]

---


# 2025-09 (Release vom 10.09.2025)

**Moohoo zusammen!**  

Wir freuen uns, euch das **2025-09 Update** präsentieren zu können!  
Dieses Release bringt **neue Features, aktualisierte Komponenten und natürlich die üblichen Bugfixes**.  

{{< admonition type=warning title="Wichtig" open=true >}}  
mailcow erfordert nun die Installation von `jq` auf dem Host-System, um mit dem neu gestalteten IPv6-Controller zu funktionieren.  
Falls es fehlt, installiere es bitte **vor** der Ausführung des Updates. Dieses Tool ist verpflichtend und wird in zukünftigen Versionen nicht entfernt werden.  
{{% /admonition %}}

{{< admonition type=warning title="Wichtig" open=true >}}  
Dieses Update bringt einen brandneuen Container mit: **`postfix-tlspol-mailcow`**, der  ausgehenden **MTA-STS-Support** zu Postfix hinzufügt.  

Prüft nach dem Update, dass der neue Container korrekt läuft, indem ihr die Logs kontrolliert:  
```
docker compose logs -f --tail 200 postfix-tlspol-mailcow
```

Sollten **CPU-Probleme oder fortlaufende Neustarts** auftreten, baut das Image manuell neu:  
```
docker build -t ghcr.io/mailcow/postfix-tlspol:1.0 data/Dockerfiles/postfix-tlspol
docker compose up -d
```  
{{% /admonition %}}


## Features
- [Rspamd][Web] Internal alias support ➡️ [PR #6713](https://github.com/mailcow/mailcow-dockerized/pull/6713)
- [Postfix][Web] add mta-sts support ➡️ [PR #6686](https://github.com/mailcow/mailcow-dockerized/pull/6686)
- [Helper-Scripts] Add prometheus exporter and grafana dashboard for mailcow ➡️ [PR #6314](https://github.com/mailcow/mailcow-dockerized/pull/6314)
- [DB][Web] optimize qhandler by keeping SHA2 in new column qhash ➡️ [PR #6556](https://github.com/mailcow/mailcow-dockerized/pull/6556)
- [Web] Add delimiter_action to mailbox and mailbox_template add/edit admin forms ➡️ [PR #6620](https://github.com/mailcow/mailcow-dockerized/pull/6620)
- [Core] modules splitting + ipv6 nat rewrite ➡️ [PR #6634](https://github.com/mailcow/mailcow-dockerized/pull/6634)

## Updates
- [SOGo] update to 5.12.3 ➡️ [Commit 360fe03](https://github.com/mailcow/mailcow-dockerized/commit/360fe0349734098bd9da75841c8cd221fbf8c32f)
- [Rspamd] update rspamd to 3.12.1 ➡️ [PR #6643](https://github.com/mailcow/mailcow-dockerized/pull/6643)

## Bug Fixes
- [Clamd] Changed clamavs tmp folder structure ➡️ [PR #6698](https://github.com/mailcow/mailcow-dockerized/pull/6698)
- [Rspamd] only recreate external_services.conf file if it was deleted ➡️ [PR #6717](https://github.com/mailcow/mailcow-dockerized/pull/6717)
- [Dovecot] imapsync gets correct timeouts from imapsync_runner.pl ➡️ [PR #6682](https://github.com/mailcow/mailcow-dockerized/pull/6682)
- [Web] Fix multiple PHP Warnings present in "stock" installation ➡️ [PR #6651](https://github.com/mailcow/mailcow-dockerized/pull/6651)
- [Dovecot] Prevent user login if protocol access has been disabled ➡️ [PR #6716](https://github.com/mailcow/mailcow-dockerized/pull/6716)
- [Web] Only include mailcow_info in JS when mailcow_cc_username is set ➡️ [PR #6715](https://github.com/mailcow/mailcow-dockerized/pull/6715)
- [Rspamd] Add boundary if present when applying domain-wide footer ➡️ [PR #6714](https://github.com/mailcow/mailcow-dockerized/pull/6714)
- [Rspamd] Do not increment rate limit for emails from user to himself ➡️ [PR #6706](https://github.com/mailcow/mailcow-dockerized/pull/6706)
- [Web] rename login placeholder for mailbox to email address ➡️ [PR #6693](https://github.com/mailcow/mailcow-dockerized/pull/6693)
- [Watchdog] use dig instead of check_dns ➡️ [PR #6685](https://github.com/mailcow/mailcow-dockerized/pull/6685)
- [Rspamd] Fill module name for set_pre_result actions ➡️ [PR #6630](https://github.com/mailcow/mailcow-dockerized/pull/6630)
- [Netfilter] fix negative timer, no unbanning of IPs ➡️ [PR #6575](https://github.com/mailcow/mailcow-dockerized/pull/6575)


## Full Changelog
https://github.com/mailcow/mailcow-dockerized/compare/2025-07...2025-09

---

Das war es für dieses Release! Wie immer empfehlen wir, eure mailcow-Installation auf dem neuesten Stand zu halten und regelmäßig Backups zu erstellen.

Bleibt sicher und viel Spaß!

Euer mailcow-Team von **The Infrastructure Company GmbH** (kurz **tinc**)

---
title: "🏖️🐮 Mooly 2026 | Postfix 3.10.12, Rspamd 4.1.0 & Nginx 1.30.3"
date: 2026-07-13T11:00:00+02:00
draft: false

author: The Infrastructure Company GmbH
toc: true

license: ""

tags: ["2026", "update", "changelog", "major"]
categories: ["Updates"]

---

## 2026-07 (Release vom 13.07.2026)

**Moohoo zusammen!**

Wir freuen uns sehr, euch das **Update 2026-07** zu präsentieren!
Dieses Release bringt gleich mehrere große Sprünge auf einmal: Unser **Postfix**-Container migriert von **Debian Bookworm auf Trixie** und läuft nun mit **Postfix 3.10.12**. Außerdem aktualisieren wir **rspamd** auf die **Version 4.1.0** (ein Major-Sprung von 3.x), aktualisieren **SOGo auf 5.12.9** und **Nginx auf 1.30.3**. Dazu kommen einige kleinere UI-Fixes und die üblichen Übersetzungs- und Postscreen-Updates.

---

**⚠️ Wichtiger Hinweis:**
Dieses Update enthält signifikante Änderungen an den zugrundeliegenden Container-Images (u.a. der Sprung von Debian 12 auf Debian 13 im Postfix-Container und ein Major-Upgrade von rspamd). Wir **empfehlen dringend, ein Backup** eurer mailcow-Installation vor dem Update zu erstellen, um auf der sicheren Seite zu sein.

---

### New Features

* postfix: migrate from bookworm to trixie by @DerLinkman ➡️ [PR #7323](https://github.com/mailcow/mailcow-dockerized/pull/7323)
* Update RSPAMD version to 4.1.0 in Dockerfile by @dragoangel ➡️ [PR #7172](https://github.com/mailcow/mailcow-dockerized/pull/7172)
* [Rspamd] Migrate metadata_exporter to multipart formatter by @FreddleSpl0it ➡️ [PR #7283](https://github.com/mailcow/mailcow-dockerized/pull/7283)
* [SOGo] Update to 5.12.9 by @goodygh ➡️ [PR #7267](https://github.com/mailcow/mailcow-dockerized/pull/7267)
* [Nginx] Update to 1.30.3 by @FreddleSpl0it ➡️ [PR #7305](https://github.com/mailcow/mailcow-dockerized/pull/7305)

### Bug Fixes

* Refresh SOGo view after mailbox activation by @ibobgunardi ➡️ [PR #7277](https://github.com/mailcow/mailcow-dockerized/pull/7277)
* Fix force_tfa not available in mailbox template #7216 by @Snafu ➡️ [PR #7275](https://github.com/mailcow/mailcow-dockerized/pull/7275)
* Escape generated password in mobileconfig by @mkuron ➡️ [PR #7212](https://github.com/mailcow/mailcow-dockerized/pull/7212)
* ui, fail2ban fix german ban_list_info translation by @goodygh ➡️ [PR #7265](https://github.com/mailcow/mailcow-dockerized/pull/7265)
* Refined wording for displaying of active settings on quarantine page by @ralfbergs ➡️ [PR #7326](https://github.com/mailcow/mailcow-dockerized/pull/7326)

### Updates

* [Postfix] update postscreen_access.cidr by @milkmaker ➡️ [PR #7269](https://github.com/mailcow/mailcow-dockerized/pull/7269)
* [Postfix] update postscreen_access.cidr by @milkmaker ➡️ [PR #7311](https://github.com/mailcow/mailcow-dockerized/pull/7311)
* Translations update from Weblate by @milkmaker ➡️ [PR #7262](https://github.com/mailcow/mailcow-dockerized/pull/7262)
* Translations update from Weblate by @milkmaker ➡️ [PR #7263](https://github.com/mailcow/mailcow-dockerized/pull/7263)
* Translations update from Weblate by @milkmaker ➡️ [PR #7302](https://github.com/mailcow/mailcow-dockerized/pull/7302)
* Update dependency php/pecl-mail-mailparse to v3.2.0 by @renovate[bot] ➡️ [PR #7189](https://github.com/mailcow/mailcow-dockerized/pull/7189)
* Update dependency composer/composer to v2.10.1 by @renovate[bot] ➡️ [PR #7193](https://github.com/mailcow/mailcow-dockerized/pull/7193)
* Update dependency composer/composer to v2.10.2 by @renovate[bot] ➡️ [PR #7312](https://github.com/mailcow/mailcow-dockerized/pull/7312)
* Update alpine Docker tag to v3.24 by @renovate[bot] ➡️ [PR #7280](https://github.com/mailcow/mailcow-dockerized/pull/7280)
* Update actions/checkout action to v7 by @renovate[bot] ➡️ [PR #7300](https://github.com/mailcow/mailcow-dockerized/pull/7300)
* Update actions/stale action to v10.4.0 by @renovate[bot] ➡️ [PR #7322](https://github.com/mailcow/mailcow-dockerized/pull/7322)
* Update devops-infra/action-pull-request action to v1.2.1 by @renovate[bot] ➡️ [PR #7258](https://github.com/mailcow/mailcow-dockerized/pull/7258)
* Update devops-infra/action-pull-request action to v1.3.0 by @renovate[bot] ➡️ [PR #7272](https://github.com/mailcow/mailcow-dockerized/pull/7272)
* Update devops-infra/action-pull-request action to v1.4.0 by @renovate[bot] ➡️ [PR #7321](https://github.com/mailcow/mailcow-dockerized/pull/7321)

### New Contributors

* @ibobgunardi made their first contribution ➡️ [PR #7277](https://github.com/mailcow/mailcow-dockerized/pull/7277)
* @Snafu made their first contribution ➡️ [PR #7275](https://github.com/mailcow/mailcow-dockerized/pull/7275)
* @ralfbergs made their first contribution ➡️ [PR #7326](https://github.com/mailcow/mailcow-dockerized/pull/7326)

### Full Changelog
[https://github.com/mailcow/mailcow-dockerized/compare/2026-05c...2026-07](https://github.com/mailcow/mailcow-dockerized/compare/2026-05c...2026-07)

---

Das war's für dieses Release!
Wie immer empfehlen wir, eure mailcow-Installation auf dem neuesten Stand zu halten und eure Daten regelmäßig zu sichern.

Bleibt sicher und happy mailing!

Euer mailcow-Team von **The Infrastructure Company GmbH** (oder kurz **tinc**)

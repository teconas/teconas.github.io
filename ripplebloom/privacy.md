---
title: Datenschutzerklärung / Privacy Policy – Ripplebloom
---
{% assign game = site.games | where: "slug", page.game | first -%}
# Datenschutzerklärung – {{ game.name }}

## Name der App  
**{{ game.name }}**

## Verantwortlicher  
{{ site.owner }}  
E-Mail: [{{ site.email }}](mailto:{{ site.email }})

## Allgemeine Hinweise  
Der Schutz Ihrer Daten ist mir wichtig. Diese App erhebt, speichert oder verarbeitet **keine personenbezogenen Daten** im Sinne der Datenschutz-Grundverordnung (DSGVO).
**TODO: Nur so stehen lassen, wenn es für die finale App zutrifft.**

## Keine Datenerhebung durch die App  
Die App **{{ game.name }}** ist vollständig offlinefähig und erhebt keinerlei Informationen über Ihre Person, Ihr Gerät, Ihren Standort oder Ihr Nutzungsverhalten.  
Es werden **keine Analyse-Tools**, **keine Werbe-SDKs**, **keine Webanfragen**, **keine In-App-Käufe** und **keine Tracker** eingesetzt.

- **TODO SDKs:** Eingebundene Bibliotheken/SDKs prüfen (z. B. Capacitor-Plugins) und ob sie Daten erheben oder senden.
- **TODO Werbung:** Keine Werbung? Sonst Werbenetzwerk, Datenarten, Einwilligung (Consent) beschreiben.
- **TODO Analytics:** Keine Analyse-/Crash-Reporting-Tools? Sonst Anbieter und Datenarten nennen.
- **TODO In-App-Käufe:** Keine? Sonst Abwicklung über Google Play Billing beschreiben.
- **TODO Online-Funktionen:** Wirklich keine Webanfragen (auch keine Fonts, Updates, Bestenlisten)?
- **TODO Berechtigungen:** Angeforderte Android-Berechtigungen aus dem Manifest prüfen und ggf. aufführen (z. B. INTERNET).

Da keine Verarbeitung personenbezogener Daten erfolgt, ist **keine Rechtsgrundlage gemäß Art. 6 DSGVO erforderlich**.
**TODO: Anpassen, falls oben doch eine Verarbeitung stattfindet.**

## Datenerhebung durch Google Play  
Beim Herunterladen und Installieren der App über den Google Play Store kann Google selbst bestimmte Daten erfassen, etwa zur Geräteidentifikation oder Nutzung der App.
Auf diese Datenverarbeitung hat der Anbieter dieser App **keinen Einfluss**. Es gelten in diesem Fall die **Datenschutzrichtlinien von Google**, abrufbar unter:  
👉 [https://policies.google.com/privacy](https://policies.google.com/privacy)

## Lokale Speicherung von Spieldaten
Der Spielstand und andere technisch notwendige Spieldaten werden **ausschließlich lokal auf dem Gerät gespeichert**.  
Diese Daten enthalten **keine personenbezogenen Informationen** und werden von der App **nicht an Dritte übermittelt**.
**TODO: Prüfen, was genau gespeichert wird (z. B. Level-Fortschritt, Einstellungen) und wo (z. B. WebView-Speicher).**

Je nach Geräte-Einstellungen oder Betriebssystem-Funktionen (z. B. Google-Backups oder Gerätemigrationen) kann es jedoch sein, dass diese Daten von **Google oder anderen Dienstanbietern automatisch synchronisiert oder gesichert** werden.  
Auf diese Vorgänge hat der App-Anbieter **keinen Einfluss**.

## Rechte betroffener Personen  
Sie haben grundsätzlich die Rechte aus Art. 15 bis 22 DSGVO (z. B. Auskunft, Löschung). Da die App **keine personenbezogenen Daten** verarbeitet, liegen hierzu jedoch keine Daten vor.
**TODO: Betroffenenrechte ausführen, falls doch Daten verarbeitet werden.**

## Kontakt  
Bei Fragen zum Datenschutz können Sie sich gerne an folgende Adresse wenden:  
📧 **{{ site.email }}**

## Stand  
**TODO: Datum der Veröffentlichung.** Änderungen dieser Datenschutzerklärung bleiben vorbehalten.

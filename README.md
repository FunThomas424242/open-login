# open-login
Konzept einer sicheren Zugangsprüfung für Anwendungen - Zielgruppe Open Source Entwickler (Web &amp; App)

## Ziele des Konzeptes
* Bequeme Nutzung sicherer Passwörter durch Endnutzer 
* Schutz vor Ausspähen der Nutzerdaten (nicht der Passwörter)
* Schutz vor Ausspähen der Passwörter (z.B. im Rahmen von Datenklau) auf dem Server oder in der Anwendung
* Schutz vor Ableiten des Masterpasswortes oder anderer abgeleiteter Passwörter

## Realisierung und Umsetzung der Ziele
* Bequeme Nutzung sicherer Passwörter durch Endnutzer wird dadurch erreicht, dass der Nutzer sich nur ein wirklich gutes, sehr sicheres Passwort merken muss + einiger nicht schützenswerter Zusatzinfos (Loginname, Webseite, Zähler)
* Schutz vor Ausspähen der Nutzerdaten (nicht der Passwörter) durch verschlüsselte Ablage der Nutzerdaten auf dem Server oder in der App
* Schutz vor Ausspähen der Passwörter (z.B. im Rahmen von Datenklau) auf dem Server oder in der Anwendung, wird gewährleistet in dem kein Passwort auf dem Server oder in der App gespeichert wird.
* Schutz vor Ableiten des Masterpasswortes oder anderer abgeleiteter Passwörter, wird gewährleistet durch Nutzung kryptographischer Funktionen wie PBKDF2.

## Quellen im Netz

* Konzept für Nuzer beschrieben: heise.de in der ct18'2014 https://www.heise.de/ct/ausgabe/2014-18-Ein-neues-Konzept-fuer-den-Umgang-mit-Passwoertern-2284364.html

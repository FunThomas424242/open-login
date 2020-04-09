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

## Bekannte Schwachstellen
* Das Masterpasswort muss über einen sicheren Kanal in die Anwendung eingegeben werden. Im Web wäre das also TLS/HTTPS, auf dem lokalen Gerät werden Eingabeverfahren benötigt, die gegen Keylogger wirken z.B. Bildschirmtastatur mit zufälliger Anordnung gern auch kombiniert über mehrere Ebenen umschaltbar. Es spricht nix dagegen dies auch online zu nutzen. 

## Allgemeine Erläuterungen zum Konzept
Das Konzept beschreibt den Aufbau eines Zugangskontrollmoduls wie es in Web-, Desktop- oder Mobilanwendungen eingesetzt werden kann.  

## Schematische Darstellung des Zugangsmoduls
![Schematische Darstellung des Zugangskontrollmoduls als SVG](img/Zugangskontrollmodul.svg "Zugangskontrollmodul (schematisch)")

## Unterstützte Abläufe
### Authentifizierung gegenüber dem System (Webseite, App)
Es wird eine initiale Einrichtung durchgeführt. Diese wird durch Eingabe des Loginnamens ausgelöst aber nur wenn der Loginname noch nicht vergeben ist. Anderenfalls wird in den normalen Loginprozess verzeigt. Bei dieser initialen Einrichtung ist, wie später auch der Masterkey einzugeben und das Keyfile auszuwählen (URL=webseite, Loginname und Zähler=0 sind dem System bekannt). Damit wird das Set an Passwörtern generiert und steht zur Verfügung. Damit der Account als vergeben registriert wird, muss eine Challenge nebst Antwort verschlüsselt abgelegt werden. Bei einem späteren Loginversuch sind wieder Loginname, Masterkey und Keyfile anzugeben. Sind es die richtigen, kann die Challenge entschlüsselt und dem Nutzer angezeigt werden. Gibt der Nutzer die richtige Antwort der Challenge ein, gilt er als authentifiziert. Als Variation kann die Antwort auch entfallen und durch ein Prüfverfahren ersetzt werden z.B. Addition. Dann sind nur einige (vom Nutzer definierte) Zahlen als Challenge zu speichern und die Antwort kann vom System zur Kontrolle errechnet werden. 
### Passwortwechsel 
Der Nutzer erhöht den Zähler
### Passwortwiederherstellen
? -> ist das überhaupt noch notwendig?
### Masterkeywechsel
? -> vermutlich viel Aufwand für die Anwendungslogik


## Quellen im Netz

* Konzept für Nuzer beschrieben: heise.de in der ct18'2014 https://www.heise.de/ct/ausgabe/2014-18-Ein-neues-Konzept-fuer-den-Umgang-mit-Passwoertern-2284364.html

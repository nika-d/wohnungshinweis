
## Helfer für die Wohnungssuche

Dieses Tool hier macht das, was ich an der Wohnungssuche in Berlin am nervigsten finde: 

1. Die Seiten ImmobilienScout24, ImmoWelt, ImmoNet und Ebay Kleinanzeigen alle 3 Minuten neu laden. 
2. Gucken, ob ein neues angebot da ist. 
3. Falls ja, mir einen Hinweis geben (Sprachausgabe der jeweiligen Wohnungsbörse, also z.B. "Immo Scout", wenn dort ein neues Angebot ist).

Wenn ich diesen Hinweis höre, weiß ich, jetzt sollte ich mal auf die Wohnungsbörse gucken, was es neues gibt. Auf diese Art erfahre ich von neuen Angeboten viel schneller, als durch die Mail-Benachrichtigungen. 

Nachteil: Die App arbeitet mit Screenshots. D.h. so lange die App läuft und nach neuen Wohnungsangeboten sucht, kannst du deinen Bildschirm, und somit deinen Rechner nicht verwenden. (Bzw. du kannst schon, aber die App wird immer wieder Safari in den Vordergrund schieben.)

## Wie benutzt man das? 

Erst unten bei den System-Voraussetzungen gucken, obs für Dich überhaupt geeignet ist.

Neues Verzeichnis auf dem Desktop anlegen, es soll "automator" heißen. Alles aus diesem Repo runterladen und dort ablegen. Jetzt müsste z.B. diese Datei hier da sein: ~/Desktop/automator/myscript . 

Ggf. deine eigenen Einstellungen machen, siehe ebenfalls bei System-Voraussetzungen. 

Nachdem alle Einstellungen gemacht sind, Automator öffnen, die App "Neuladen und Gleichheit feststellen.app" öffnen und ausführen. Jetzt ist dein Rechner beschäftigt - etwas anderes nebenbei machen wird nicht gehen, weil die App den Bildschirm braucht. 

## System-Voraussetzungen: Mac

Ich hab einen Mac (aktuell BigSur 11.2.2), und da das hier auf Automator-Workflows beruht, funktionierts auch nur für Macs. Sorry alle anderen! Vielleicht inspiriert euch die allgemeine Beschreibung oben dazu, sowas auch für euer Gerät/Betriebssystem zu erstellen.

#### Ein paar allgemeine Einstellungen

Unter Systemeinstellungen -> Ton die "Toneffekte der Benutzeroberfläche" deaktivieren, damit nicht mehr bei jedem Screenshot das typische Screenshot-Geräusch zu hören ist. 

Safari als Standard-Browser festlegen. 

Adblock-Erweiterung für Safari installieren. Es ist nicht wichtig, welchen Ad-Blocker du installierst, nur, dass du keine Werbung siehst, wenn du z.B. auf Ebay Kleinanzeigen gehst. Die Werbung 

Falls Accounts für die Wohnungsbörsen vorhanden sind, dort anmelden und angemeldet bleiben.  

#### Automator 

Automator solltest du schon mal benutzt haben weil Du gleich Einstellungen machen musst mit Automator. Ist aber echt nicht schwierig. Nette, kurze Einführung, z.B. hier: https://www.macwelt.de/a/download-ordner-am-mac-mit-automator-aufraeumen-und-sauber-halten,3438436 

#### Die richtigen URLs einstellen

Alle Wohnungsbörsen, die ich benutze, haben alle Sucheinstellungen (Ort, max. Miete, min. Größe der Wohnung usw.) in der URL, die aufgerufen wird, wenn man auf "Suchen" klickt. Also einfach die Sucheinstellungen auf der jeweiligen Seite machen, so wie immer. 

Dann die URL kopieren, die werden wir gleich brauchen. 

Automator öffnen, und diese beiden Tools: 
- in App "Bilder reinitialisieren.app" 
- in Workflow "seiten aufrufen.workflow"

Jetzt die eben kopierte URL jeweils im Schritt "Angegebene URLs abfragen" einfügen. 

#### Die richtigen Datei-Pfade einstellen

Bitte gehe alle Apps und Workflows ein mal gründlich in Automator durch, und überprüfe für jeden Arbeitsschritt, ob er eine Datei erwartet / enthält, und falls ja, ob der Pfad richtig gesetzt ist. Es kann gut sein, dass ich meine lokalen Pfade drinstehen habe - dann wird es für dich nicht funktionieren. 

## ImageMagick ist cool! 

Um zu erkennen, ob ein neues Angebot da ist, vergleicht ein Script einen früheren Screenshot mit einem neueren. Nutze ich in einem Script ImageMagick, super gute, Apache 2 lizenzierte CLI tools für Bilder: https://imagemagick.org , https://github.com/ImageMagick . 

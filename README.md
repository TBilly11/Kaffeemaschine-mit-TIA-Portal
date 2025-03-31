# Kaffeemaschine-mit-TIA-Portal
# Datenübertragung zwischen einem ESP32-Microcontoller und einer Webanwendung  mittels HTTP-Anfragen
<h1>1 Projektspräsentation</h1>


<h1> 2 Einzelsteuerung </h1>
 - Die Anlage wird in Betrieb gesetzt, indem der Taster S5 betätigt wird, simuliert
 dieser den Einwurf einer Münze.
 - Der Benutzer hat nachher die Möglichkeit, mit den tastenden Schaltern zwischen
 den Getränken Kaffee S1 oder Tee S2 zu wählen.
 - Nach der Getränkewahl besteht die Möglichkeit zwischen den verschiedenen
 Zutaten wie Milch S4, Zucker S3 oder einfach nur das gewählte Getränk zu
 entscheiden, wobei diese in einer stufenweisen Auswahl in der Intensität variiert
 werden können. Der Taster S6 wird gedrückt, falls keinen Zusatzauswahl gebraucht
 wird.
 - Die jeweilige Auswahl wird durch das Anleuchten der entsprechenden
 Signallampen H1 (Kaffee), H2 (Tee), H3 (Zucker), H4 (Milch) oder H6 (kein
 Zusatzauswahl) bestätigt.
 - Die Anzeige H7 simuliert für 10 Sekunden die Bereitstellung eines Bechers für das
 ausgewählte Getränk, wobei dieses innerhalb weiterer 10 Sekunden zubereitet
 wird.
 - Die Becherbereitstellung wird mit einer Verzögerungszeit simuliert und der Füll
 vorgang darf erst nach dieser Zeit beginnen. Der Füllvorgang ist beendet, wenn der
 Sensor B1 betätigt wurde. Damit der Betreiber eine Übersicht wie viele Kunden
 bisher bedient wurden, wird zusätzlich ein interner Bezugszähler um eins erhöht.
 Sobald der Becher mit dem fertigen Getränk entnommen wurde – was mit dem
 Sensor B2 simuliert wird – ist der gesamte Vorgang beendet.
 - Abschließend wird wieder in den Bereitschaftsmodus H5 signalisiert und alle
 Komponenten (Signallampen, Ventile usw.) werden in den Ausgangszustand
 gebracht, so dass der nächste Benutzer nach erneutem Einwurf einer Münze ein
 neues Getränk wählen kann.

<h2> 2.1 Software</h2>
<h3> 2.1.1 Arduino IDE</h3>
<br />
<br />
<img src="https://i.imgur.com/tstUSon.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<h3> 2.1.2 Python-Django</h3>
<br />
<br />
<img src="https://i.imgur.com/0gpaPQc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<h3>2.1.3.Visual Studio Code</h3>
<br />
<br />
<img src="https://i.imgur.com/vLczaGc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h3>2.1.4 Windows PowerShell</h3>
<br />
<br />
<img src="https://i.imgur.com/swHorZU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />


<h2> 2.2 Hardware</h2>
<h3> 2.2.1 ESP 32</h3>
<br />
<br />
<img src="https://i.imgur.com/PPFy0hz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

<h3>  2.2.2 RC522 RFID-Modul</h3>
<br />
<br />
<img src="https://i.imgur.com/ELRIocU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

<h3>  2.2.3 LCD Touchscreen 2.8inch SPI Module ILI9341</h3>
<br />
<br />
<img src="https://i.imgur.com/KETXBVF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

<h3>   2.2.4 Micro Servo 9G (SG90)</h3>
<br />
<br />
<img src="https://i.imgur.com/nnj8yPk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
<h2> 3 Programmablauf</h2>
 Wird das Programm gestartet, 
<br />
<br />
<img src="https://i.imgur.com/kapRb6c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />


<h2> Aufbau</h2>
<br />
<p align="center">
  <img src="https://i.imgur.com/a78HhZL.jpeg" width="800" />
  <img src="https://i.imgur.com/7A9rFIG.jpeg" width="800" />
</p>

<br />
<br />
<h2> Einlogen-Seite</h2>
Das Web-Interface soll durch Benutzername und Passwort geschützt sein. Der Zugang soll auf Administratoren beschränkt sein.
<br />
<br />
<img src="https://i.imgur.com/jcRT7aK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h2>Die Hauptseite</h2>
Die Web-Interface wurde realisiert, der Admin kann Benutzer eintragen bzw. löschen. Es ist außerdem möglich, eingetragene Benutzer zu editieren. Eingetragene Benutzer sind persistent gespeichert , d.h. bei einem Stromausfall bleiben alle Daten erhalten.
<br />
<br />
<img src="https://i.imgur.com/dNDweek.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h2>Protokoll-Seite</h2>
Die Implementierung des Türprotokollierungssystems wurde erfolgreich abgeschlossen. Bei jeder Türöffnung werden nun der Benutzername, das Datum, die Uhrzeit sowie das verwendete Authentifizierungsverfahren protokolliert. Das Protokoll verfügt über eine einstellbare Länge; sobald die maximale Anzahl an Einträgen erreicht wird, werden die ältesten automatisch gelöscht. Zudem kann das Protokoll über das Benutzerinterface eingesehen werden.
<br />
<br />
<img src="https://i.imgur.com/eRvtwsB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

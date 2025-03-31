# Kaffeemaschine-mit-TIA-Portal
<h1>1 Projektspräsentation</h1>

<br />
<img src="https://i.imgur.com/XZz4xx2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 In diesem Projekt aus dem Sommersemester 2021 handelt 
 mit der strukturierten Planung einer vorhandenen Anlage ggf. eine Kaffeemaschine.
 Die Industrie wird immer flexibler, nachhaltiger, genauer und gewinnorientierter.
 Dabei ist es wichtig mit Präzision und möglichst ressourceneffizient zu arbeiten.Es
 ist wichtig, dass der meiste Aufwand einer Anlagenplanung ein vernünftiges
 Konzept wird, mit welchem es jedem ausgebildeten Ingenieur oder eine andere
 qualifizierte Person in der Lage ist, einen Getränkeautomaten zu programmieren
 und diesen als fertiges Produkt umzusetzen.


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


<h2>3 Use Case Diagramm</h2>
<br />
<br />
<img src="https://i.imgur.com/pbcl3LT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<h2>3 Zustandsdiagramm </h2>
Das Automat startet erst nach dem Münzeneinwurf (S5: = TRUE) und danach 
kann man die verschiedene Kombination der Getränke auswählen.


- S1 = false & S2 = true (Teeauswahl);
- S1 = true & S2 = false (Kaffeeauswahl);  
- S1 = false & S2 = true & S3 = True (Tee mit Zucker); 
- S1 = false & S2 = true & S4= True (Tee mit Milch); 
- S1 = false & S2 = true & S3 = True & S4= True (Tee mit Zucker und Milch);  
- S1 = true & S2 = false & S3= True (Kaffee mit Zucker); 
- S1 = true & S2 = false & S4= True (Kaffee mit Milch);  
- S1 = true & S2 = false & S3= True & S4=True (Kaffee mit Zucker und Milch);


Es muss nicht möglich sein Tee und Kaffee gleichzeitig auszuwählen. Nach der 
Auswahl des Getränks mit oder ohne die gewünschten Zutaten, gibt es eine 
Verzögerungszeit (3s), die wird mit einem TON realisiert. Danach gibt es der 
Füllvorgang (K2=TRUE) während des Füllvorgangs muss kein weitere Auswähle 
gemacht werden können darüber hinaus wird eine Mechanik aktiv sein um die 
Becherentnahme während des Füllvorgangs zu verhindern. Erst nach dem 
Füllvorgang kann den Becher entnommen werden und die Kundenanzahl wird 
inkrementiert.
<br />
<br />
<img src="https://i.imgur.com/liCgTHa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<h2>4 Datenmodell</h2>
<br />
<br />
<img src="https://i.imgur.com/JklsAg5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/W584ct6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />


<h2>5  Hauptfunktion in Strukturierter Text </h2>
<br />
<br />

<img src="https://i.imgur.com/oPALMGE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/XMBI50N.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/yZjKHUv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 

<img src="https://i.imgur.com/AkVbZaK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/2t2ftdd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/WMiPDC5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/wpZOGJh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

<h2>6 Hauptprogrammbaustein</h2>
<br />
<br />
<img src="https://i.imgur.com/dmd6wIp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 


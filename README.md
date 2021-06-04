# Snakegame

Snake als 2D Spiel

# Spiel inhalt: 
	- Schlange startet an zufälliger Position
	- Apfel spawnt immer wieder neu an zufälliger Position (nicht auf Schlange) 
	- Schlange muss Äpfel essen und wird dadurch 1 Längeneinheit größer
	- Wenn Schlange sich selber oder den Rand der Karte berührt ist das Spiel verloren
	- Gewonnen hat man, wenn die Schlange das komplette Spielfeld ausfüllt

später:
	- mehrere Level (verschiedene Formen)
	- eigene Level einfügen (.txt im Ordner ablegen) 
	- 

Darstellung des Spieles druch javax.swing 

# Klassen:
	(Emmely) Spielstart
		- Von hieraus startet das Spiel und wird per Menü gesteuert
	(alle) Spielfeld
		- aktuelles Spielfeld, aktualisiert das Spielfeld und läd die richtige Map
		- Größe abhängig von Äpfel (Spielfeldgröße-1 = Maximale Äpfel)
	(Emmely) Spiel
		- aktuelles Spielverhalten
		- besteht aus Vierecken
		- Bewegung: letztes viereck gelöscht, neues Viereck an der gewünschten Laufrichung erstellen
	
	(Marvin) Steuerung
		- Schlange kann nur nach links oder rechts gesteuert werden
		- Schlange bewegt sich automatisch taktgesteuert nach vorne um 1 feld
	(David) Takt	
		- Reihenfolge: 
				1. Abfrage Richtungswechsel (Zeitliche angabe, "auf Eingabe warten" //Zeit bei Richtungswechsel bestimmt die Spielgeschwindigkeit
				2. Collision Abfrage (bezogen auf aktuelle Richtung)
				3. Schritt in Wichtungswechsel (oder gerade aus, bei Richtungswechsel NULL)
				4. prüfen auf Schlange "alive" (false z.B. bei Schlange beißt sich selber, Schlange geht gegen Rand)
				5. ggf. Scoreboard aktualisieren (bei Apfel gegessen Punkte +1) 
	(Marvin) Schlange
		- Schlange, wird von Spieler gesteuert
	(Emmely) Apfel
		- Spawnt zufällig auf Spielfeld und kann gegessen werden
	(Marvin/David) Scoreboard 
		- Zeigt die Anzahl der gegessenen Äpfel an
	(Daivd) CollisionSystem
		- reagiert auf Kolisionsereignise mit Schlange<->Spielfeldrand, Schlange<->Apfel oder 	Schlange<->Schlange
    ###############################################################################################################################

# später
	MapLoader 
		- Liest aus einer Textdatei z.B. # oder P um die Spielfeld aufzubauen
		- soll das MapDesigning einfacher machen
# Lebenslauf
## WiIng
- interesse automatische datenverarbeitung und regelungstechnik
- nebenbei noch weiter et module aus dem bereich signalverarbeitung gehoert
- Abschlussarbeit: automatische verarbeitung von Messdaten
	- zeitreihen von kraft und verschiebungssensoren
	- software um aus den Zeitreihen materialeigenschaften abzuleiten
## Informatik min Mathe Nebenfach
- ich wussete schon dass ich in den data science bereich will
- daher moeglichst viele Mathe grundlagen aus Statistik, Optimierung und Numerik
- und Infiormatik module aus Bereich Machine learning und data mining
## Abschlussarbeit: domain adapation im autonomen Fahren
- erster schritt: training von deep learning modell das objekte auf bildern von Verkehrssituationen erkennt
- gute model performance auf daten die genau so sind wie trainingsdaten 
- domain shift = andere situationen wie in den trainingsdaten fuehrt zu schlechterer abnahme der performance
	- andere lichtverhaltnisse
	- regen
	- anderes land
- fokus der arbeit: methoden zur kompensation der domainverschiebung ohne dass neues trainingsdaten erforderlich sind
- selftraining, adversarial attacks, entropie minimierung, gewichtsregularisierung
## 2021 einstieg New Yorker als Data Scientist
- arbeit im distibutionprojekt: zustendig optimierung der gesamten warenfluesse vom zentrallager in die filiallen
- Datenpipeline in production die jeder Nacht vollautomatisiert ueber die gesammte zuteilung der ware entscheidet
	- pyspark pipeline: erhalt daten direkt aus dem ERP system berechnet die zuteilung und schickt die daten per API zurueck ans ERP system
	- hohe ausfallsicherheit (kosten bei ausfall bis zu 1 mio)
## Fokus meiner Arbeit: bauen von system zur demand vorhersage
- backtesting: lineare ganzzahlige optimieren: wie hoch waere gewinnpotential mit perfekter information (6 bis 7 % mehr umsatz und mehr marge)
- proof of concept fuer demand vorhersage
	- testen weche daten eigenen sich zur demand und wie muessen die daten vorbereitet werden vorhersage
	- welche models funktionieren gut (random forrest, gradient boosted trees, deep learning)
	- simulation der ergebnisse (3 % mehr umsatz und mehr marge)
- bau des vorhersage systems
	- daten:
		- produkteigeschaften wie warengruppe und farbe (tabular data)
		- verkaeufe der vergangenheit als Zeitreihe
		- image embeddings (vektor der die vosuellen eigenschaft der produktbilder beschreibt)
	- bei einer pipeline zur datenvorbereitung (hauptarbeit)
	- training von deep lerning model zur vorhersage von demand quantieles
		- quantile regression: statt point estimate (wie beispielsweise vorhersage des erwartungswert) vorhersage von verschieden quantielen der Nachfrage verteilung

# Warum Audi
- vereint viele Themen die mich sehr interessieren:
	- Autonomes Fahren
		- grosses interesse fuer Autonomes Fahren insbesondere nach abschlussarbeit
		- schluesseltechnologie fuer Automobielindustrie an der ich gerne mitarbeiten wuerde
	- vereint ingenieur themen wie mit klassischen data science themen wie statistik, machine learning und datenverarbeitung
- Neu aufgebautes projekt: von anfang mitgestalten des projekts
- Arbeit in automobilel industrie

# Warum welchsel?
- seit chef vor 6 montagen zu meta gewechselt
	- mehrmaliger managemnent wwechsel
	- immer neue roadmaps
	- allgemein zukunft ungewiss
	→ Suche nach mehr bestaendigkeit  
- guter Zeitpunkt fuer wechsel in projekt da abschlossene projekt phase
- keine remote arbeit
- Auto pefekte Stelle (will in automobies indulstrie)
- grobes Vorgehen
	- Parser für OWL-Dokumente, Tokens generieren
	- einzelne Tokens auf semantische Äquivalenz überprüfen
		- NLP nutzen, entweder Vorarbeit oder eigenes kleines Netz trainieren für bestimmte Testfälle (Achtung, das hier ist eine BA und keine Dissertation, klein halten)
		- vorhandene Open Source Matcher nutzen (z.B. https://github.com/ernestojimenezruiz/logmap-matcher)
		- Axiome aufbauen und Ableitungsregeln verwenden (muss schauen wir schwierig das genau wird, wirkt wie umfangreiche manuelle arbeit)
	- Ergebnis anhand Referenzalignments benchmarken


- sehr fixe Idee: Matching Problem auf SAT-Problem reduzieren, "Mapping Ontologies using SAT Solvers"
	- nicht in dieser BA, aber wäre mal einen Versuch wert in der Zukunft
- sehr fixe Idee (könnte Spaß machen): Crowdsourcing für den Aufbau eines Referenzalignments nutzen
	- Ergebnispräsentation am Ende der BA für Interessierte bereitstellen, falls es wirklich funktioniert
	- Anwendungsdomäne Industrie 4.0 schränkt Zielgruppe für Crowdsourcing erheblich ein 
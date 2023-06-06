Zusammenfassung *Ontology Matching: State of the Art and Future Challenges* [[Literatur|(1)]]

**Einführung**
- Umgang mit Uneindeutigkeit und Ambiguität bei Interpretation von domänenspezifischen Inhalten ist wachsendes Forschungsgebiet
- Ansatz über Ontology Matching
	- Ontologie ist Vokabular zur syntaktischen und semantischen Beschreibung einer Domäne
	- Beschreibung des Vokabulars in OWL
- semantische Heterogenität durch Maschinen erfassbar machen
	- semantisch äquivalente Entitäten erkennen und einander zuordnen
	- Übersetzung der Entitäten
- deutliche Verbesserungen über die letzten Jahre (Stand 2013), Entwicklungskurve flacht ab
- um dieser Entwicklung entgegenzuwirken, 8 grundlegende Herausforderungen beim Ontology Matching adressieren
	- Skalierbarkeit von Referenzalignements
	- Effizienz
	- Matching unter Berücksichtigung von weiterem Hintergrundwissen
	- Auswahl, Anpassung und Kombination von Matching-Tools
	- Nutzereinbindung
	- Ergebnisevaluation
	- Soziales Matching
	- Infrastruktur zur Verwaltung von Alignments

**Inhaltliche Einführung Ontology Matching**
![[Beispiel_Alignment.png]]
- Ontologien $O_1$ und $O_2$ mit Klassen und Attributen
	- jeder Eintrag wird allgemein als Entität bezeichnet
	- Buch ist Subklasse von Produkt 
- Korrespondenzen zwischen semantisch äquivalenten Klassen blau gezeichnet
	- Teilmengenbeziehung für jede Korrespondenz gegeben
- Menge aller Korrespondenz ist das Alignment
	- Wörterbuch, das Vokabeln der einen Domäne in andere Domäne übersetzen kann
- Eingabe für Ontology Matching Problem sind also zwei Ontologien $O_1$ und $O_2$, Ausgabe ist ein Alignment $A$
	- Variation mit $A^{\prime}$ als zusätzlichem Eingabeparameter, zu erweiterndes Alignment
*Anmerkung für schriftliche Version: Formale Einführung Alignment und Ontology Matching Problem*

**Anwendungsbeispiele von Matching Services** 
- Matching zwischen Thesauri (Def: Zusammenstellung von Begriffen eines Fachgebietes)
	- Iconclass und Aria, zwei Thesauri des Rijksmuseums in Amsterdam
	- Labels für die Kunstwerke, verschiedene Formate und Stile
	- Matching der Labels, einheitlicher und paralleler Zugriff auf beide Thesauri 
- Matching von Geoinformationen
	- hydrografische Karte und topologische Karte zusammensetzen

**Umsetzungsbeispiele von Matching Services**
- die folgende Tabelle enthält einige Beispiele für Matching Services, die in der Praxis verwendet werden
	- erste Hälfte der Tabelle enthält allgemeine Informationen 
	- zweite Hälfte der Tabelle beschreibt die verschiedenen Matching Methoden
		- terminologische Methoden arbeiten auf Strings
			- Labels
			- Kommentare
		- strukturelle Methoden nutzen weitere Modellierungseigenschaften einer OWL-Ontologie
			- Attribute
			- Klassen
			- Typen
			- Relationen
		-  instanzbasierte Methoden funktionieren auf konkreten Daten
			- Gegensatz zu strukturellen Methoden, welche lediglich Schemata (Def: formale Beschreibung eines Datensatzes, siehe Abbildung 1) nutzen
		- semantische Methoden basieren auf gesamten Eingabemodellen
		
| System | Domäne | Output || terminologisch | strukturell | instanzbasiert | semantisch |
| ---------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- |
| SAMBO | Biomedizintechnik| 1:1 Alignment || N-Grams, Levenshtein-Distanz, UMLS[^1], WordNet[^2] | iterative strukturelle Ähnlichkeit durch is-a und part-of Hierarchien | Naive Bayes |
| Falcon | generisch | 1:1 Alignment || I-SUB, V-Doc[^3]| strukturelle Ähnlichkeiten, Clusteranalyse, GMO[^4]| Objektähnlichkeit |
| DSsim | generisch | 1:1 Alignment || Tokenisierung
| RiMOM | generisch | 1:1 Alignment ||  Levenshtein-Distanz, Vektordistanz, WordNet | Affinity-Propagation | Vektordistanz | 
| ASMOV | Bioinformatik | 1:1 Alignment ||
| Anchor-Flood | generisch | 1:1 Alignment ||
| [AgreementMaker](https://github.com/agreementmaker/agreementmaker) | generisch| n:m Alignment ||

[^1]: Unified Medical Language System, Projekt zur Angleichung von medizinischen Wörterbüchern
[^2]: Wortnetz der englischen Sprache
[^3]: Linguistic Matcher
[^4]: Iterative Structural Matcher

**Benchmarks**
![[eval.png]]
- Vergleich führender Matching Tools durch die Ontology Alignment Evaluation Initiative (OAEI) jährlich durchgeführt
- Qualität Ergebnisse anhand von drei Faktoren bemessen
	- Precision (Präzision): Maß für die Korrektheit der Ergebnisse und somit für die Richtigkeit eines generierten Alignments
	- Recall (Abruf): Maß für die Vollständigkeit der Ergebnisse, wurden alle Korrespondenzen zwischen semantisch äquivalenten Klassen und Attributen erkannt
	- F-measure (F-Wert): zusammenfassender Wert für Precision und Recall
- Anwendungskontext ist das Matching literarischer Quellenangaben, Ergebnisskala von 0 bis 1 mit 1 als besten Wert
	- die Qualität der Ergebnisse ist mit Werten nahe der 1 konstant hoch
- weitere Testfälle für das Matching von Webverzeichnissen und das Matching von biomedizinischen Begriffen über die Anatomie des Menschen
- folgende Entwicklungen sind erkennbar
	- individuelle Systeme verbessern sich im Laufe der Jahre für die gleichen Testfälle
	- ein besseres Ergebnis für einen Testfall wird durchschnittlich nicht auf Kosten eines anderen Testfalls erreicht
	- die Tools haben für die betrachteten Testfälle in den letzten Jahren eine durchschnittliche Verbesserung von 108 Prozent erzielt
	- die Verbesserungsrate verlangsamt sich, messbarer Fortschritt stagniert mit der Zeit

**Skalierbarkeit von Referenzalignements**
- Matching-Tools müssen domänenspezifisch getestet werden, um die Qualität der Ergebnisse und somit die Praktikabilität einschätzen zu können
- zwei wichtige Ressourcen werden dabei benötigt
	- umfangreiche Testdatensätze
	- Referenzalignements mit verifizierter Korrektheit als Benchmark für die Ergebnisse eines Matching-Tools auf jedem Testdatensatz
- Datensätze mit bis zu 1.000.000 Entitäten pro Ontologie sehr groß
	- Testdaten müssen erhoben werden
	- Entwicklung eines Referenzalignements ist eine zeitaufwendige Aufgabe
-  Lösungsansätze für beide Problemstellungen und aktuelle Entwicklungen
	- Testdatensätze
		- OAEI-2008 und OAEI-2009 als Kampagnen zur Verknüpfung von bereits existierenden Ontologien entlang verschiedener Domänen
			- WordNet: lexikalische Datenbank
			- DBPedia: Wissensbasis Wikipedia
			- GTAA: Thesaurus für Fernsehprogramme
	- Referenzalignements
		- manuelle Zuordnung von Entitäten
		- semiautomatisches Matching, Zusammenspiel von Matching Tools und Menschen 

**Effizienz**
- Matching Tools müssen die Entitäten großer Ontologien in einem adäquaten Zeitraum verbinden können
- Laufzeit kann direkt durch Hardware verbessert werden
	- mehr Arbeitsspeicher und schnellere Prozessoren beschleunigen das Matching, Hardware ist aber häufig begrenzt
		- leistungsstärkere Komponenten
		- Verteilung einzelner Subaufgaben auf weitere Peers (Def: gleichwertiger Teilnehmer eines Rechennetzes, der Ressourcen oder Dienste mit anderen Teilnehmern austauscht)
	- Laufzeit sollte unabhängig der Hardware bemessen werden, Einführung einer Norm für Testhardware sinnvoll
- Effizienz der Software aufgrund begrenzter Hardwareressourcen in verschiedensten Anwendungsdomänen wichtig, mehrere Ansätze für Performanceoptimierung
	- parallelisieren der Berechnung von Korrespondenzen 
	- approximieren von Korrespondenzen
	- modularisieren von Ontologien
	- optimieren bestehender Algorithmen
*Anmerkung für schriftliche Version: Kurze Erwähnung der Komplexitätstheorie, oberer Grenzen und O-Notation* 

**Matching mit Hintergrundwissen**
- domänenspezifisches Hintergrundwissen kann die Qualität des Matchings verbessern
	- bereits vorhandenes Wissen nutzen und neues Wissen ableiten
	- manche Zusammenhänge nur mit Vorwissen erkennbar
- Hintergrundwissen unterschiedlich darstellbar, Darstellung muss in OWL übersetzt oder annotiert werden
	- Internetseiten
	- Bilder
- Recall wird auf Kosten der Precision erhöht, Abwägen der beiden Faktoren 

**Soziales Matching**
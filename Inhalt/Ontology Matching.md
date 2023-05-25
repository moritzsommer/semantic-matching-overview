Zusammenfassung *Ontology Matching: State of the Art and Future Challenges* [[Literatur|(1)]]

**Einführung:**
- Umgang mit Uneindeutigkeit und Ambiguität bei Interpretation von domänenspezifischen Inhalten ist wachsendes Forschungsgebiet
- Ansatz über Ontology Matching
	- Ontologie ist Vokabular zur syntaktischen und semantischen Beschreibung einer Domäne
	- Beschreibung des Vokabulars in OWL
- semantische Heterogenität durch Maschinen erfassbar machen
	- semantisch äquivalente Entitäten erkennen und einander zuordnen
	- Übersetzung der Entitäten
- deutliche Verbesserungen über die letzten Jahre (Stand 2013), Entwicklungskurve flacht ab
- um dieser Entwicklung entgegenzuwirken, 8 grundlegende Herausforderungen beim Ontology Matching adressieren
	- Skalierbarkeit des Matchings
	- Effizienz
	- Matching unter Berücksichtigung von weiterem Hintergrundwissen
	- Auswahl, Anpassung und Kombination von Matching-Tools
	- Nutzereinbindung
	- Ergebnisevaluation, Erklärung des Resultates nach Matching
	- Soziales Matching
	- Infrastruktur zur Verwaltung von Alignments

**Inhaltliche Einführung Ontology Matching:**
![[Beispiel_Alignment.png]]
- Ontologien $O_1$ und $O_2$ mit eigenen Klassen und Attributen
	- Buch Subklasse von Produkt
- Korrespondenzen zwischen semantisch äquivalenten Klassen blau gezeichnet
	- Teilmengenbeziehung für jede Korrespondenz gegeben
- Menge aller Korrespondenz ist das Alignment
	- Analogie ist Wörterbuch, das Vokabeln der einen Domäne in andere Domäne übersetzen kann
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
- Die folgende Tabelle enthält einige Beispiel für Matching Services, die in der Praxis verwendet werden
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
			- Gegensatz zu strukturellen Methoden, welche lediglich Schemata (Def: formale Beschreibung der Struktur von Daten) nutzen
		- semantische Methoden basieren auf gesamten Eingabemodellen
		
| System | Domäne | Output || terminologisch | strukturell | instanzbasiert | semantisch |
| ---------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- |
| SAMBO | Biomedizintechnik| 1:1 Alignment || N-Grams, Levenshtein-Distanz, UMLS[^1], WordNet[^2] | iterative strukturelle Ähnlichkeit durch is-a und part-of Hierarchien | Naive Bayes
| Falcon | generisch | 1:1 Alignment || I-SUB, V-Doc[^3]| strukturelle Ähnlichkeiten, Clusteranalyse, GMO[^4]| Objektähnlichkeit
| DSsim | generisch | 1:1 Alignment ||
| RiMOM | generisch | 1:1 Alignment ||  Levenshtein-Distanz, Vektordistanz, WordNet | Affinity-Propagation | Vektordistanz 
| ASMOV | Bioinformatik | 1:1 Alignment ||
| Anchor-Flood | generisch | 1:1 Alignment ||
| [AgreementMaker](https://github.com/agreementmaker/agreementmaker) | generisch| n:m Alignment ||

[^1]: Unified Medical Language System, Projekt zur Angleichung von medizinischen Wörterbüchern
[^2]: Wortnetz der englischen Sprache
[^3]: Linguistic Matcher
[^4]: Iterative Structural Matcher

**Benchmarks**
**Skalierbarkeit**
**Effizienz**
**Matching mit Hintergrundwissen**
**Soziales Matching**
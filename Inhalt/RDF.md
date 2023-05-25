Das Resource Description Framework (RDF) ist ein Standard des World Wide Web Consortiums (W3C) zur Darstellung von Informationen im Web. RDF ermöglicht die Beschreibung von Ressourcen und deren Beziehungen zueinander in einer maschinenlesbaren Form. Es stellt eine grundlegende Struktur zur Verfügung, um Wissen und Metadaten zu modellieren und auszutauschen.

Allgemein handelt es sich um ein standardisiertes Datenformat und kann auf verschiedenen Plattformen und Systemen verwendet werden. Die Plattformunabhängigkeit von RDF ermöglicht den Austausch und die Interoperabilität von Informationen zwischen verschiedenen Systemen, unabhängig von den verwendeten Technologien. RDF-Daten können mit verschiedenen Werkzeugen und Bibliotheken analysiert, abgefragt und verarbeitet werden, die die Standards und Spezifikationen des RDF-Frameworks unterstützen.

RDF wird in verschiedenen Bereichen eingesetzt, darunter Wissensrepräsentation, semantische Webtechnologien, Metadatenbeschreibung und semantische Webtechnologien. Es ermöglicht die Verknüpfung und Integration von Informationen aus unterschiedlichen Quellen, wodurch Zusammenhänge und Beziehungen zwischen Ressourcen im Web besser verstanden und genutzt werden können.

Das RDF-Datenmodell basiert auf dem Konzept von Tripeln, die aus Subjekt, Prädikat und Objekt bestehen. Diese Tripel repräsentieren Aussagen über Ressourcen im Web. Subjekt und Objekt werden durch Uniform Resource Identifiers (URIs) identifiziert, während das Prädikat die Art der Beziehung zwischen ihnen beschreibt. Häufig werden RDF-Datenmodelle als Graph dargestellt, die direkte Darstellung der Tripel mithilfe von XML ist aber ebenso geläufig. [[Literatur|(1)]]

![[RDF_Graph.png]]

```XML
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
		 xmlns:ex ="http://example.org/">
		 
	<rdf:Description rdf:about="http://example.org/SemanticWeb">
		<ex:VerlegtBei>
			<rdf:Description rdf:about="http://springer.com/Verlag">
			</rdf:Description>
		</ex:VerlegtBei>
	</rdf:Description>
	
</rdf:RDF>
```

*Anmerkung für schriftliche Version: Formale Semantik von RDF hier einführen, syntaktisches Schlussfolgern mit Ableitungsregeln*
Die Extensible Markup Language (XML) ist eine erweiterbare Auszeichnungssprache, die von der World Wide Web Consortium (W3C) entwickelt wurde. Sie ermöglicht es, hierarchisch strukturierte Daten einheitlich zu definieren und zu übertragen. XML wurde als plattformunabhängige und leicht erweiterbare Sprache entwickelt, die sowohl für Menschen als auch für Maschinen lesbar ist.

Ein Hauptvorteil von XML besteht darin, dass sie als plattformunabhängiges Format weit verbreitet ist und somit sich somit in viele Anwendungsdomänen etabliert hat. Die Sprache wird beispielsweise zur Speicherung und Abfrage von Informationen in einer Datenbank genutzt. Ein weiteres Anwendungsbeispiel sind Webanwendungen, bei denen XML als plattformunabhängiges Kommunikationstool zwischen verschiedenen Diensten verwendet wird.

Eine XML-Datei besteht aus markierten Elementen, die in einer hierarchischen Struktur angeordnet sind. Jedes Element besteht aus einem Starttag, einem Endtag und möglicherweise einem Inhalt oder anderen verschachtelten Elementen. Die Start- und Endtags sind in spitzen Klammern eingeschlossen.

```xml
<Person>
  <Name>Moritz Sommer</Name>
  <Age>21</Age>
  <University>RWTH Aachen</University>
  <ResidenceDistance>10 minutes away from the university</ResidenceDistance>
  <GameStats>
    <Game>
      <Title>Fortnite</Title>
      <Playtime>900 hours</Playtime>
    </Game>
    <Game>
      <Title>Minecraft</Title>
      <Playtime>3000 hours</Playtime>
    </Game>
    <Game>
      <Title>CSGO</Title>
      <Playtime>400 hours</Playtime>
    </Game>
  </GameStats>
  <PCSpecs>
    <GPU>1080ti</GPU>
    <CPU>I7 8700k</CPU>
    <RAM>16GB</RAM>
  </PCSpecs>
  <BestSkill>
    <TraitDescription>Being late for lectures despite living 10 minutes away from university</TraitDescription>
  </BestSkill>
</Person>
```
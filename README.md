# Supermarkt Sales Dashboard w/ Power BI

## Inhalt

[Hintergrund und Übersicht](#hintergrund-und-übersicht)

[Datenstruktur](#datenstruktur)

[Dashboards und Analysen](#dashboards-und-analysen)

[Annahmen und Vorbehalte](#annahmen-und-vorbehalte)

[Genutzte Kenntnisse](#genutzte-kenntnisse)

## Hintergrund und Übersicht

Dieses Projekt analysiert und visualisiert die Verkaufdaten eines chinesischen Supermarkts im Zeitraum 2020 bis 2023 - mit Fokus auf der Produktkategorie Gemüse. Das Unternehmen stellt ausführliche Daten zu Transaktionen, Preisen, Produktsortiment und Verlustraten zur Verfügung. Diese Informationen werden in diesem Projekt aufbereitet, analysiert und anhand der wichtigsten Kennzahlen übersichtlich dargestellt, um Vertriebs- und Produktverantwortlichen einen schnellen Einblick in aktuelle Entwicklungen und Optimierungspotenziale zu ermöglichen. Optional können Geldbeträge auf Basis historischer Wechselkurse in Euro dargestellt werden, um internationale Vergleiche zu ermöglichen.

Das Dashboard liefert insbesondere Einblicke in die folgenden Bereiche:
- **Aktueller Trend in KPIs**: Darstellung von KPIs mit Trend des letzten Monats für schnelle Einsicht in tägliche Veränderung

- **Historischer Verkaufstrend**: Historischer Verlauf von Verkaufszahlen und jährlicher Trend (zum Ausgleich üblicher saisonaler Fluktuation), fokussiert auf Umsatz, Menge und Verkaufspreis

- **Leistung auf Produktebene**: Leistung einzelner Produktkategorien mit herausstechenden Produkten, Profit, Marge und Rückgaberate sowie Verlauf von Preisen und Leistung

<br/><br/>
Ausführung der im Projekt genutzten Kenntnisse [hier](#genutzte-kenntnisse)  
Interaktive Dashboards und Einsicht in DAX-Code [hier](/Supermarket%20Dashboard.pbix)
<br/><br/>

## Datenstruktur

Die Daten des Unternehmens bestehen aus vier Tabellen: fSales, dLossRate, dPrice und dProducts. Hinzugefügt wurde eine Datumstabelle sowie eine Tabelle mit historischem Wechselkurs (RMB zu EUR). Die Transaktionstabelle enthält 878.503 Einträge.

![Datenmodell Dashborad](/Bilder/Dashboard%20ERD.png)




## Dashboards und Analysen

### Kurzzusammenfassung
Nach einem Peak im Februar 2021 verzeichnete das Unternehmen im zweiten Halbjahr 2021 einen Umsatzrückgang von 25% im Vergleich zum Vorjahr. Ab Mitte 2022 stabilisierte sich der Trend, mit einem erneuten Hoch im Januar 2023 und aktuell deutlich positiven Entwicklungen in mehreren KPIs wie Gewinn (+35%) und durchschnittlichem Einkaufswert (+38%). Der Absatzanstieg im zweiten Halbjahr 2022 wurde durch eine deutliche Preissenkung unterstützt. Weitere Einflussfaktoren wie saisonale Schwankungen, fluktuierende Einkaufspreise sowie kategoriespezifische Unterschiede werden im Folgenden detaillierter analysiert.

### Revenue Insights: Dashboard und Analyse

![Dashboard Revenue Insights](/Bilder/Snapshot%20Revenue%20Dashboard.png)
Dieses Dashboard bietet einen Überblick über zentrale KPIs und den jeweiligen YOY Trend basierend auf den letzten 30 Tagen. Es bietet zudem Einblick in Verkaufszahlen und Verkaufspreise über die Zeit. Die dritte Zeile zeigt die Leistung der verschiedenen Produktkategorien.
<br/><br/>

**Zeile 1: Aktuelle Trends in KPIs** 
- Der Umsatz zeigt aktuell eine Steigung von 35% und der durchschnittliche Einkaufswert ist ebenfalls um 38% zum Vorjahr gestiegen. Bei einer stabilen Transaktionsanzahl (-2%) ist dieser Anstieg auf um 13% höhere Produktpreise und ein gestiegenes Volumen pro Einkauf zurückzuführen.
<br/><br/>

**Zeile 2: Historischer Verkaufstrend** 
- Im Februar 2021 erreichten die Verkäufe mit 23T€ Umsatz bei 18T kg verkaufter Menge einen Hochpunkt, begleitet vom historisch höchsten Verkaufspreis von 1,73 €/kg. Dies folgt dem saisonalen Trend mit hohen Verkäufen zum Jahresanfang.

- Ab Juli 2021 fällt Umsatz im Jahresvergleich über zwölf Monate, insbesondere im 4. Quartal 2021 sank die verkaufte Menge entgegen dem saisonalen Trend. Im November 2021 wurden mit 8T € Umsatz und 6T kg Verkaufsmenge die niedrigsten Werte erzielt. Als Ursachen kommen höhere Preise sowie pandemiebedingte Restriktionen in Frage.

- Ab Juni 2022 steigt der monatliche Umsatz im Verleich zum Vorjahr kontinuierlich, mit einer Wiederherstellung des Umsatzniveaus von 2020 im Januar 2023 (23T€ Umsatz). Besonders im 3. und 4. Quartal 2022 stieg die Verkaufsmenge deutlich an (bis zu 23T kg im August), begleitet von einer Preissenkung von bis zu 41% im November 2022.
<br/><br/>

**Zeile 3: Leistung in Produktkategorien**
- In jedem Jahr zeigen sich die Kategorien Blattgemüse, Capsicum und essbare Pilze als größte Treiber des Umsatzes. Blattgemüse ist insgesamt mit 32% des Umsatzes und 42% der verkauften Menge jeweils führend, ist mit 0,86€ pro kg aber auch die preiswerteste Kategorie. Die Kategorie Solanum bleibt durchgängig die umsatzschwächste, hielt jedoch mit mindestens 4% einen konstanten Anteil an Umsatz und Absatz.
<br/><br/>

### Product Performance: Dashboard und Analyse
![Dashboard Product Insights](/Bilder/Snapshot%20Product%20Dashboard.png)

Dieses Dashboard ist für tiefere Einblicke in die Leistung einzelner Produktkategorien optimiert und liefert neben aktuellen Trends in Profit und Marge eine Übersicht über die saisonalen Verkaufszahlen sowie über Trends in Ein- und Verkaufspreisen. Das Sortiment kann anhand negativ und positiv herausstechender Produkte analysiert werden.
<br/><br/>

**Zeile 1: Aktuelle Trends in KPIs** 

- Der Profit (unter Berücksichtigung der Verlustraten) ist mit 22% schwächer gewachsen als der Umsatz, was zu einem Rückgang der Marge um 10% führt. Da die Verlustraten stabil sind, ist dies auf höhere Einkaufspreise zurückzuführen. Größter Treiber dieses Trend sind Wasserknollen, deren Marge um 51% gefallen ist - nach einem außergewöhnlich hohen Margenpeak im Vorjahr.

- Die Rückgaberaten sind insgesamt sehr niedrig und im Jahresvergleich weiter gesunken, was auf eine hohe Produktqualität hinweist. Die größte absolute Verbesserung wurde bei Wasserknollengemüsen erzielt, mit einem Rückgang um 0,11%.
<br/><br/>

**Zeile 2: Trend in monatlicher Leistung und Ein- und Verkaufspreisen**
- Die Verkaufsmenge weist einen klaren saisonalen Trend mit Spitzen im Herbst und Winter auf. Der Profit zeigt hingegen zum Jahresende einen Rückgang, der in 2020 auf gestiegene Einkaufspreise zurückzuführen ist, während er 2023 mit gesunkenen Verkaufspreisen einhergeht. Eine Umkehr der saisonalen Verkaufstrends zeigt sich nur in der Kategorie Solanum mit höherem Absatz im Sommer, während Verkäufe in der Kategorie Kohl und Blattgemüse keinem signifikanten saisonalen Trend folgen.

- Im Jahr 2023 sind Ein- und Verkaufspreise insgesamt stabil, mit leichten Abweichungen in einzelnen Produktkategorien. Auffällig sind steigende Ein- und Verkaufpreise bei Wasserknollen, während bei Capsicum die Verkaufspreise fallen.
<br/><br/>

**Zeile 3: Produktsortiment**
- Nachfrage und Profit in den Kategorien Solanum, Wasserknollengemüse und Kohl werden jeweils stark von einem Produkt dominiert. Hier besteht also eine hohe Abhängigkeit und die Leistung der Produktkategorie ist anfällig für Ausfälle.

- Im aktuellen Sortiment befinden sich in allen Produktkategorien Produkte mit sehr geringer Verkaufsmenge (unter 20kg pro Monat) und einem monatlichen Profit von unter 5€, die auf Wirtschaftlichkeit hin überprüft werden sollten.

- Alle Produkte mit negativem Deckungsbeitrag wurden bereits aus dem Sortiment genommen - mit der Ausnahme von Eisgras. Dies weist eine Verlustrate von über 10% auf und sollte hinsichtlich möglicher Ursachen wie Lagerbedingungen oder Kühlung näher untersucht werden.
<br/><br/>

## Annahmen und Vorbehalte
- **Aktualität der Daten**: Die Daten decken nur einen Zeitraum von ca. 3 Jahren ab und stammen nicht aus einer sich aktualisierenden Quelle. Daher basiert die Auswertung aktueller Trends auf Juni 2023. Der Vorteil täglicher Analyse des Trends der letzten 30 Tage kommt besonders bei häufig oder automatisch aktualisierter Datenquelle/Datenbank zum Vorschein. 

- **Einfuss der Pandemie**: Verkaufsdaten vor der Coronapandemie sind nicht inkludiert, weshalb eine Rückkehr zum Status davor nur schwer eingeschätzt werden kann. Zudem ist es ohne einen genauen Standort des Unternehmens nicht möglich, den Einfluss der mitunter sehr strengen regionalen Lockdowns in China auf das Kaufverhalten einzubeziehen.

- **Währungsumrechnung**: Die sichtbaren Trends hängen bei Umrechung in EUR auch von der Fluktuation des Wechselkurses vom RMB in Euro ab. Dies muss bei der Trendanalyse beachtet werden. Alle Metriken können aber in der Originalwährung betrachtet werden.

- **Verlustraten**: Die Verlustraten liegen nicht historisch vor und bieten damit nur einen groben Einblick in den durchschnittlichen Verlust pro Produkt.
<br/><br/>

## Genutzte Kenntnisse

- **Datentransformation (ETL) mit Power Query**: Änderung Datentypen, Erstellen Composite Key, Quelle zur historischen Währungstransformation integriert und angepasst

- **Datenmodellierung**: Erstellung eines effizienten Datenmodels im Sternschema

- **DAX**: Explizite Measures wie Gewinn, Profit und Marge im angemessenen Filterkontext mit zentralen DAX-Funktionen berechnen

- **Visualisierung und Dashboard Design**: Erstellen von KPI-Cards mit Trends, Tabellen, Diagrammen und bedingter Formatierung um wichtigste Kennzahlen übersichtlich darzustellen

- **Nutzerkontrolle**: Datenschnitte und Parameter zum Wählen von Kategorie, Zeit, Währung und Kennzahl
---
description: Erstellen und verwalten Sie die Eigenschaften oder Segmente, die bei der Look-alike-Modellierung verwendet werden.
keywords: relative Gewichtung, Look-alike
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: Über Look-alike-Modellierung
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 0%

---

# Grundlegendes zu [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Neue Benutzer mit [!UICONTROL Look-Alike Modeling] suchen {#find-new-users}

[!UICONTROL Look-Alike Modeling] hilft Ihnen bei der Erkennung neuer, eindeutiger Zielgruppen durch automatisierte Datenanalyse. Der Prozess beginnt, wenn Sie einen [!UICONTROL trait] oder [!UICONTROL segment], ein Zeitintervall sowie den Erstanbieter- und Drittanbieter-Wert [!UICONTROL data sources] auswählen. Ihre Auswahlmöglichkeiten bieten die Eingaben für das algorithmische Modell. Wenn der Analysevorgang ausgeführt wird, sucht er basierend auf gemeinsamen Merkmalen der ausgewählten Population nach infrage kommenden Benutzern. Nach Abschluss sind diese Daten in [Trait Builder](../../features/traits/about-trait-builder.md) verfügbar, wo Sie sie verwenden können, um Eigenschaften basierend auf der [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md) zu erstellen. Darüber hinaus können Sie Segmente erstellen, die algorithmische Eigenschaften mit [!UICONTROL rules-based traits] kombinieren und weitere Qualifizierungsanforderungen mit [!DNL Boolean] Ausdrücken und Vergleichsoperatoren hinzufügen. [!UICONTROL Look-Alike Modeling] gibt Ihnen eine dynamische Möglichkeit, Werte aus allen verfügbaren Eigenschaftsdaten zu extrahieren.

## Vorteile {#advantages}

Die wichtigsten Vorteile der Verwendung von [!UICONTROL Look-Alike Modeling] sind:

* **Datengenauigkeit:** Der Algorithmus wird regelmäßig ausgeführt, was dazu beiträgt, Ergebnisse auf dem neuesten Stand zu halten und relevant zu sein.
* **Automatisierung:** Sie müssen nicht viele statische Regeln verwalten. Der Algorithmus findet Zielgruppen für Sie.
* **Sparen Sie Zeit und reduzieren Sie den Aufwand:** Mit unserem Modellierungsprozess müssen Sie nicht erraten, was [!UICONTROL traits]/[!UICONTROL segments] möglicherweise funktioniert oder Zeitressourcen für Kampagnen verwendet, um neue Zielgruppen zu entdecken. Das Modell kann das für Sie tun.
* **Zuverlässigkeit:** Die Modellierung funktioniert mit serverseitigen Erkennungs- und Qualifizierungsprozessen, die Ihre eigenen Daten und ausgewählte Drittanbieterdaten auswerten, auf die Sie Zugriff haben. Das bedeutet, dass Sie die Besucher Ihrer Site nicht sehen müssen, um sie für eine Eigenschaft zu qualifizieren.

## Workflow {#workflow}

Sie verwalten Modelle in **[!UICONTROL Audience Data > Models]**. Auf hoher Ebene umfasst der Workflow-Prozess Folgendes:

* Wählen Sie die Basisdaten aus, die der Algorithmus auswerten soll. Dazu gehören [!UICONTROL trait] oder [!UICONTROL segment], der Zeitraum und [!UICONTROL data sources] (Ihre eigenen Daten und Drittanbieterdaten, auf die Sie bereits über [!DNL Audience Manager] Zugriff haben). Im Workflow zur Modellerstellung können Sie die [!UICONTROL traits] ausschließen, die Sie nicht in Ihr Modell eingreifen möchten.
* Speichern Sie Ihr Modell. Nach dem Speichern wird der algorithmische Evaluierungsprozess automatisch ausgeführt. Beachten Sie jedoch, dass es bis zu 7 Tage dauern kann, bis dieser Prozess abgeschlossen ist. [!DNL Audience Manager] sendet Ihnen eine E-Mail, wenn der Algorithmus abgeschlossen ist und Ergebnisse für die Erstellung von [!UICONTROL trait] verfügbar sind.
* Erstellen Sie algorithmische [!UICONTROL traits] in [!UICONTROL Trait Builder].
* Kombinieren Sie [!UICONTROL traits] in [!UICONTROL Segment Builder] zu [!UICONTROL segments].
* Erstellen und senden Sie [!UICONTROL segment] -Daten an eine [!UICONTROL destination].

## Fehlerbehebung {#troubleshooting}

Wir deaktivieren alle [!UICONTROL Look-Alike Model] , die keine Daten für drei aufeinander folgende Ausführungen generieren können. Beachten Sie, dass Sie den Status des Modells danach nicht wieder auf &quot;aktiv&quot;festlegen können. Um sicherzustellen, dass Ihre Modelle Daten generieren, empfehlen wir, Modelle aus Datenquellen mit genügend [!UICONTROL traits] zu erstellen, aus denen Daten gesammelt werden können.

## Grundlegendes zu [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] ist ein proprietärer Algorithmus, der entwickelt wurde, um neue [!UICONTROL traits] automatisch zu entdecken. Er vergleicht [!UICONTROL trait] Daten aus Ihrem aktuellen [!UICONTROL traits] und [!UICONTROL segments] mit allen anderen Erstanbieter- und Drittanbieterdaten, auf die Sie über [!DNL Audience Manager] zugreifen können. Eine Beschreibung des algorithmischen Erkennungsprozesses von [!UICONTROL TraitWeight] finden Sie in diesem Abschnitt .

![](assets/algo_model.png)

Die folgenden Schritte beschreiben den [!UICONTROL TraitWeight]-Evaluierungsprozess.

### Schritt 1: Erstellen einer Grundlinie für den Vergleich [!UICONTROL Trait]

Um eine Grundlinie zu erstellen, misst [!UICONTROL TraitWeight] alle mit einer Zielgruppe verbundenen [!UICONTROL traits] in einem Intervall von 30, 60 oder 90 Tagen. Als Nächstes wird [!UICONTROL traits] nach ihrer Häufigkeit und ihrer Korrelation sortiert. Die Häufigkeitszählung misst die Gemeinsamkeit. Korrelation misst die Wahrscheinlichkeit, dass ein [!UICONTROL trait] nur in der Zielgruppe der Grundlinie vorhanden ist. &quot;[!UICONTROL Traits]&quot;, die häufig vorkommen, weisen eine hohe Gemeinsamkeit auf, ein wichtiges Merkmal, das verwendet wird, um bei Kombination mit [!UICONTROL traits], das in Ihrem ausgewählten [!UICONTROL data sources] gefunden wird, einen gewichteten Wert festzulegen.

### Schritt 2: Derselbe [!UICONTROL Traits] im [!UICONTROL Data Source] finden

Nachdem er eine Grundlinie für den Vergleich erstellt hat, sucht der Algorithmus in Ihrem ausgewählten [!UICONTROL data sources] nach identischem [!UICONTROL traits] . In diesem Schritt führt [!UICONTROL TraitWeight] eine Frequenzanzahl aller entdeckten [!UICONTROL traits] durch und vergleicht sie mit der Grundlinie. Im Gegensatz zur Grundlinie sind die ungewöhnlichen [!UICONTROL traits] jedoch höher als die, die häufiger vorkommen. Selten [!UICONTROL traits] soll ein hohes Maß an Spezifität aufweisen. [!UICONTROL TraitWeight] bewertet Kombinationen der gemeinsamen Grundlinie [!UICONTROL traits] und der ungewöhnlichen (hochspezifischen) [!UICONTROL data source] [!UICONTROL traits] als einflussreicher oder wünschenswerter als [!UICONTROL traits], die beiden Datensätzen gemeinsam sind. In der Tat erkennt unser Modell diese großen, gemeinsamen [!UICONTROL traits] und weist Datensätzen mit hohen Korrelationen keine übermäßige Priorität zu. Selten [!UICONTROL traits] erhalten höhere Priorität, da sie mit höherer Wahrscheinlichkeit neue Unique Users darstellen als [!UICONTROL traits] mit hoher Gemeinsamkeit.

### Schritt 3: Gewichtung zuweisen

In diesem Schritt rangiert [!UICONTROL TraitWeight] neu entdeckte [!UICONTROL traits] in der Reihenfolge des Einflusses oder der Zweckmäßigkeit. Die Gewichtsskala ist ein Prozentsatz, der von 0 % bis 100 % reicht. [!UICONTROL Traits], der näher an 100 % liegt, bedeutet, dass sie eher der Zielgruppe in Ihrer Grundlinie ähneln. Außerdem sind stark gewichtete [!UICONTROL traits] nützlich, da sie neue Unique Users darstellen, die sich ähnlich wie Ihre etablierte, Baseline-Zielgruppe verhalten können. Beachten Sie, dass [!UICONTROL TraitWeight] [!UICONTROL traits] mit hoher Gemeinsamkeit im Ausgangswert und hoher Spezifität in den verglichenen Datenquellen als wertvoller betrachtet als [!UICONTROL traits], die in jedem Datensatz vorkommen.

### Schritt 4: Scoring-Benutzer

Jeder Benutzer in dem ausgewählten [!UICONTROL data sources] erhält eine Benutzerbewertung, die der Summe aller Gewichtungen des einflussreichen [!UICONTROL traits] für das Profil dieses Benutzers entspricht. Die Benutzerbewertungen werden dann zwischen 0 und 100 % normalisiert.

### Schritt 5: Anzeigen und Arbeiten mit Ergebnissen

[!DNL Audience Manager] zeigt Ihre gewichteten Modellergebnisse in [!UICONTROL Trait Builder] an. Wenn Sie einen [!UICONTROL algorithmic trait] erstellen möchten, können Sie mit [!UICONTROL Trait Builder] [!UICONTROL traits] auf der Grundlage des gewichteten Werts erstellen, der vom Algorithmus während einer Datenausführung generiert wurde. Sie können eine höhere Genauigkeit wählen, um nur Benutzer zu qualifizieren, die sehr hohe Benutzerbewertungen aufweisen und daher der Grundzielgruppe und nicht dem Rest der Zielgruppe sehr ähnlich sind. Wenn Sie eine größere Zielgruppe (Reichweite) erreichen möchten, können Sie die Genauigkeit verringern.

### Schritt 6: Die Bedeutung eines [!UICONTROL Trait] für alle Verarbeitungszyklen neu bewerten

In regelmäßigen Abständen bewertet [!UICONTROL TraitWeight] die Wichtigkeit eines [!UICONTROL trait] anhand der Größe und der Veränderung der Population dieses [!UICONTROL trait] neu. Dies geschieht, wenn sich die Anzahl der für diese [!UICONTROL trait] qualifizierten Benutzer im Laufe der Zeit erhöht oder verringert. Dieses Verhalten wird am deutlichsten in Eigenschaften beobachtet, die sehr groß werden. Angenommen, der Algorithmus verwendet [!UICONTROL trait A] für die Modellierung. Wenn die Population von [!UICONTROL trait A] zunimmt, bewertet [!UICONTROL TraitWeight] die Wichtigkeit dieses [!UICONTROL trait] erneut und kann einen niedrigeren Wert zuweisen oder ihn ignorieren. In diesem Fall ist [!UICONTROL trait A] zu häufig oder zu groß, um etwas Wichtiges über die Population zu sagen. Nachdem [!UICONTROL TraitWeight] den Wert von [!UICONTROL trait A] verringert (oder ihn im Modell ignoriert) hat, nimmt die Population der algorithmischen Eigenschaft ab. Die einflussreiche Liste [!UICONTROL traits] spiegelt die Entwicklung der Grundlinie-Population wider. Verwenden Sie die Liste des einflussreichen [!UICONTROL traits] , um zu verstehen, warum diese Änderungen auftreten.

Verwandte Links:

* [Modellaufbau](../../features/algorithmic-models/create-model.md)
* [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md)

## Zeitplan für [!UICONTROL Look-Alike Models] und [!UICONTROL Traits] aktualisieren {#update-schedule}

Erstellen und Aktualisieren von Zeitplänen für neue oder vorhandene [!UICONTROL algorithmic models] und [!UICONTROL traits].

### [!UICONTROL Look-Alike Model] Zeitplan für Erstellung und Aktualisierung

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> Aktivitätstyp </th>
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>Modell erstellen oder klonen</b> </td>
   <td colname="col2"> <p>Für neue oder geklonte [!UICONTROL Look-Alike Models] wird der Erstellungsprozess einmal täglich ausgeführt bei: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17.00 Uhr EST (November - März) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18 Uhr EDT (März - November) </li> 
     </ul> </p> <p>Nach Ablauf der Erstellungsfrist erstellte oder geklonte Modelle werden am folgenden Tag verarbeitet. </p> <p>Wenn die erste Ausführung eines Modells keine Daten generiert, wird sie am nächsten Tag ein zweites Mal ausgeführt. Wenn der zweite Versuch ebenfalls keine Daten generiert, wird am nächsten Tag ein dritter Versuch unternommen. Das Modell wird nicht mehr ausgeführt, wenn der dritte Versuch ebenfalls keine Daten generiert. In diesem Fall wird das Modell deaktiviert. Weitere Informationen finden Sie unter <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Fehlerbehebung bei Look-alike-Modellen</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Modell aktualisieren</b> </td> 
   <td colname="col2"> <p>Unter idealen Bedingungen laufen vorhandene Modelle an Werktagen, mindestens einmal alle 7 Tage. Wenn Sie beispielsweise am Montag ein Modell (bis zum Termin) erstellen, wird es spätestens am folgenden Montag aktualisiert. </p> <p>Ein Modell wird erneut ausgeführt, wenn eine der folgenden Bedingungen erfüllt ist: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Ihr letzter Lauf war nicht erfolgreich. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Es wurde erfolgreich ausgeführt, bevor ES in den letzten sieben Tagen überhaupt nicht ausgeführt wurde UND dem Modell wurde mindestens eine aktive Eigenschaft angehängt. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] Zeitplan für Erstellung und Aktualisierung

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Aktivitätstyp </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Erstellen einer Eigenschaft</b> </td> 
   <td colname="col2"> <p>Der Erstellungsprozess für Eigenschaften wird täglich von Montag bis Freitag ausgeführt. Im Allgemeinen werden in der Benutzeroberfläche innerhalb von 48 Stunden neue algorithmische Eigenschaften angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Eigenschaft aktualisieren</b> </td> 
   <td colname="col2"> <p>Vorhandene Eigenschaften werden mindestens alle 7 Tage aktualisiert und folgen dem Zeitplan für Modellaktualisierungen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modelllistenansicht {#models-list-view}

Die Listenansicht ist ein zentraler Arbeitsbereich, in dem Sie Modelle erstellen, überprüfen und verwalten können.

Die Listenseite [!UICONTROL Models] enthält Funktionen und Tools, die Ihnen dabei helfen,

* Erstellen Sie neue Modelle.
* Verwalten Sie vorhandene Modelle (Bearbeiten, Anhalten, Löschen oder Klonen).
* Suchen Sie nach Modellen anhand des Namens.
* Erstellen Sie [!UICONTROL algorithmic traits] mit einem beliebigen Modell.

## Modellzusammenfassungsansicht {#models-summary-view}

Auf der Zusammenfassungsseite werden Modelldetails wie Name, Reichweite/Genauigkeit, Verarbeitungsverlauf und aus dem Modell erstellter [!UICONTROL traits] angezeigt. Die Seite enthält auch Einstellungen, mit denen Sie Modelle erstellen und verwalten können. Klicken Sie in der Zusammenfassungsliste auf einen Modellnamen, um dessen Details anzuzeigen.

Die Modellzusammenfassungs-Seite enthält die folgenden Abschnitte.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Abschnitt </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> Grundlegende Informationen</span> </p> </td>
   <td colname="col2"> <p>Enthält grundlegende Informationen zum Modell, z. B. seinen Namen und den Zeitpunkt der letzten Ausführung. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> ModellReichweite und -genauigkeit</span> </p> </td> 
   <td colname="col2"> <p>Zeigt die <a href="../../features/traits/trait-accuracy-reach.md"> Genauigkeit und Reichweitendaten für den letzten Modelllauf an.</a> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Modellverarbeitungsverlauf</span> </p> </td> 
   <td colname="col2"> <p>Zeigt das Verarbeitungsdatum und die Verarbeitungszeit für die letzten zehn Ausführungen an und ob Daten für diese Ausführungen generiert wurden. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Einflussreiche Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>Die Tabelle <span class="wintitle"> Einflussnehmende Eigenschaften</span> : </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Führt die 50 einflussreichsten Eigenschaften auf, die am besten in der Grundlinie des Modells dargestellt werden. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Ordnet jede Eigenschaft in der Reihenfolge ihres Ranges <span class="wintitle"> Relative Gewichtung</span> zu. Die <span class="wintitle"> Relative Gewichtung</span> sortiert neu entdeckte Eigenschaften in der Reihenfolge ihres Einflusses oder ihrer Zweckmäßigkeit. Die Gewichtsskala ist ein Prozentsatz, der von 0 % bis 100 % reicht. Eigenschaften, die näher bei 100 % platziert wurden, bedeuten, dass sie eher der Zielgruppe in Ihrer Grundlinie ähneln. Siehe <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Grundlegendes zu TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Zeigt die eindeutigen 30-Tage-Werte und die gesamte Eigenschaftspopulation für jede Eigenschaft an. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Eigenschaften mit Modell</span> </p> </td>
   <td colname="col2"> <p>Zeigt eine Liste der algorithmischen Eigenschaften basierend auf dem ausgewählten Modell an. Klicken Sie auf einen Eigenschaftsnamen oder eine Eigenschafts-ID , um weitere Informationen zur Eigenschaft zu erhalten. Wählen Sie <b><span class="uicontrol"> Neue Eigenschaft mit Modell erstellen</span></b> aus, um zum Erstellungsvorgang für algorithmische Eigenschaften zu wechseln. </p> <p>Die Abschnittsbeschriftung ändert sich basierend auf dem Namen Ihres Modells. Angenommen, Sie erstellen ein Modell und nennen es Modell A. Wenn Sie die Zusammenfassungsseite laden, wird der Name dieses Abschnitts in <span class="wintitle"> Eigenschaften mit Modell A</span> geändert. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Ziele](../../features/destinations/destinations.md)
>* [Eigenschaften](../../features/traits/trait-details-page.md)
>* [Segmente](../../features/segments/segments-purpose.md)

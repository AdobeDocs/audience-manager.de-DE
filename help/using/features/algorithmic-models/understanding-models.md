---
description: Erstellen und verwalten Sie die Eigenschaften oder Segmente, die bei der Look-alike-Modellierung verwendet werden.
keywords: Relatives Gewicht, Lookalike
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

# Grundlagen zu [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Neue Benutzer mit [!UICONTROL Look-Alike Modeling] suchen {#find-new-users}

Mit [!UICONTROL Look-Alike Modeling] können Sie durch automatisierte Datenanalyse neue, einzigartige Zielgruppen ermitteln. Der Prozess beginnt mit der Auswahl eines [!UICONTROL trait] oder einer [!UICONTROL segment], eines Zeitintervalls sowie einer Erst- und [!UICONTROL data sources]. Ihre Auswahl liefert die Eingaben für das algorithmische Modell. Wenn der Analytics-Prozess ausgeführt wird, sucht er basierend auf gemeinsamen Merkmalen der ausgewählten Population nach geeigneten Benutzern. Nach Abschluss stehen diese Daten im [Trait Builder) zur Verfügung](../../features/traits/about-trait-builder.md) in dem Sie damit Eigenschaften basierend auf [Genauigkeit und Reichweite“ erstellen &#x200B;](../../features/traits/trait-accuracy-reach.md). Darüber hinaus können Sie Segmente erstellen, die algorithmische Eigenschaften mit [!UICONTROL rules-based traits] kombinieren, und andere Qualifizierungsanforderungen mit [!DNL Boolean] Ausdrücken und Vergleichsoperatoren hinzufügen. [!UICONTROL Look-Alike Modeling] bietet Ihnen eine dynamische Möglichkeit, Wert aus allen verfügbaren Eigenschaftsdaten zu extrahieren.

## Vorteile {#advantages}

Zu den wichtigsten Vorteilen der Verwendung von [!UICONTROL Look-Alike Modeling] gehören:

* **Datengenauigkeit:** Der Algorithmus wird regelmäßig ausgeführt, wodurch die Ergebnisse aktuell und relevant bleiben.
* **Automatisierung** Sie müssen nicht viele statische Regeln verwalten. Der Algorithmus findet Zielgruppen für Sie.
* **Sparen Sie Zeit und reduzieren Sie den Aufwand:** Mit unserem Modellierungsprozess müssen Sie nicht erraten, welche [!UICONTROL traits]/[!UICONTROL segments] funktionieren könnten, oder Zeit und Ressourcen für Kampagnen aufwenden, um neue Audiences zu entdecken. Das Modell kann das für Sie tun.
* **Zuverlässigkeit:** Modeling arbeitet mit Server-seitigen Erkennungs- und Qualifizierungsprozessen, die Ihre eigenen Daten und ausgewählte Drittanbieterdaten, auf die Sie Zugriff haben, auswerten. Das bedeutet, dass Sie die Besucher auf Ihrer Site nicht sehen müssen, um sie für eine Eigenschaft zu qualifizieren.

## Workflow {#workflow}

Sie verwalten Modelle in **[!UICONTROL Audience Data > Models]**. Im Großen und Ganzen umfasst der Workflow-Prozess Folgendes:

* Wählen Sie die Baseline-Daten aus, die der Algorithmus auswerten soll. Dazu gehören ein [!UICONTROL trait] oder [!UICONTROL segment], ein Zeitraum und [!UICONTROL data sources] (Ihre eigenen Daten und Drittanbieterdaten, auf die Sie bereits über [!DNL Audience Manager] Zugriff haben). Im Arbeitsablauf für die Modellerstellung können Sie die [!UICONTROL traits] ausschließen, die Sie nicht mit Ihrem Modell beeinträchtigen möchten.
* Speichern Sie Ihr Modell. Nach dem Speichern wird der algorithmische Auswertungsprozess automatisch ausgeführt. Beachten Sie jedoch, dass es bis zu 7 Tage dauern kann, bis dieser Vorgang abgeschlossen ist. [!DNL Audience Manager] sendet Ihnen eine E-Mail, wenn der Algorithmus abgeschlossen ist und die Ergebnisse für die [!UICONTROL trait] verfügbar sind.
* Algorithmische [!UICONTROL traits] in [!UICONTROL Trait Builder] erstellen.
* [!UICONTROL traits] in [!UICONTROL segments] zu [!UICONTROL Segment Builder] kombinieren.
* Erstellen und Senden [!UICONTROL segment] Daten an eine [!UICONTROL destination].

## Fehlerbehebung {#troubleshooting}

Wir deaktivieren alle [!UICONTROL Look-Alike Model], die in drei aufeinander folgenden Durchgängen keine Daten generieren. Beachten Sie, dass Sie den Status des Modells danach nicht mehr auf „aktiv“ zurücksetzen können. Um sicherzustellen, dass Ihre Modelle Daten generieren, empfehlen wir, Modelle aus Datenquellen mit ausreichendem [!UICONTROL traits] zu erstellen, aus denen Daten gesammelt werden können.

## Grundlagen zu [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] ist ein proprietärer Algorithmus, der die automatische Erkennung neuer [!UICONTROL traits] ermöglicht. Es vergleicht [!UICONTROL trait] Daten aus Ihrer aktuellen [!UICONTROL traits] und [!UICONTROL segments] mit allen anderen Erst- und Drittanbieterdaten, auf die Sie über [!DNL Audience Manager] Zugriff haben. In diesem Abschnitt finden Sie eine Beschreibung des [!UICONTROL TraitWeight] algorithmischen Erkennungsprozesses.

![](assets/algo_model.png)

Die folgenden Schritte beschreiben den Prozess der [!UICONTROL TraitWeight].

### Schritt 1: Baseline für [!UICONTROL Trait] Vergleich erstellen

Um eine Baseline zu erstellen, misst [!UICONTROL TraitWeight] alle mit einer Zielgruppe verknüpften [!UICONTROL traits] für ein Intervall von 30, 60 oder 90 Tagen. Als Nächstes werden [!UICONTROL traits] nach ihrer Häufigkeit und ihrer Korrelation sortiert. Die Häufigkeitsanzahl misst die Gemeinsamkeit. Die Korrelation misst die Wahrscheinlichkeit, dass ein [!UICONTROL trait] nur in der Baseline-Zielgruppe vorhanden ist. Häufig vorkommende [!UICONTROL Traits] weisen eine hohe Gemeinsamkeit auf. Dies ist ein wichtiges Merkmal, das verwendet wird, um einen gewichteten Wert festzulegen, wenn sie mit [!UICONTROL traits] kombiniert werden, die in Ihrem ausgewählten [!UICONTROL data sources] entdeckt wurden.

### Schritt 2: Gleiches [!UICONTROL Traits] im [!UICONTROL Data Source] suchen

Nachdem eine Baseline für den Vergleich erstellt wurde, sucht der Algorithmus nach identischen [!UICONTROL traits] in der ausgewählten [!UICONTROL data sources]. In diesem Schritt führt [!UICONTROL TraitWeight] eine Häufigkeitszählung aller erkannten [!UICONTROL traits] durch und vergleicht sie mit der Grundlinie. Im Gegensatz zur Baseline werden gelegentliche [!UICONTROL traits] jedoch höher eingestuft als solche, die häufiger auftreten. Seltene [!UICONTROL traits] sollen ein hohes Maß an Spezifität aufweisen. [!UICONTROL TraitWeight] bewertet Kombinationen aus häufigen [!UICONTROL traits] und gelegentlichen (hochspezifischen) [!UICONTROL data source] [!UICONTROL traits] als einflussreicher oder wünschenswerter als [!UICONTROL traits] beiden Datensätzen gemeinsam. Tatsächlich erkennt unser Modell diese großen, gemeinsamen [!UICONTROL traits] und weist Datensätzen mit hohen Korrelationen keine übermäßige Priorität zu. Selten [!UICONTROL traits] eine höhere Priorität erhalten, da sie mit höherer Wahrscheinlichkeit neue, eindeutige Benutzende repräsentieren als [!UICONTROL traits] mit hoher allgemeiner Gemeinsamkeit.

### Schritt 3: Gewichtung zuweisen

In diesem Schritt reiht [!UICONTROL TraitWeight] neu entdeckte [!UICONTROL traits] nach Einfluss oder Erwünschtheit ein. Die Gewichtsskala ist ein Prozentsatz, der von 0 % bis 100 % reicht. [!UICONTROL Traits], die näher an 100 % rangen, bedeutet, dass sie der Zielgruppe in Ihrer Grundlinie ähneln. Starke gewichtete [!UICONTROL traits] sind außerdem wertvoll, da sie neue, eindeutige Benutzende darstellen, die sich möglicherweise ähnlich wie Ihre etablierte Baseline-Zielgruppe verhalten. Denken Sie daran, dass [!UICONTROL TraitWeight] [!UICONTROL traits] mit hoher Gemeinsamkeit bei der Baseline und hoher Spezifität in den verglichenen Datenquellen für wertvoller hält als [!UICONTROL traits] in jedem Datensatz.

### Schritt 4: Bewertung von Benutzern

Jedem Benutzer im ausgewählten [!UICONTROL data sources] wird ein Benutzerwert zugewiesen, der der Summe aller Gewichtungen der einflussreichen [!UICONTROL traits] im Profil dieses Benutzers entspricht. Die Benutzerbewertungen werden dann zwischen 0 und 100 % normalisiert.

### Schritt 5: Ergebnisse anzeigen und verwenden

[!DNL Audience Manager] zeigt die gewichteten Modellergebnisse in [!UICONTROL Trait Builder] an. Wenn Sie ein [!UICONTROL algorithmic trait] erstellen möchten, können Sie mit [!UICONTROL Trait Builder] [!UICONTROL traits] erstellen, die auf dem gewichteten Score basieren, der vom Algorithmus während eines Datendurchgangs generiert wurde. Sie können eine höhere Genauigkeit wählen, um nur Benutzende zu qualifizieren, die sehr hohe Benutzerbewertungen haben und daher der Baseline-Zielgruppe sehr ähnlich sind, anstatt dem Rest der Zielgruppe. Wenn Sie eine größere Zielgruppe (Reichweite) erreichen möchten, können Sie die Genauigkeit verringern.

### Schritt 6: Bewertung der Signifikanz eines [!UICONTROL Trait] über alle Verarbeitungszyklen hinweg

In regelmäßigen Abständen bewertet [!UICONTROL TraitWeight] die Bedeutung einer [!UICONTROL trait] anhand der Größe und der Veränderung der Population dieser [!UICONTROL trait] neu. Dies geschieht, wenn die Anzahl der für diese [!UICONTROL trait] qualifizierten Benutzenden im Laufe der Zeit zunimmt oder abnimmt. Dieses Verhalten zeigt sich am deutlichsten bei Eigenschaften, die sehr groß werden. Angenommen, der Algorithmus verwendet [!UICONTROL trait A] für die Modellierung. Wenn die Population der [!UICONTROL trait A] zunimmt, bewertet [!UICONTROL TraitWeight] die Bedeutung dieser [!UICONTROL trait] neu und kann einen niedrigeren Wert zuweisen oder sie ignorieren. In diesem Fall ist [!UICONTROL trait A] zu verbreitet oder zu groß, um irgendetwas Bedeutsames über seine Bevölkerung zu sagen. Nachdem [!UICONTROL TraitWeight] den Wert von [!UICONTROL trait A] verringert (oder im Modell ignoriert) hat, nimmt die Population des algorithmischen Merkmals ab. Die Liste der einflussreichen [!UICONTROL traits] spiegelt die Entwicklung der Grundgesamtheit wider. Verwenden Sie die Liste der einflussreichen [!UICONTROL traits], um zu verstehen, warum diese Änderungen auftreten.

Verwandte Links:

* [Modellersteller](../../features/algorithmic-models/create-model.md)
* [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md)

## Zeitplan für [!UICONTROL Look-Alike Models] und [!UICONTROL Traits] aktualisieren {#update-schedule}

Erstellen und Aktualisieren von Zeitplänen für neue oder vorhandene [!UICONTROL algorithmic models] und [!UICONTROL traits]

### Zeitplan für Erstellung und Aktualisierung von [!UICONTROL Look-Alike Model]

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> Aktivitätstyp </th>
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>Erstellen oder Klonen eines Modells</b> </td>
   <td colname="col2"> <p>Bei neuen oder geklonten [!UICONTROL Look-Alike Models] wird der Erstellungsprozess einmal täglich um ausgeführt: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17.00 Uhr EST (November - März) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18:00 Uhr EDT (März - November) </li> 
     </ul> </p> <p>Nach Ablauf der Erstellungsfrist erstellte oder geklonte Modelle werden am folgenden Tag verarbeitet. </p> <p>Wenn bei der ersten Ausführung eines Modells keine Daten generiert werden, erfolgt die Ausführung am nächsten Tag zum zweiten Mal. Wenn der zweite Versuch ebenfalls keine Daten generiert, gibt es einen dritten Versuch, den nächsten Tag. Das Modell wird nicht mehr ausgeführt, wenn auch der dritte Versuch keine Daten generiert. In diesem Fall deaktivieren wir das Modell. Weitere Informationen finden Sie unter Fehlerbehebung <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Lookalike-Modellen</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Modell aktualisieren</b> </td> 
   <td colname="col2"> <p>Unter idealen Bedingungen werden bestehende Modelle werktags mindestens einmal alle 7 Tage ausgeführt. Wenn Sie beispielsweise ein Modell (innerhalb der Frist) am Montag erstellen, wird es spätestens am folgenden Montag aktualisiert. </p> <p>Ein Modell wird erneut ausgeführt, wenn es eine der folgenden Bedingungen erfüllt: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Der letzte Durchgang war nicht erfolgreich. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Es wurde bereits erfolgreich ausgeführt, bevor UND es wurde in den letzten 7 Tagen überhaupt nicht ausgeführt. UND dem Modell ist mindestens eine aktive Eigenschaft zugeordnet. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Zeitplan für Erstellung und Aktualisierung von [!UICONTROL Look-Alike Trait]

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
   <td colname="col2"> <p>Der Prozess zur Erstellung von Eigenschaften wird täglich von Montag bis Freitag ausgeführt. Im Allgemeinen erscheinen neue algorithmische Eigenschaften innerhalb von 48 Stunden in der Benutzeroberfläche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Eigenschaft aktualisieren</b> </td> 
   <td colname="col2"> <p>Vorhandene Eigenschaften werden mindestens einmal alle 7 Tage aktualisiert und dem Zeitplan für Modellaktualisierungen folgen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Listenansicht der Modelle {#models-list-view}

Die Listenansicht ist ein zentraler Arbeitsbereich, in dem Sie Modelle erstellen, überprüfen und verwalten können.

Die Seite [!UICONTROL Models] enthält Funktionen und Tools, die Ihnen bei Folgendem helfen:

* Erstellen Sie neue Modelle.
* Verwalten vorhandener Modelle (Bearbeiten, Pausieren, Löschen oder Klonen).
* Suche nach Modellen anhand des Namens.
* Erstellen Sie [!UICONTROL algorithmic traits] mit einem beliebigen Modell.

## Modellzusammenfassungsansicht {#models-summary-view}

Auf der Zusammenfassungsseite werden Modelldetails wie Name, Reichweite/Genauigkeit, Verarbeitungsverlauf und aus dem Modell erstellte [!UICONTROL traits] angezeigt. Die Seite enthält auch Einstellungen zum Erstellen und Verwalten von Modellen. Klicken Sie in der Zusammenfassungsliste auf einen Modellnamen, um dessen Details anzuzeigen.

Die Seite mit der Modellübersicht enthält die folgenden Abschnitte.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Abschnitt </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> grundlegende Informationen</span> </p> </td>
   <td colname="col2"> <p>Enthält grundlegende Informationen zum Modell, z. B. den Namen und den Zeitpunkt der letzten Ausführung. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reichweite und Genauigkeit des <span class="wintitle"> Modells</span> </p> </td> 
   <td colname="col2"> <p>Zeigt <a href="../../features/traits/trait-accuracy-reach.md"> Genauigkeit und Reichweite</a> Daten für die letzte Modellausführung. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> des Verarbeitungsverlaufs</span> </p> </td> 
   <td colname="col2"> <p>Zeigt das Verarbeitungsdatum und die Verarbeitungszeit der letzten 10 Ausführungen an und gibt an, ob bei diesen Ausführungen Daten generiert wurden. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> einflussreiche Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>Die Tabelle <span class="wintitle"> einflussreiche Eigenschaften</span>: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Führt die 50 wichtigsten einflussreichen Eigenschaften auf, die in der Grundgesamtheit des Modells am besten dargestellt werden. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Ordnet jedes Merkmal nach seinem <span class="wintitle"> relativen Gewicht </span>. Das <span class="wintitle"> Relative Gewicht</span> sortiert neu entdeckte Merkmale nach Einfluss oder Erwünschtheit. Die Gewichtsskala ist ein Prozentsatz, der von 0 % bis 100 % reicht. Eigenschaften, die näher an 100 % rangieren, bedeuten, dass sie der Zielgruppe in Ihrer Grundgesamtheit ähnlicher sind. Siehe <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> zum Verstehen von TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Zeigt die eindeutigen 30-Tage-Werte und die gesamte Population der einzelnen Eigenschaften für jedes Merkmal an. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Eigenschaften mithilfe eines Modells</span> </p> </td>
   <td colname="col2"> <p>Zeigt eine Liste der algorithmischen Eigenschaften basierend auf dem ausgewählten Modell an. Klicken Sie auf einen Eigenschaftsnamen oder eine Eigenschafts-ID, um weitere Informationen über die Eigenschaft zu erhalten. Wählen Sie <b><span class="uicontrol"> Neue Eigenschaft mit Modell erstellen </span></b>, um zum Prozess der algorithmischen Eigenschaftserstellung zu wechseln. </p> <p>Die Abschnittsbeschriftung ändert sich je nach Modellnamen. Angenommen, Sie erstellen ein Modell und benennen es Modell A. Wenn Sie die Zusammenfassungsseite laden, wird der Name dieses Abschnitts in Eigenschaften <span class="wintitle"> Modell A</span> geändert. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Ziele](../../features/destinations/destinations.md)
>* [Eigenschaften](../../features/traits/trait-details-page.md)
>* [Segmente](../../features/segments/segments-purpose.md)

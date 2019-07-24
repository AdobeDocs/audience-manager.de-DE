---
description: Erstellen und verwalten Sie die im algorithmischen Modellierung verwendeten Eigenschaften oder Segmente, auch als Look-Alike-Modellierung bezeichnet. Modellfunktionen finden Sie unter Zielgruppendaten > Modelle.
keywords: relative Gewichtung
seo-description: Erstellen und verwalten Sie die im algorithmischen Modellierung verwendeten Eigenschaften oder Segmente, auch als Look-Alike-Modellierung bezeichnet. Modellfunktionen finden Sie unter Zielgruppendaten > Modelle.
seo-title: Grundlagen zu algorithmischen Modellen
solution: Audience Manager
title: Grundlagen zu algorithmischen Modellen
topic: DIL-API
uuid: 39441 e 72-5316-453 d -9 aff -0 e 0 b 633 aabcd
translation-type: tm+mt
source-git-commit: 157e70906b80bd0a23ba6e7721d2c456d378ffb5

---


# About Algorithmic Models {#about-algorithmic-models}

Erstellen und verwalten Sie die im algorithmischen Modellierung verwendeten Eigenschaften oder Segmente, auch als Look-Alike-Modellierung bezeichnet. Model features are located in **[!UICONTROL Audience Data > Models]**.

<!-- c_models.xml -->

## Understanding Algorithmic Models {#understanding-models}

The sections below represent a review of algorithmic modeling in [!DNL Audience Manager]. Sie beschreiben, wie die Modellierung funktioniert, welche Vorteile und welcher Arbeitsablauf erzielt wird.

<!-- understanding-models.xml -->

## Find New Users with Algorithmic Modeling {#find-new-users}

Die algorithmische Modellierung hilft Ihnen, neue, einzigartige Zielgruppen durch automatisierte Datenanalyse zu entdecken. Der Prozess beginnt, wenn Sie eine Eigenschaft oder ein Segment, ein Zeitintervall sowie Datenquellen aus der ersten und dritten Partei auswählen. Ihre Optionen bieten die Eingaben für das algorithmische Modell. Wenn der Analyseprozess ausgeführt wird, sucht er nach Benutzern, die auf freigegebenen Merkmalen der ausgewählten Population basieren. Upon completion, this data is available in [Trait Builder](../../features/traits/about-trait-builder.md) where you can use it to create traits based on [accuracy and reach](../../features/traits/trait-accuracy-reach.md). Darüber hinaus können Sie Segmente erstellen, die algorithmische Eigenschaften mit regelbasierten Eigenschaften kombinieren, und andere Qualifikationsanforderungen mit booleschen Ausdrücken und Vergleichsoperatoren hinzufügen. Algorithmische Modellierung bietet Ihnen eine dynamische Möglichkeit, Werte aus allen verfügbaren Eigenschaftsdaten zu extrahieren.

## Vorteile {#advantages}

The major benefits of using [!DNL Audience Manager] modeling include:

* **Genauigkeit der Daten:** Der Algorithmus wird regelmäßig ausgeführt, wodurch die Ergebnisse aktuell und relevant bleiben.
* **Automatisierung:** Sie müssen keine umfangreichen statischen Regeln verwalten. Der Algorithmus findet Zielgruppen für Sie.
* **Sparen Sie Zeit und reduzieren Sie die Arbeit:** Mit unserem Modellierungsprozess müssen Sie nicht wissen, welche Eigenschaften/Segmente funktionieren oder wie viel Zeit Sie für Kampagnen verbringen, um neue Zielgruppen zu entdecken. Das Modell kann dies für Sie tun.
* **Zuverlässigkeit:** Die Modellierung funktioniert mit serverseitigen Such- und Qualifizierungsprozessen, die Ihre eigenen Daten und die ausgewählten Drittanbieterdaten auswerten, auf die Sie Zugriff haben. Das bedeutet, dass Sie die Besucher auf Ihrer Site nicht für eine Eigenschaftsvariable qualifizieren müssen.

## Arbeitsablauf{#workflow}

You manage models in **[!UICONTROL Audience Data > Models]**. Auf einer hohen Ebene umfasst der Workflow-Prozess Folgendes:

* Wählen Sie die Ausgangsdaten aus, die der Algorithmus bewerten soll. This includes a trait or segment, time range, and data sources (your own data and third-party data you already have access to through [!DNL Audience Manager]). Im Arbeitsablauf für die Modellerstellung können Sie die Eigenschaften ausschließen, die Sie nicht mit Ihrem Modell stören möchten.
* Speichern Sie Ihr Modell. Nach dem Speichern wird der algorithmische Evaluierungsprozess automatisch ausgeführt. Es kann jedoch bis zu 7 Tage dauern, bis dieser Vorgang abgeschlossen ist. [!DNL Audience Manager] sendet eine E-Email, wenn der Algorithmus abgeschlossen ist und die Ergebnisse für die Erstellung von Eigenschaften verfügbar sind.
* Build algorithmic traits in [!UICONTROL Trait Builder].
* Combine traits into segments in [!UICONTROL Segment Builder].
* Erstellen und senden Sie Segmentdaten an ein Ziel.

## Fehlerbehebung {#troubleshooting}

Wir deaktivieren ein algorithmische Modell, das keine Daten für drei aufeinander folgende Ausführungen generiert. Beachten Sie, dass Sie den Status des Modells nicht wieder auf aktiv setzen können. Um sicherzustellen, dass Ihre Modelle Daten generieren, sollten Sie Modelle aus Datenquellen mit ausreichenden Eigenschaften erstellen, um Daten zu sammeln.

>[!MORE_ LIKE_ THIS]
>
>* [Ziele](../../features/destinations/destinations.md)
>* [Eigenschaften](../../features/traits/trait-details-page.md)
>* [Segmente](../../features/segments/segments-purpose.md)


## Understanding TraitWeight {#understanding-traitweight}

[!UICONTROL TraitWeight] ist ein proprietärer Algorithmus, der automatisch neue Eigenschaften entdecken soll. It compares trait data from your current traits and segments against all other first and third-party data that you have access to through [!DNL Audience Manager]. Refer to this section for a description of the [!UICONTROL TraitWeight] algorithmic discovery process.

<!-- traitweight.xml -->

![](assets/algo_model.png)

The following steps describe the [!UICONTROL TraitWeight] evaluation process.

### Schritt 1: Erstellen eines Ausgangswerts für den Trait-Vergleich

To build a baseline, [!UICONTROL TraitWeight] measures all the traits associated with an audience for a 30, 60, or 90 day interval. Als Nächstes werden Eigenschaften entsprechend ihrer Häufigkeit und deren Korrelation eingestuft. Die Häufigkeit misst die Gemeinsamkeit. Korrelation misst die Wahrscheinlichkeit, dass ein Merkmal nur in der Grundlinienzielgruppe vorhanden ist. Häufig angezeigte Eigenschaften weisen eine hohe Gemeinsamalität auf, ein wichtiges Merkmal, mit dem ein gewichtetes Ergebnis festgelegt wird, wenn es mit Eigenschaften kombiniert wird, die in den ausgewählten Datenquellen entdeckt wurden.

### Schritt 2: Identische Eigenschaften in der Datenquelle suchen

Nachdem Sie einen Ausgangswert für den Vergleich erstellt haben, sucht der Algorithmus nach identischen Eigenschaften in den ausgewählten Datenquellen. In this step, [!UICONTROL TraitWeight] performs a frequency count of all discovered traits and compares them to the baseline. Im Gegensatz zu der Grundlinie sind ungewöhnliche Eigenschaften jedoch höher als die, die häufiger angezeigt werden. Seltene Eigenschaften bieten einen hohen Grad an Spezifität. [!UICONTROL TraitWeight] bewertet Kombinationen aus allgemeinen Grundlinieneigenschaften und ungewöhnlichen (hochgradig spezifischen) Datenquelleneigenschaften als einflussreicher oder wünschenswerter als für beide Datensätze. In der Tat erkennt unser Modell diese großen, allgemeinen Eigenschaften und weist Datensätzen mit hohen Korrelationen keine übermäßige Priorität zu. Seltene Eigenschaften erhalten höhere Priorität, da sie eher neue, Unique Users als Eigenschaften darstellen, die über die gesamte Pinnwand hinweg zu hoch sind.

### Schritt 3: Gewichtung zuweisen

In this step, [!UICONTROL TraitWeight] ranks newly discovered traits in order of influence or desirability. Die Gewichtung ist ein Prozentsatz, der zwischen 0% und 100% ausführt. Eigenschaften, die näher an 100% rangiert sind, bedeuten, dass sie eher wie die Zielgruppe in Ihrer Grundlinienpopulation sind. Stark gewichtete Eigenschaften sind außerdem wertvoll, da sie neue individuelle Benutzer darstellen, die sich ähnlich wie die etablierte Grundzielgruppe verhalten. Remember, [!UICONTROL TraitWeight] considers traits with high commonality in the baseline and high specificity in the compared data sources to be more valuable than traits common in each data set.

### Schritt 4: Auswertungsbenutzer

Jeder Benutzer in den ausgewählten Datenquellen erhält ein Benutzerergebnis, das der Summe aller Gewichtungen der einflussreichsten Eigenschaften des Benutzerprofils entspricht. Die Benutzerbewertungen werden dann zwischen 0 und 100% normalisiert.

### Schritt 5: Ergebnisse anzeigen und mit diesen arbeiten

Audience Manager displays your weighted model results in [!UICONTROL Trait Builder]. When you want to build an algorithmic trait, [!UICONTROL Trait Builder] lets you create traits based on the weighted score generated by the algorithm during a data run. Sie können eine höhere Genauigkeit wählen, um nur Benutzer zu qualifizieren, die sehr hohe Benutzerbewertungen haben und daher sehr ähnlich der Grundzielgruppe sind und nicht den Rest der Zielgruppe. Wenn Sie eine größere Zielgruppe erreichen möchten (Reichweite), können Sie die Genauigkeit verringern.

### Schritt 6: Bewerten Sie die Bedeutung einer Eigenschaft über Verarbeitungszyklen hinweg erneut.

Periodically, [!UICONTROL TraitWeight] re-evaluates the importance of a trait based on the size and change in the population of that trait. Dies geschieht, wenn die Anzahl der Benutzer, die für diese Eigenschaft qualifiziert sind, im Laufe der Zeit erhöht oder verringert wird. Dieses Verhalten wird in Eigenschaften, die sehr groß werden, sehr klar dargestellt. Angenommen, der Algorithmus verwendet Eigenschaften A für das Modellieren. As the population of trait A increases, [!UICONTROL TraitWeight] re-evaluates the importance of that trait and may assign a lower score or ignore it. In diesem Fall ist Merkmala zu häufig oder sehr umfangreich, um seine Population hervorzuheben. After [!UICONTROL TraitWeight] reduces the value of Trait A (or ignores it in the model), the population of the algorithmic trait decreases. Die Liste einflussreicher Eigenschaften spiegelt die Evolution der Grundlinienpopulation wider. Verwenden Sie die Liste der einflussreichsten Eigenschaften, um zu verstehen, warum diese Änderungen vorgenommen wurden.

Verwandte Links:

* [Modellaufbau](../../features/algorithmic-models/create-model.md)
* [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md)

## Update Schedule for Algorithmic Models and Traits {#update-schedule}

Erstellen und Aktualisieren von Zeitplänen für neue oder vorhandene algorithmische Modelle und Eigenschaften.

<!-- c_model_update_schedule.xml -->

### Algorithmische Modellerstellung und -aktualisierung

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> Aktivitätstyp </th>
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>Ein Modell erstellen oder klonen</b> </td>
   <td colname="col2"> <p>Bei neuen oder geklonten Algorithmen wird der Erstellungsprozess einmal pro Tag unter folgender Adresse ausgeführt: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (November - März) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (März - November) </li> 
     </ul> </p> <p>Modelle, die nach dem Erstellungstermin erstellt oder geklont wurden, werden am folgenden Tag verarbeitet. </p> <p>Wenn die erste Ausführung eines Modells keine Daten generiert, wird es ein zweites Mal ausgeführt, am nächsten Tag. Wenn der zweite Versuch auch keine Daten generiert, erfolgt ein dritter Versuch, am nächsten Tag. Das Modell wird beendet, wenn der dritte Versuch auch keine Daten generiert. In diesem Fall deaktivieren wir das Modell. See more in <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Troubleshooting Algorithmic Models</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Modell aktualisieren</b> </td> 
   <td colname="col2"> <p>Unter idealen Bedingungen laufen vorhandene Modelle an Wochentagen, mindestens einmal alle 7 Tage. Wenn Sie beispielsweise am Montag ein Modell (um den Termin) erstellen, wird am Montag der folgende Montag aktualisiert. </p> <p>Ein Modell wird erneut ausgeführt, wenn es eine der folgenden Bedingungen erfüllt: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Die letzte Ausführung war nicht erfolgreich. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Es wurde erfolgreich ausgeführt, bevor und es in den vergangenen 7 Tagen überhaupt nicht ausgeführt wurde und das Modell verfügt über mindestens eine aktive Eigenschaft. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Algorithmische Eigenschaften Erstellen und Aktualisieren Plan

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Aktivitätstyp </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Erstellen von Eigenschaften</b> </td> 
   <td colname="col2"> <p>Der Eigenschaftserstellungsprozess wird jeden Tag bis Freitag ausgeführt. Im Allgemeinen werden neue algorithmische Eigenschaften innerhalb von 48 Stunden in der Benutzeroberfläche angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Aktualisieren von Eigenschaften</b> </td> 
   <td colname="col2"> <p>Vorhandene Eigenschaften werden mindestens einmal alle 7 Tage aktualisiert und folgen dem Zeitplan für Modellaktualisierungen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Models List View {#models-list-view}

Die Listenansicht ist ein zentraler Arbeitsbereich, mit dem Sie Modelle erstellen, überprüfen und verwalten können.

<!-- c_models_list_view.xml -->

Die Modellseite enthält Funktionen und Tools, die Ihnen dabei helfen:

* Erstellen Sie neue Modelle.
* Verwalten Sie vorhandene Modelle (bearbeiten, anhalten, löschen oder klonen).
* Suchen Sie nach Modellen nach Namen.
* Erstellen Sie algorithmische Eigenschaften mit einem beliebigen Modell.

## Models Summary View {#models-summary-view}

Auf der Zusammenfassungsseite werden Modelldetails wie Name, Reichweite/Genauigkeit, Verarbeitungsverlauf und Eigenschaften angezeigt, die aus dem Modell erstellt wurden. Die Seite enthält auch Einstellungen, mit denen Sie Modelle erstellen und verwalten können. Klicken Sie in der Zusammenfassungsliste auf einen Modellnamen, um dessen Details anzuzeigen.

<!-- c_models_summary.xml -->

Die Modellzusammenfassungsseite enthält die folgenden Abschnitte.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Abschnitt </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> Basisinformationen</span> </p> </td>
   <td colname="col2"> <p>Enthält grundlegende Informationen zum Modell, z. B. seinem Namen und zum Zeitpunkt der letzten Ausführung. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Modellreichweite und -genauigkeit</span> </p> </td> 
   <td colname="col2"> <p>Shows <a href="../../features/traits/trait-accuracy-reach.md"> accuracy and reach</a> data for the last model run. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Modell-Verarbeitungsverlauf</span> </p> </td> 
   <td colname="col2"> <p>Zeigt das Verarbeitungsdatum und die Uhrzeit der letzten 10 Ausführungen an und ob Daten auf diesen ausgeführt wurden. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Einflussreiche Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> Influential Traits</span> table: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Listet die 50 wichtigsten Einflusseigenschaften auf, die am besten in der Grundlinienpopulation des Modells dargestellt werden. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Ranks each trait in order of its <span class="wintitle"> Relative Weight</span> rank. The <span class="wintitle"> Relative Weight</span> sorts newly discovered traits in order of influence or desirability. Die Gewichtung ist ein Prozentsatz, der zwischen 0% und 100% ausführt. Eigenschaften, die näher an 100% rangiert sind, bedeuten, dass sie eher wie die Zielgruppe in Ihrer Grundlinienpopulation sind. See <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Understanding TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Zeigt die 30-Tage-individuellen Werte und die Gesamtfüllung für die einzelnen Merkmale an. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Eigenschaften mit Modell</span> </p> </td>
   <td colname="col2"> <p>Zeigt eine Liste der algorithmischen Eigenschaften basierend auf dem ausgewählten Modell an. Klicken Sie auf einen Eigenschaftsnamen oder eine Eigenschafts-ID, um weitere Informationen zu der Eigenschaft zu erhalten. Select <b><span class="uicontrol"> Create New Trait with Model</span></b> to go to the algorithmic trait creation process. </p> <p>Die Abschnittsbeschriftung ändert sich je nach dem Namen Ihres Modells. For example, say you create a model and name it Model A. When you load the summary page, the name of this section gets changed to <span class="wintitle"> Traits Using Model A</span>. </p> </td>
  </tr>
 </tbody>
</table>
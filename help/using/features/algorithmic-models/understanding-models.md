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


# Grundlagen zu algorithmischen Modellen {#about-algorithmic-models}

Erstellen und verwalten Sie die im algorithmischen Modellierung verwendeten Eigenschaften oder Segmente, auch als Look-Alike-Modellierung bezeichnet. Modellfunktionen finden Sie in **[!UICONTROL Audience Data > Models]**.

<!-- c_models.xml -->

## Grundlagen zu algorithmischen Modellen {#understanding-models}

The sections below represent a review of algorithmic modeling in [!DNL Audience Manager]. Sie beschreiben, wie die Modellierung funktioniert, welche Vorteile und welcher Arbeitsablauf erzielt wird.

<!-- understanding-models.xml -->

## Neue Benutzer mit algorithmischer Modellierung suchen {#find-new-users}

Die algorithmische Modellierung hilft Ihnen, neue, einzigartige Zielgruppen durch automatisierte Datenanalyse zu entdecken. Der Prozess beginnt, wenn Sie eine Eigenschaft oder ein Segment, ein Zeitintervall sowie Datenquellen aus der ersten und dritten Partei auswählen. Ihre Optionen bieten die Eingaben für das algorithmische Modell. Wenn der Analyseprozess ausgeführt wird, sucht er nach Benutzern, die auf freigegebenen Merkmalen der ausgewählten Population basieren. Nach Abschluss sind diese Daten im [Eigenschaftenaufbau](../../features/traits/about-trait-builder.md) verfügbar, wo Sie sie verwenden können, um Eigenschaften basierend auf [Genauigkeit und Reichweite zu erstellen](../../features/traits/trait-accuracy-reach.md). Darüber hinaus können Sie Segmente erstellen, die algorithmische Eigenschaften mit regelbasierten Eigenschaften kombinieren, und andere Qualifikationsanforderungen mit booleschen Ausdrücken und Vergleichsoperatoren hinzufügen. Algorithmische Modellierung bietet Ihnen eine dynamische Möglichkeit, Werte aus allen verfügbaren Eigenschaftsdaten zu extrahieren.

## Vorteile {#advantages}

Die Verwendung [!DNL Audience Manager] von Modellierung bietet die größten Vorteile:

* **Genauigkeit der Daten:** Der Algorithmus wird regelmäßig ausgeführt, wodurch die Ergebnisse aktuell und relevant bleiben.
* **Automatisierung:** Sie müssen keine umfangreichen statischen Regeln verwalten. Der Algorithmus findet Zielgruppen für Sie.
* **Sparen Sie Zeit und reduzieren Sie die Arbeit:** Mit unserem Modellierungsprozess müssen Sie nicht wissen, welche Eigenschaften/Segmente funktionieren oder wie viel Zeit Sie für Kampagnen verbringen, um neue Zielgruppen zu entdecken. Das Modell kann dies für Sie tun.
* **Zuverlässigkeit:** Die Modellierung funktioniert mit serverseitigen Such- und Qualifizierungsprozessen, die Ihre eigenen Daten und die ausgewählten Drittanbieterdaten auswerten, auf die Sie Zugriff haben. Das bedeutet, dass Sie die Besucher auf Ihrer Site nicht für eine Eigenschaftsvariable qualifizieren müssen.

## Arbeitsablauf{#workflow}

Sie verwalten Modelle in **[!UICONTROL Audience Data > Models]**. Auf einer hohen Ebene umfasst der Workflow-Prozess Folgendes:

* Wählen Sie die Ausgangsdaten aus, die der Algorithmus bewerten soll. Dies umfasst eine Eigenschaft oder ein Segment, einen Zeitraum und Datenquellen (Ihre eigenen Daten und Drittanbieterdaten, auf die Sie bereits [!DNL Audience Manager]zugreifen können). Im Arbeitsablauf für die Modellerstellung können Sie die Eigenschaften ausschließen, die Sie nicht mit Ihrem Modell stören möchten.
* Speichern Sie Ihr Modell. Nach dem Speichern wird der algorithmische Evaluierungsprozess automatisch ausgeführt. Es kann jedoch bis zu 7 Tage dauern, bis dieser Vorgang abgeschlossen ist. [!DNL Audience Manager] sendet eine E-Email, wenn der Algorithmus abgeschlossen ist und die Ergebnisse für die Erstellung von Eigenschaften verfügbar sind.
* Erstellen Sie algorithmische Eigenschaften in [!UICONTROL Trait Builder].
* Eigenschaften in Segmenten kombinieren [!UICONTROL Segment Builder].
* Erstellen und senden Sie Segmentdaten an ein Ziel.

## Fehlerbehebung {#troubleshooting}

Wir deaktivieren ein algorithmische Modell, das keine Daten für drei aufeinander folgende Ausführungen generiert. Beachten Sie, dass Sie den Status des Modells nicht wieder auf aktiv setzen können. Um sicherzustellen, dass Ihre Modelle Daten generieren, sollten Sie Modelle aus Datenquellen mit ausreichenden Eigenschaften erstellen, um Daten zu sammeln.

>[!MORE_ LIKE_ THIS]
>
>* [Ziele](../../features/destinations/destinations.md)
>* [Eigenschaften](../../features/traits/trait-details-page.md)
>* [Segmente](../../features/segments/segments-purpose.md)


## Grundlegendes zu traitweight {#understanding-traitweight}

[!UICONTROL TraitWeight] ist ein proprietärer Algorithmus, der automatisch neue Eigenschaften entdecken soll. Sie vergleicht Eigenschaftsdaten aus Ihren aktuellen Eigenschaften und Segmenten mit allen anderen First- und Drittanbieterdaten, auf die Sie über [!DNL Audience Manager]diese Daten zugreifen können. In diesem Abschnitt finden Sie eine Beschreibung des [!UICONTROL TraitWeight] algorithmischen Erkennungsprozesses.

<!-- traitweight.xml -->

![](assets/algo_model.png)

Die folgenden Schritte beschreiben den [!UICONTROL TraitWeight] Bewertungsprozess.

### Schritt 1: Erstellen eines Ausgangswerts für den Trait-Vergleich

Um eine Ausgangslinie zu erstellen, [!UICONTROL TraitWeight] werden alle mit einer Zielgruppe verknüpften Eigenschaften für ein 30-, 60-, 90-tägiges oder 90-tägiges Intervall gemessen. Als Nächstes werden Eigenschaften entsprechend ihrer Häufigkeit und deren Korrelation eingestuft. Die Häufigkeit misst die Gemeinsamkeit. Korrelation misst die Wahrscheinlichkeit, dass ein Merkmal nur in der Grundlinienzielgruppe vorhanden ist. Häufig angezeigte Eigenschaften weisen eine hohe Gemeinsamalität auf, ein wichtiges Merkmal, mit dem ein gewichtetes Ergebnis festgelegt wird, wenn es mit Eigenschaften kombiniert wird, die in den ausgewählten Datenquellen entdeckt wurden.

### Schritt 2: Identische Eigenschaften in der Datenquelle suchen

Nachdem Sie einen Ausgangswert für den Vergleich erstellt haben, sucht der Algorithmus nach identischen Eigenschaften in den ausgewählten Datenquellen. Führt in diesem Schritt alle erkannten Eigenschaften [!UICONTROL TraitWeight] durch und vergleicht sie mit der Grundlinie. Im Gegensatz zu der Grundlinie sind ungewöhnliche Eigenschaften jedoch höher als die, die häufiger angezeigt werden. Seltene Eigenschaften bieten einen hohen Grad an Spezifität. [!UICONTROL TraitWeight] bewertet Kombinationen aus allgemeinen Grundlinieneigenschaften und ungewöhnlichen (hochgradig spezifischen) Datenquelleneigenschaften als einflussreicher oder wünschenswerter als für beide Datensätze. In der Tat erkennt unser Modell diese großen, allgemeinen Eigenschaften und weist Datensätzen mit hohen Korrelationen keine übermäßige Priorität zu. Seltene Eigenschaften erhalten höhere Priorität, da sie eher neue, Unique Users als Eigenschaften darstellen, die über die gesamte Pinnwand hinweg zu hoch sind.

### Schritt 3: Gewichtung zuweisen

In diesem Schritt [!UICONTROL TraitWeight] werden neu erkannte Eigenschaften nach dem Einfluss oder der gewünschten Priorität sortiert. Die Gewichtung ist ein Prozentsatz, der zwischen 0% und 100% ausführt. Eigenschaften, die näher an 100% rangiert sind, bedeuten, dass sie eher wie die Zielgruppe in Ihrer Grundlinienpopulation sind. Stark gewichtete Eigenschaften sind außerdem wertvoll, da sie neue individuelle Benutzer darstellen, die sich ähnlich wie die etablierte Grundzielgruppe verhalten. Denken Sie daran, [!UICONTROL TraitWeight] Eigenschaften mit hoher Gemeinsamalität in der Grundlinie und hoher Spezifität in den Vergleichsdatenquellen zu berücksichtigen, um wertvoller als die in den einzelnen Datensätzen geläufigen Eigenschaften zu sein.

### Schritt 4: Auswertungsbenutzer

Jeder Benutzer in den ausgewählten Datenquellen erhält ein Benutzerergebnis, das der Summe aller Gewichtungen der einflussreichsten Eigenschaften des Benutzerprofils entspricht. Die Benutzerbewertungen werden dann zwischen 0 und 100% normalisiert.

### Schritt 5: Ergebnisse anzeigen und mit diesen arbeiten

Audience Manager zeigt Ihr gewichtetes Modell in an [!UICONTROL Trait Builder]. Wenn Sie eine algorithmische Eigenschaft erstellen möchten, [!UICONTROL Trait Builder] können Sie Eigenschaften basierend auf dem gewichteten Ergebnis erstellen, das durch den Algorithmus während einer Datenausführung generiert wurde. Sie können eine höhere Genauigkeit wählen, um nur Benutzer zu qualifizieren, die sehr hohe Benutzerbewertungen haben und daher sehr ähnlich der Grundzielgruppe sind und nicht den Rest der Zielgruppe. Wenn Sie eine größere Zielgruppe erreichen möchten (Reichweite), können Sie die Genauigkeit verringern.

### Schritt 6: Bewerten Sie die Bedeutung einer Eigenschaft über Verarbeitungszyklen hinweg erneut.

In regelmäßigen Abständen [!UICONTROL TraitWeight] wird die Wichtigkeit einer Eigenschaft auf Grundlage der Größe und Änderung der Bevölkerung dieser Eigenschaft erneut ausgewertet. Dies geschieht, wenn die Anzahl der Benutzer, die für diese Eigenschaft qualifiziert sind, im Laufe der Zeit erhöht oder verringert wird. Dieses Verhalten wird in Eigenschaften, die sehr groß werden, sehr klar dargestellt. Angenommen, der Algorithmus verwendet Eigenschaften A für das Modellieren. Wenn die Population von Eigenschaften zunimmt, [!UICONTROL TraitWeight] bewerten Sie die Relevanz dieser Eigenschaft erneut und weisen eine niedrigere Bewertung zu oder ignorieren sie. In diesem Fall ist Merkmala zu häufig oder sehr umfangreich, um seine Population hervorzuheben. Nachdem der [!UICONTROL TraitWeight] Wert von Eigenschaften A (oder im Modell ignoriert) verringert wurde, verringert sich die Population der algorithmischen Eigenschaft. Die Liste einflussreicher Eigenschaften spiegelt die Evolution der Grundlinienpopulation wider. Verwenden Sie die Liste der einflussreichsten Eigenschaften, um zu verstehen, warum diese Änderungen vorgenommen wurden.

Verwandte Links:

* [Modellaufbau](../../features/algorithmic-models/create-model.md)
* [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md)

## Zeitplan für algorithmische Modelle und Eigenschaften aktualisieren {#update-schedule}

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
     </ul> </p> <p>Modelle, die nach dem Erstellungstermin erstellt oder geklont wurden, werden am folgenden Tag verarbeitet. </p> <p>Wenn die erste Ausführung eines Modells keine Daten generiert, wird es ein zweites Mal ausgeführt, am nächsten Tag. Wenn der zweite Versuch auch keine Daten generiert, erfolgt ein dritter Versuch, am nächsten Tag. Das Modell wird beendet, wenn der dritte Versuch auch keine Daten generiert. In diesem Fall deaktivieren wir das Modell. Weitere Informationen finden Sie unter <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Fehlerbehebung für algorithmische Modelle</a>. </p> </td>
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

## Modelllistenansicht {#models-list-view}

Die Listenansicht ist ein zentraler Arbeitsbereich, mit dem Sie Modelle erstellen, überprüfen und verwalten können.

<!-- c_models_list_view.xml -->

Die Modellseite enthält Funktionen und Tools, die Ihnen dabei helfen:

* Erstellen Sie neue Modelle.
* Verwalten Sie vorhandene Modelle (bearbeiten, anhalten, löschen oder klonen).
* Suchen Sie nach Modellen nach Namen.
* Erstellen Sie algorithmische Eigenschaften mit einem beliebigen Modell.

## Modellzusammenfassung {#models-summary-view}

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
   <td colname="col2"> <p>Zeigt <a href="../../features/traits/trait-accuracy-reach.md"> Genauigkeit und</a> Reichweitendaten für das letzte Modell an. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Modell-Verarbeitungsverlauf</span> </p> </td> 
   <td colname="col2"> <p>Zeigt das Verarbeitungsdatum und die Uhrzeit der letzten 10 Ausführungen an und ob Daten auf diesen ausgeführt wurden. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Einflussreiche Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>Die Tabelle <span class="wintitle"> Einflussreiche Eigenschaften</span> : </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Listet die 50 wichtigsten Einflusseigenschaften auf, die am besten in der Grundlinienpopulation des Modells dargestellt werden. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Ordnet jede Eigenschaft in der Reihenfolge ihrer <span class="wintitle"> relativen Gewichtung</span> zu. Die <span class="wintitle"> relative Gewichtung</span> sortiert neu erkannte Eigenschaften in Hinblick auf Einfluss oder Wünschbarkeit. Die Gewichtung ist ein Prozentsatz, der zwischen 0% und 100% ausführt. Eigenschaften, die näher an 100% rangiert sind, bedeuten, dass sie eher wie die Zielgruppe in Ihrer Grundlinienpopulation sind. Siehe <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Traitweight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Zeigt die 30-Tage-individuellen Werte und die Gesamtfüllung für die einzelnen Merkmale an. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Eigenschaften mit Modell</span> </p> </td>
   <td colname="col2"> <p>Zeigt eine Liste der algorithmischen Eigenschaften basierend auf dem ausgewählten Modell an. Klicken Sie auf einen Eigenschaftsnamen oder eine Eigenschafts-ID, um weitere Informationen zu der Eigenschaft zu erhalten. Wählen <b><span class="uicontrol"> Sie Neue Eigenschaften mit Modell</span></b> erstellen, um zum algorithmischen Eigenschaftserstellungsprozess zu wechseln. </p> <p>Die Abschnittsbeschriftung ändert sich je nach dem Namen Ihres Modells. Beispiel: Sie erstellen ein Modell und geben das Modell A ein. Wenn Sie die Zusammenfassungsseite laden, wird der Name dieses Abschnitts in <span class="wintitle"> Eigenschaften mit Modell A geändert</span>. </p> </td>
  </tr>
 </tbody>
</table>
---
description: Erstellen und verwalten Sie die Eigenschaften oder Segmente, die bei der Modellierung mit Look-Alias verwendet werden.
keywords: relative weight, lookalike
seo-description: Erstellen und verwalten Sie die Eigenschaften oder Segmente, die bei der Modellierung mit Look-Alias verwendet werden.
seo-title: Look-Alike-Modellierung
solution: Audience Manager
title: Look-Alike-Modellierung
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1590'
ht-degree: 1%

---


# Understanding [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Neue Benutzer suchen mit [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] hilft Ihnen bei der Erkennung neuer, einzigartiger Audiencen durch die automatisierte Analyse von Daten. Der Prozess wird Beginn, wenn Sie ein [!UICONTROL trait] oder [!UICONTROL segment], ein Zeitintervall sowie ein Erstanbieter- und ein Drittanbieter auswählen [!UICONTROL data sources]. Ihre Auswahl bietet die Eingaben für das algorithmische Modell. Wenn der Analyseverfahren ausgeführt wird, sucht er anhand gemeinsamer Merkmale der ausgewählten Population nach infrage kommenden Benutzern. Nach Abschluss dieser Daten stehen Ihnen im [Eigenschaften-Builder](../../features/traits/about-trait-builder.md) zur Verfügung, mit dem Sie Eigenschaften erstellen können, die auf der [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md)basieren. Darüber hinaus können Sie Segmente erstellen, die algorithmische Eigenschaften mit [!UICONTROL rules-based traits] kombinieren und weitere Qualifizierungsanforderungen mit [!DNL Boolean] Ausdrücken und Vergleichsoperatoren hinzufügen. [!UICONTROL Look-Alike Modeling] gibt Ihnen eine dynamische Möglichkeit, Werte aus allen verfügbaren Eigenschaftsdaten zu extrahieren.

## Vorteile {#advantages}

Zu den wichtigsten Vorteilen der Verwendung [!UICONTROL Look-Alike Modeling] zählen:

* **Datengenauigkeit:** Der Algorithmus wird regelmäßig ausgeführt, was dazu beiträgt, die Ergebnisse aktuell und relevant zu halten.
* **Automatisierung:** Sie müssen nicht viele statische Regeln verwalten. Der Algorithmus findet Audiencen für Sie.
* **Sparen Sie Zeit und Mühe:** Mit unserem Modellierungsprozess brauchen Sie nicht zu erraten, was funktioniert [!UICONTROL traits]/[!UICONTROL segments] oder Zeitaufwand für Kampagnen zu verbringen, um neue Audiencen zu entdecken. Das Modell kann das für Sie tun.
* **Zuverlässigkeit:** Die Modellierung funktioniert mit serverseitigen Erkennungs- und Qualifizierungsprozessen, die Ihre eigenen Daten und ausgewählte Drittanbieterdaten auswerten, auf die Sie Zugriff haben. Das bedeutet, dass Sie die Besucher auf Ihrer Site nicht sehen müssen, um sie für eine Eigenschaft zu qualifizieren.

## Arbeitsablauf{#workflow}

Sie verwalten Modelle in **[!UICONTROL Audience Data > Models]**. Auf hoher Ebene umfasst der Workflow-Prozess Folgendes:

* Wählen Sie die Ausgangsdaten aus, die der Algorithmus auswerten soll. Dazu gehören ein [!UICONTROL trait] oder [!UICONTROL segment], ein Zeitraum und [!UICONTROL data sources] (Ihre eigenen Daten und Daten von Drittanbietern, auf die Sie bereits Zugriff haben [!DNL Audience Manager]). Im Arbeitsablauf für die Modellerstellung können Sie die Elemente ausschließen, [!UICONTROL traits] die Sie nicht in Ihr Modell eingreifen möchten.
* Speichern Sie Ihr Modell. Nach dem Speichern wird der algorithmische Evaluierungsprozess automatisch ausgeführt. Beachten Sie jedoch, dass dieser Vorgang bis zu 7 Tage dauern kann. [!DNL Audience Manager] sendet Ihnen eine E-Mail, wenn der Algorithmus abgeschlossen ist und Ergebnisse zur [!UICONTROL trait] Erstellung verfügbar sind.
* Erstellen Sie algorithmisch [!UICONTROL traits] in [!UICONTROL Trait Builder].
* Kombinieren Sie [!UICONTROL traits] zu [!UICONTROL segments] in [!UICONTROL Segment Builder].
* Erstellen und senden Sie [!UICONTROL segment] Daten an eine [!UICONTROL destination].

## Fehlerbehebung {#troubleshooting}

Wir deaktivieren alle, [!UICONTROL Look-Alike Model] bei denen die Generierung von Daten für drei aufeinander folgende Vorgänge fehlschlägt. Beachten Sie, dass Sie den Status des Modells anschließend nicht wieder auf &quot;aktiv&quot;zurücksetzen können. Um sicherzustellen, dass Ihre Modelle Daten generieren, empfehlen wir Ihnen, Modelle aus Datenquellen zu erstellen, aus denen ausreichend Daten gesammelt [!UICONTROL traits] werden können.

## Understanding [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] ist ein proprietärer Algorithmus, der entwickelt wurde, um neue [!UICONTROL traits] automatisch zu entdecken. Es vergleicht die [!UICONTROL trait] Daten Ihrer aktuellen Daten [!UICONTROL traits] und [!UICONTROL segments] mit allen anderen Erstanbieter- und Drittanbieterdaten, auf die Sie Zugriff haben [!DNL Audience Manager]. In diesem Abschnitt finden Sie eine Beschreibung des [!UICONTROL TraitWeight] algorithmischen Erkennungsprozesses.

![](assets/algo_model.png)

Die folgenden Schritte beschreiben den [!UICONTROL TraitWeight] Bewertungsprozess.

### Schritt 1: Erstellen einer Grundlinie für [!UICONTROL Trait] Vergleich

Um eine Grundlinie zu erstellen, [!UICONTROL TraitWeight] misst alle mit einer Audience verbundenen [!UICONTROL traits] Werte für einen Zeitraum von 30, 60 oder 90 Tagen. Als Nächstes wird sie [!UICONTROL traits] nach ihrer Häufigkeit und ihrer Korrelation eingestuft. Die Häufigkeit misst die Gemeinsamkeit. Korrelation misst die Wahrscheinlichkeit, dass eine [!UICONTROL trait] nur in der Audience des Ausgangswerts vorhanden ist. [!UICONTROL Traits] die häufig auftreten, werden als Zeichen hoher Gemeinsamkeit bezeichnet, ein wichtiges Merkmal, das verwendet wird, um eine gewichtete Punktzahl festzulegen, wenn es mit der [!UICONTROL traits] Entdeckung in Ihrer Auswahl kombiniert wird [!UICONTROL data sources].

### Schritt 2: Suchen Sie im [!UICONTROL Traits] Abschnitt [!UICONTROL Data Source]

Nachdem er eine Vergleichsgrundlinie erstellt hat, sucht der Algorithmus [!UICONTROL traits] in Ihrer Auswahl nach identischen [!UICONTROL data sources]. In diesem Schritt [!UICONTROL TraitWeight] führt eine Frequenzzählung aller entdeckten Daten durch [!UICONTROL traits] und vergleicht sie mit der Grundlinie. Im Gegensatz zum Ausgangswert [!UICONTROL traits] sind die ungewöhnlichen Werte jedoch höher als diejenigen, die häufiger auftreten. Selten [!UICONTROL traits] soll eine hohe Spezifität aufweisen. [!UICONTROL TraitWeight] bewertet Kombinationen von gemeinsamem Ausgangswert [!UICONTROL traits] und ungewöhnlichen (hochspezifischen) Kombinationen [!UICONTROL data source] als einflussreicher oder wünschenswerter als [!UICONTROL traits] [!UICONTROL traits] für beide Datensätze üblich. In der Tat erkennt unser Modell diese großen, gemeinsamen [!UICONTROL traits] und weist keine übermäßige Priorität zu Datensätzen mit hohen Korrelationen. Selten erhalten [!UICONTROL traits] Sie eine höhere Priorität, da sie mit größerer Wahrscheinlichkeit neue, eindeutige Benutzer repräsentieren als [!UICONTROL traits] mit hoher Gemeinsamkeit.

### Schritt 3: Gewichtung zuweisen

In diesem Schritt [!UICONTROL TraitWeight] Ranglisten neu entdeckt [!UICONTROL traits] in der Reihenfolge Einfluss oder wünschenswert. Die Skala der Gewichtung ist ein Prozentwert zwischen 0 % und 100 %. [!UICONTROL Traits] Wenn sie näher an 100 % liegen, sind sie eher wie die Audience in Ihrer Grundgesamtheit. Auch sind stark gewichtete [!UICONTROL traits] Werte wertvoll, da sie neue, individuelle Benutzer darstellen, die sich ähnlich wie Ihre etablierte, grundlegende Audience verhalten. Denken Sie daran, [!UICONTROL TraitWeight] betrachtet [!UICONTROL traits] die hohe Gemeinsamkeit im Ausgangswert und die hohe Spezifität der verglichenen Datenquellen als wertvoller als [!UICONTROL traits] üblich in jedem Datensatz.

### Schritt 4: Benutzer auswerten

Jeder Benutzer in der ausgewählten Liste [!UICONTROL data sources] erhält eine Benutzerbewertung, die der Summe aller Gewichtungen des Einflussbereichs auf das Profil [!UICONTROL traits] des Benutzers entspricht. Die Benutzerwerte werden dann zwischen 0 und 100 % normalisiert.

### Schritt 5: Anzeigen und Arbeiten mit Ergebnissen

[!DNL Audience Manager] zeigt Ihre gewichteten Modellergebnisse an [!UICONTROL Trait Builder]. Wenn Sie eine [!UICONTROL algorithmic trait]erstellen möchten, [!UICONTROL Trait Builder] können Sie [!UICONTROL traits] auf der Grundlage des gewichteten Ergebnisses erstellen, das der Algorithmus während einer Datenausführung generiert hat. Sie können eine höhere Genauigkeit wählen, um nur Benutzer mit sehr hohen Benutzerwerten zu qualifizieren, die sich daher sehr ähnlich wie die Audience vor dem Ausgangswert und nicht mit der übrigen Audience verhalten. Wenn Sie eine größere Audience (Reichweite) erreichen möchten, können Sie die Genauigkeit herabsetzen.

### Schritt 6: Die Bedeutung eines [!UICONTROL Trait] Verarbeitungszyklus neu bewerten

In regelmäßigen Abständen [!UICONTROL TraitWeight] wird die Bedeutung einer [!UICONTROL trait] auf der Grundlage der Größe und Veränderung der Bevölkerung dieser [!UICONTROL trait]neu bewertet. Dies geschieht, wenn die Anzahl der dafür qualifizierten Benutzer mit der Zeit [!UICONTROL trait] steigt oder abnimmt. Dieses Verhalten wird am deutlichsten in Eigenschaften gesehen, die sehr groß werden. Nehmen wir beispielsweise an, der Algorithmus verwendet [!UICONTROL trait A] die Modellierung. Wenn die Population der [!UICONTROL trait A] wächst, bewertet [!UICONTROL TraitWeight] die Bedeutung dieser [!UICONTROL trait] und kann eine niedrigere Punktzahl zuweisen oder ignorieren. In diesem Fall [!UICONTROL trait A] ist zu verbreitet oder zu groß, um etwas Bedeutendes über seine Bevölkerung zu sagen. Nachdem der Wert des Modells [!UICONTROL TraitWeight] verringert [!UICONTROL trait A] (oder im Modell ignoriert) wurde, nimmt die Population der algorithmischen Eigenschaft ab. Die Liste des Einflusses [!UICONTROL traits] spiegelt die Entwicklung der Grundpopulation wider. Nutzen Sie die Liste des Einflussreichen, [!UICONTROL traits] um zu verstehen, warum diese Änderungen stattfinden.

Verwandte Links:

* [Modellaufbau](../../features/algorithmic-models/create-model.md)
* [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md)

## Zeitplan aktualisieren für [!UICONTROL Look-Alike Models] und [!UICONTROL Traits] {#update-schedule}

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
   <td colname="col1"> <b>Erstellen oder Klonen eines Modells</b> </td>
   <td colname="col2"> <p>Für neue oder geklonte [!UICONTROL Look-Alike Models] läuft der Erstellungsprozess einmal täglich um: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17:00 Uhr EST (November - März) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18:00 Uhr EDT (März - November) </li> 
     </ul> </p> <p>Modelle, die nach Ablauf der Erstellungsfrist erstellt oder geklont wurden, werden am folgenden Tag verarbeitet. </p> <p>Wenn die erste Ausführung eines Modells keine Daten generiert, wird sie am nächsten Tag ein zweites Mal ausgeführt. Wenn der zweite Versuch auch keine Daten generiert, wird am nächsten Tag ein dritter Versuch unternommen. Das Modell wird nicht mehr ausgeführt, wenn beim dritten Versuch auch keine Daten generiert werden. In diesem Fall deaktivieren wir das Modell. Weitere Informationen finden Sie unter <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Fehlerbehebung für Look-Alike-Modelle</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Modell aktualisieren</b> </td> 
   <td colname="col2"> <p>Unter idealen Bedingungen werden vorhandene Modelle an Wochentagen, mindestens alle 7 Tage, ausgeführt. Wenn Sie z. B. am Montag ein Modell erstellen (bis zum Termin), wird es spätestens am folgenden Montag aktualisiert. </p> <p>Ein Modell wird erneut ausgeführt, wenn eine der folgenden Bedingungen erfüllt ist: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Die letzte Runde war nicht erfolgreich. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Es wurde vor UND in den letzten 7 Tagen noch nicht ausgeführt UND das Modell hat mindestens eine aktive Eigenschaft. </li>
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
   <td colname="col1"> <b>Eigenschaften erstellen</b> </td> 
   <td colname="col2"> <p>Die Erstellung der Eigenschaften wird jeden Tag von Montag bis Freitag durchgeführt. Im Allgemeinen werden in der Benutzeroberfläche innerhalb von 48 Stunden neue algorithmische Eigenschaften angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Eigenschaften aktualisieren</b> </td> 
   <td colname="col2"> <p>Vorhandene Eigenschaften werden mindestens einmal alle 7 Tage aktualisiert und folgen dem Zeitplan für Modellaktualisierungen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ansicht zur Liste von Modellen {#models-list-view}

Die Liste Ansicht ist ein zentraler Arbeitsbereich, der Ihnen beim Erstellen, Überprüfen und Verwalten von Modellen hilft.

Die Seite &quot; [!UICONTROL Models] Liste&quot;enthält Funktionen und Tools, mit denen Sie:

* Erstellen Sie neue Modelle.
* Verwalten Sie vorhandene Modelle (bearbeiten, anhalten, löschen oder klonen).
* Suchen Sie nach Modellen anhand des Namens.
* Erstellen Sie [!UICONTROL algorithmic traits] mit einem beliebigen Modell.

## Ansicht der Modellzusammenfassung {#models-summary-view}

Auf der Zusammenfassungsseite werden Modelldetails wie Name, Reichweite/Genauigkeit, Verarbeitungsverlauf und aus dem Modell [!UICONTROL traits] erstellte Details angezeigt. Die Seite enthält auch Einstellungen, mit denen Sie Modelle erstellen und verwalten können. Klicken Sie auf einen Modellnamen in der Zusammenfassungs-Liste, um dessen Details anzuzeigen.

Die Modellübersichtsseite enthält die folgenden Abschnitte.

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
   <td colname="col2"> <p>Beinhaltet grundlegende Informationen zum Modell, z. B. den Namen und den Zeitpunkt des letzten Ausführung. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Modellreichweite und -genauigkeit</span> </p> </td> 
   <td colname="col2"> <p>Zeigt <a href="../../features/traits/trait-accuracy-reach.md"> Genauigkeit und Reichweitendaten</a> für die letzte Modellausführung an. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Modellverarbeitungsverlauf</span> </p> </td> 
   <td colname="col2"> <p>Zeigt das Datum und die Uhrzeit der Verarbeitung der letzten 10 Ausführung und an, ob Daten für diese Ausführung generiert wurden. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Einflussreiche Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>Tabelle mit <span class="wintitle"> einflussreichen Eigenschaften</span> : </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Liste der 50 einflussreichsten Eigenschaften, die am besten in der Grundgesamtheit des Modells dargestellt werden. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Richtet die einzelnen Eigenschaften nach ihrem Rang <span class="wintitle"> Relative Gewichtung</span> aus. Die <span class="wintitle"> Relative Gewichtung</span> sortiert neu entdeckte Eigenschaften nach Einfluss oder Zweckmäßigkeit. Die Skala der Gewichtung ist ein Prozentwert zwischen 0 % und 100 %. Eigenschaften, die näher an 100 % liegen, sind eher wie die Audience in Ihrer Grundgesamtheit. Siehe <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Grundlegendes zu TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Zeigt die 30-Tage-Uniques und die Gesamtanzahl der Eigenschaften für jede Eigenschaft an. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Eigenschaften mit Modell</span> </p> </td>
   <td colname="col2"> <p>Zeigt eine Liste der algorithmischen Eigenschaften, die auf dem ausgewählten Modell basieren. Klicken Sie auf einen Eigenschaftsnamen oder eine Eigenschafts-ID, um weitere Informationen zu den Eigenschaften anzuzeigen. Wählen Sie "Neue Eigenschaft mit Modell <b><span class="uicontrol"></span></b> erstellen", um zum algorithmischen Eigenschaftenerstellungsprozess zu wechseln. </p> <p>Die Abschnittbeschriftung ändert sich je nach Name des Modells. Beispiel: Sie erstellen ein Modell und geben ihm einen Namen für Modell A. Wenn Sie die Zusammenfassungsseite laden, wird der Name dieses Abschnitts in <span class="wintitle"> Eigenschaften mit Modell A</span>geändert. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Ziele ](../../features/destinations/destinations.md)
>* [Eigenschaften ](../../features/traits/trait-details-page.md)
>* [Segmente ](../../features/segments/segments-purpose.md)


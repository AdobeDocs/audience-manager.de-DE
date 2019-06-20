---
description: Gibt Daten zur Anzahl der eindeutigen Benutzer zurück, die für alle Ihre ersten und dritten Eigenschaften freigegeben wurden.
seo-description: Gibt Daten zur Anzahl der eindeutigen Benutzer zurück, die für alle Ihre ersten und dritten Eigenschaften freigegeben wurden.
seo-title: Überschneidungsbericht zwischen Eigenschaften
solution: Audience Manager
title: Überschneidungsbericht zwischen Eigenschaften
uuid: 7 fb 3 fc 9 e -0 e 0 b -492 a -9 c 3 a -04356 afb 19 c 7
translation-type: tm+mt
source-git-commit: 4dc8aad623198cbc24c5c76ac3818d7ee00e9a5e

---


# Überschneidungsbericht zwischen Eigenschaften{#trait-to-trait-overlap-report}

Gibt Daten zur Anzahl der eindeutigen Benutzer zurück, die für alle Ihre ersten und dritten Eigenschaften freigegeben wurden.

>[!NOTE]
>
>Die Überlappungsberichte in Audience Manager berücksichtigen RBAC-Prinzipien. Sie können nur Eigenschaften aus Datenquellen anzeigen, auf die Sie Zugriff auf die [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md) haben, zu der Sie gehören.

<!-- 

c_overlap_reports.xml

 -->

## Überblick

Der [!UICONTROL Trait-to-Trait Overlap] Bericht gibt Daten zu den % der Unique Users zurück, die zwischen all Ihren eigenen Eigenschaften und Ihren Drittanbietereigenschaften freigegeben wurden. Dieser Bericht hilft Ihnen bei der Optimierung:

* Erstellen Sie Segmente mit hoher oder niedriger Überschneidung, je nach Ihren Anforderungen. Eigenschaften mit hoher Überlappung bieten eine zielgruppe, aber weniger individuelle Besucher. Eigenschaften mit geringer Überlappung können hilfreich sein, um einen größeren, individuellen Besucher zu erreichen.
* Validieren von Eigenschaftsdaten von Drittanbietern: Eine starke Überlappung zwischen ähnlichen ersten und dritten Eigenschaften empfiehlt, dass die Eigenschaft von Ihrem Datenpartner genau und vertrauenswürdig ist. Umgekehrt kann eine niedrige Überlappung darauf hinweisen, dass ein Drittanbietermerkmal möglicherweise nicht dieselben Informationen wie Ihre eigene Erstanbieter-Eigenschaft enthält.
* Finden Sie unerwartete Überlappungen zwischen Eigenschaften heraus und verwenden Sie diese Informationen, um innovative Segmente zu erstellen.

## Beispielbericht

Die folgende Abbildung zeigt eine allgemeine Übersicht über Elemente im [!UICONTROL Trait-to-Trait Overlap] Bericht.

>[!NOTE]
>
>Der [!UICONTROL Trait-to-Trait Overlap] Bericht gibt ein leeres Feld zurück, wenn es die gleiche Eigenschaft mit sich selbst vergleicht.

![](assets/trait-to-trait-overlap.png)

## Drilldown für einzelne Datenpunkte

Wählen Sie einen einzelnen Punkt aus, um die Datendetails in einem Popup-Fenster anzuzeigen. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## Trait-to-Trait-Überlappungs-Datenfelder definiert {#field-definitions}

Beschreibt die im Popup-Fenster angezeigten Metriken, wenn Sie auf einen einzelnen Datenpunkt klicken.

<!-- 

r_t2t_data_pop.xml

 -->

Das Popup für den [!UICONTROL Trait-to-Trait Overlap] Bericht enthält die folgenden Metriken. Beachten Sie, dass die Metrik &quot;Individuelle Werte&quot; in der Tabelle Ihre *Echtzeitbenutzer repräsentiert*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Datenanbieter-Name</span></b> </td> 
   <td colname="col2"> Name des Eigentümers des Merkmals. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Datenprovider-Typ</span></b> </td> 
   <td colname="col2">Definiert den Typ des Anbieters, zu dem ein Merkmal gehört. Kann entweder: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Erstanbieter (eigene Eigenschaft). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Drittanbieter (von einem externen Partner/Anbieter). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschafts-ID</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für diese Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaftsname</span></b> </td> 
   <td colname="col2"> Name der Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überlappung %</span></b> </td> 
   <td colname="col2"> Zeigt die % der eindeutigen Überlappung zwischen Vergleichseigenschaften (überlappen Uniques/Eigenschafteneindeutige Werte). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überlappende Uniques</span></b> </td> 
   <td colname="col2"> <p>Um die Überschneidung % zu erhalten, verwendet Audience Manager die folgende Formel:</p> <p>Überlappende Uniques/(Basissegmente Individuelle Werte + Überlappende Segmente - Überlappende Uniques)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait Uniques</span></b> </td> 
   <td colname="col2"> Die Anzahl der individuellen Besucher in der Eigenschaft. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Berichtsergebnisse mit den Datenreglern filtern](../../reporting/dynamic-reports/data-sliders.md)
>* [In dynamischen Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Erklärung der Berichtsymbole und Tools](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Überlappungsberichte: Zeitplan und Mindestgröße des Segments aktualisieren](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datenstichproben und Fehlersätze in ausgewählten Audience Manager-Berichten…](../../reporting/report-sampling.md)
>* [CSV-Dateien für Überlappungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)
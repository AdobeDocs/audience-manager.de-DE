---
description: Eigenschaftenausschluss bietet zusätzliche Steuerelemente im Modellierungsarbeitsablauf, mit denen Sie dem Modell die erforderlichen Schutzrails hinzufügen können, basierend auf Ihren Kenntnissen und regulatorischen Vorschriften. Verwenden Sie die Option "Ausnahmen" , um auszuwählen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.
seo-description: Eigenschaftenausschluss bietet zusätzliche Steuerelemente im Modellierungsarbeitsablauf, mit denen Sie dem Modell die erforderlichen Schutzrails hinzufügen können, basierend auf Ihren Kenntnissen und regulatorischen Vorschriften. Verwenden Sie die Option "Ausnahmen" , um auszuwählen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.
seo-title: Algorithmische Modelleigenschaften - Ausschluss
title: Algorithmische Modelleigenschaften - Ausschluss
uuid: 1359800 b -6 e 6 c -41 e 1-88 b 4-23 d 31952 abb 3
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Algorithmische Modelle: Eigenschaftenausschluss {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] bietet zusätzliche Steuerelemente im Modellierungsarbeitsablauf, mit denen Sie dem Modell die erforderlichen Schutzrails hinzufügen können, basierend auf Ihren Kenntnissen und regulatorischen Vorschriften. Verwenden Sie die [!UICONTROL Exclusions] Option, um auszuwählen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.

## Nutzungsszenarios {#use-cases}

Im Folgenden finden Sie einige Anwendungsfälle, die Sie ansprechen [!UICONTROL Trait Exclusion]können:

* [!UICONTROL Trait Exclusion] ermöglicht es Ihnen, bestimmte Catch-alle-Eigenschaften, wie z. B. Site-Besuchereigenschaften, auszuschließen, sodass Sie das Modell nicht verfälschen und zu stagnierenden Ergebnissen führen.
* Sie können Eigenschaften entfernen, über die Sie nichts wissen oder die nicht von einer Datenquelle vertrauen, um die einflussreiche Eigenschaften besser verstehen zu können.
* Sie können bestimmte Eigenschaften (z. B. demografische Eigenschaften) ausschließen, um die möglichen Compliance-Verpflichtungen zu erfüllen.

>[!IMPORTANT]
>
>Ein wichtiger Hinweis zum dritten Verwendungsfall. Wenn der Drittanbieter-Datenprovider dem Datenfeed *nach Erstellung des Modells*eine neue demografische Eigenschaft hinzufügt, wird die Eigenschaft automatisch vom Modell aufgenommen. Sie können Eigenschaften nicht aus der Modellierung ausschließen, nachdem Sie das Modell erstellt haben. Siehe [Wichtige Aspekte und Einschränkungen](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Seien Sie vorsichtig, wenn Sie diese Funktion verwenden und mit dem Datenanbieter zusammenarbeiten, um sicherzustellen, dass Sie über Änderungen an der Feed-Struktur informiert werden.

![](assets/lam_exclude_traits.png)

## Verwenden von Eigenschaftsausnahmen {#how-to-use}

Verwenden Sie den [Arbeitsablauf zum Erstellen von Modellen](../../features/algorithmic-models/create-model.md#build-model) , um neue algorithmische Modelle zu erstellen.

1. Die [!UICONTROL Exclusions] Auswahl wird ausgegraut, bis Sie eine oder mehrere Datenquellen für die Modellierung auswählen.
2. Nachdem Sie eine oder mehrere Datenquellen für die Modellierung ausgewählt haben, klicken **[!UICONTROL Browse All Traits]** Sie auf.
3. Im **[!UICONTROL Select Traits to Exclude]** Fenster können Sie alle Eigenschaften anzeigen, die mit den zuvor ausgewählten Datenquellen verknüpft sind. Wählen Sie die Eigenschaften aus, die Sie ausschließen möchten.
4. Sie können die Eigenschaften nach Eigenschaftstyp filtern oder die Ordner im Eigenschaftenmodus durchsuchen. Beachten Sie, dass Eigenschaftenordner nur die Eigenschaften anzeigen, die mit Ihren ausgewählten Datenquellen verknüpft sind.
5. Drücken **[!UICONTROL Exclude Selected Traits]** Sie auf.

>[!TIP]
>
>Sie können ganze Ordner ausschließen, indem Sie die Ordnereigenschaft ausschließen, anstatt die Eigenschaften im Ordner einzeln auszuklammern. Beispielsweise müssen Sie in einem Ordner mit 20 Eigenschaften nur die Ordnereigenschaft ausschließen, anstatt alle Eigenschaften einzeln auszuschließen.

Wenn Sie Videolehrgänge bevorzugen, sehen Sie sich unsere Video-Demonstration für Trait Exclusion an:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=ger)

## Wichtige Aspekte und Einschränkungen {#important-aspects-and-limitations}

Bitte beachten Sie die folgenden Aspekte und Einschränkungen in Bezug auf [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ausgeschlossene Eigenschaften in der Modellzusammenfassung </p> </td>
   <td colname="col2"> <p>Die ausgeschlossenen Eigenschaften <i>werden</i> in der Ansicht "Modelle - Zusammenfassung" nicht angezeigt. Die ausgeschlossenen Eigenschaften werden nur im Arbeitsablauf "Modell <b><span class="uicontrol"> bearbeiten</span></b> " angezeigt. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rollenbasierte Zugriffssteuerungssteuerung (RBAC) </p> </td>
   <td colname="col2"> <p>Beachten Sie die folgenden Einschränkungen für Unternehmen, die <a href="../../features/administration/administration-overview.md#administration"> RBAC verwenden</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Wenn Sie keinen Zugriff auf die Anzeige einer Eigenschaft haben, <i>können</i> Sie diese Eigenschaft nicht aus dem Modell ausschließen. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Wenn Sie keinen Zugriff auf eine Eigenschaft <i>haben,</i> können Sie diese Eigenschaft nicht in der ausgeschlossenen Eigenschaftsliste anzeigen. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausgeschlossene Eigenschaften nach dem Speichern von Modellen ändern </p> </td>
   <td colname="col2"> <p>Sie können die ausgeschlossenen Eigenschaften nicht ändern, nachdem Sie ein Modell erstellt und gespeichert haben. Wenn Sie die Ergebnisse anpassen möchten, können Sie das Modell klonen und die ausgeschlossenen Eigenschaften ändern. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximale Anzahl von Eigenschaften, die Sie ausschließen können </p> </td>
   <td colname="col2"> <p>Die maximale Anzahl von Eigenschaften, die Sie aus einem Modell ausschließen können, ist 500. Verwenden Sie Ordnereigenschaften, um Ihre Ausschlüsse zu maximieren. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grundlinieneigenschaft ausschließen </p> </td>
   <td colname="col2"> <p>Die Grundlinieneigenschaft wird standardmäßig ausgeschlossen, sodass sie nicht in der <b><span class="uicontrol"> Ausschlussliste</span></b> angezeigt wird, wenn das Modell erstellt wird. </p> </td>
  </tr>
 </tbody>
</table>

## Verwandte Links

* [Grundlagen zu algorithmischen Eigenschaften](/help/using/features/algorithmic-models/understanding-models.md)
* [Eigenschaftenausschluss - Lernprogramm](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
---
description: Eigenschaftenausschluss bietet zusätzliche Steuerelemente im Modellierungsarbeitsablauf, mit denen Sie dem Modell die erforderlichen Schutzrails hinzufügen können, basierend auf Ihren Kenntnissen und regulatorischen Vorschriften. Verwenden Sie die Option "Ausnahmen" , um auszuwählen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.
seo-description: Eigenschaftenausschluss bietet zusätzliche Steuerelemente im Modellierungsarbeitsablauf, mit denen Sie dem Modell die erforderlichen Schutzrails hinzufügen können, basierend auf Ihren Kenntnissen und regulatorischen Vorschriften. Verwenden Sie die Option "Ausnahmen" , um auszuwählen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.
seo-title: Algorithmische Modelleigenschaften - Ausschluss
title: Algorithmische Modelleigenschaften - Ausschluss
uuid: 1359800 b -6 e 6 c -41 e 1-88 b 4-23 d 31952 abb 3
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Algorithmic Models: Trait Exclusion {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] bietet zusätzliche Steuerelemente im Modellierungsarbeitsablauf, mit denen Sie dem Modell die erforderlichen Schutzrails hinzufügen können, basierend auf Ihren Kenntnissen und regulatorischen Vorschriften. Use the [!UICONTROL Exclusions] option to select which traits to ignore when creating models from one or more data sources.

## Nutzungsszenarios {#use-cases}

Here are some use cases you can address with [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] ermöglicht es Ihnen, bestimmte Catch-alle-Eigenschaften, wie z. B. Site-Besuchereigenschaften, auszuschließen, sodass Sie das Modell nicht verfälschen und zu stagnierenden Ergebnissen führen.
* Sie können Eigenschaften entfernen, über die Sie nichts wissen oder die nicht von einer Datenquelle vertrauen, um die einflussreiche Eigenschaften besser verstehen zu können.
* Sie können bestimmte Eigenschaften (z. B. demografische Eigenschaften) ausschließen, um die möglichen Compliance-Verpflichtungen zu erfüllen.

>[!IMPORTANT]
>
>Ein wichtiger Hinweis zum dritten Verwendungsfall. If the third-party data provider adds a new demographic trait to the data feed *after you created the model*, the trait is automatically picked up by the model. Sie können Eigenschaften nicht aus der Modellierung ausschließen, nachdem Sie das Modell erstellt haben. See [Important Aspects &amp; Limitations](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Seien Sie vorsichtig, wenn Sie diese Funktion verwenden und mit dem Datenanbieter zusammenarbeiten, um sicherzustellen, dass Sie über Änderungen an der Feed-Struktur informiert werden.

![](assets/lam_exclude_traits.png)

## How to Use Trait Exclusions {#how-to-use}

Use the [Build a model](../../features/algorithmic-models/create-model.md#build-model) workflow to build new algorithmic models.

1. The [!UICONTROL Exclusions] selection is greyed out until you select one or more data sources for modeling.
2. After selecting one or more data sources for modeling, press **[!UICONTROL Browse All Traits]**.
3. In the **[!UICONTROL Select Traits to Exclude]** window, you can see all traits associated with the data sources you selected previously. Wählen Sie die Eigenschaften aus, die Sie ausschließen möchten.
4. Sie können die Eigenschaften nach Eigenschaftstyp filtern oder die Ordner im Eigenschaftenmodus durchsuchen. Beachten Sie, dass Eigenschaftenordner nur die Eigenschaften anzeigen, die mit Ihren ausgewählten Datenquellen verknüpft sind.
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>Sie können ganze Ordner ausschließen, indem Sie die Ordnereigenschaft ausschließen, anstatt die Eigenschaften im Ordner einzeln auszuklammern. Beispielsweise müssen Sie in einem Ordner mit 20 Eigenschaften nur die Ordnereigenschaft ausschließen, anstatt alle Eigenschaften einzeln auszuschließen.

Wenn Sie Videolehrgänge bevorzugen, sehen Sie sich unsere Video-Demonstration für Trait Exclusion an:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=ger)

## Important Aspects &amp; Limitations {#important-aspects-and-limitations}

Please take note of the following aspects and limitations related to [!UICONTROL Trait Exclusion]:

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
   <td colname="col2"> <p>The excluded traits <i>do not show up</i> in the Models Summary view. You can see the excluded traits only in the <b><span class="uicontrol"> Edit Model</span></b> workflow. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rollenbasierte Zugriffssteuerungssteuerung (RBAC) </p> </td>
   <td colname="col2"> <p>Note the following limitations for companies using <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">If you don't have access to view a trait, you <i>cannot</i> select that trait to be excluded from the model. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">If you don't have access to view a trait, you <i>cannot</i> view that trait in the excluded traits list. </li>
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
   <td colname="col2"> <p>The baseline trait is excluded by default, so it does not show up in the <b><span class="uicontrol"> Exclusions</span></b> list, when building the model. </p> </td>
  </tr>
 </tbody>
</table>

## Verwandte Links

* [Grundlagen zu algorithmischen Eigenschaften](/help/using/features/algorithmic-models/understanding-models.md)
* [Eigenschaftenausschluss - Lernprogramm](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
---
description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-description: Der Eigenschaftsausschluss bietet zusätzliche Steuerelemente in Ihrem Modellarbeitsablauf, mit denen Sie die erforderlichen Schutzleisten zum Modell hinzufügen können, basierend auf Ihrer Domänenkompetenz und Ihren regulatorischen Anforderungen. Verwenden Sie die Option "Ausnahmen", um festzulegen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.
seo-title: Algorithmischer Modelleigenschaftsausschluss
title: Algorithmischer Modelleigenschaftsausschluss
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# Algorithmische Modelle: Eigenschaftsausschluss {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] bietet zusätzliche Steuerelemente in Ihrem Modellierungsarbeitsablauf, mit denen Sie die erforderlichen Schutzschienen zum Modell hinzufügen können, basierend auf Ihrer Domänenkompetenz und Ihren regulatorischen Anforderungen. Verwenden Sie die [!UICONTROL Exclusions] Option, um festzulegen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.

## Nutzungsszenarios {#use-cases}

Im Folgenden finden Sie einige Anwendungsfälle, mit denen Sie sich befassen können [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] ermöglicht es Ihnen, bestimmte allgemeine Eigenschaften auszuschließen, wie z. B. Site-Besuchereigenschaften, sodass Sie das Modell nicht voreinstellen, was zu reduzierten Ergebnissen führt.
* Sie können Eigenschaften, die Sie nicht kennen oder denen Sie nicht vertrauen, aus einer Datenquelle entfernen, um die einflussreichen Eigenschaften besser zu verstehen.
* Sie können bestimmte Eigenschaften, wie demografische Merkmale, ausschließen, um eventuell vorhandene Compliance-Verpflichtungen zu erfüllen.

>[!IMPORTANT]
>
>Ein wichtiger Hinweis zum dritten Verwendungsfall. Wenn der Drittanbieter für Daten eine neue demografische Eigenschaft zum Datenfeed hinzufügt, *nachdem Sie das Modell* erstellt haben, wird die Eigenschaft automatisch vom Modell übernommen. Sie können Eigenschaften nach dem Erstellen des Modells nicht von der Modellierung ausschließen. Siehe [Wichtige Aspekte und Einschränkungen](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Gehen Sie bei Verwendung dieser Funktion vorsichtig vor und arbeiten Sie mit dem Datenanbieter zusammen, um sicherzustellen, dass Sie über Änderungen an der Feed-Struktur informiert werden.

![](assets/lam_exclude_traits.png)

## So verwenden Sie Eigenschaftsausschlüsse {#how-to-use}

Verwenden Sie den Arbeitsablauf [Erstellen eines Modells](../../features/algorithmic-models/create-model.md#build-model) , um neue algorithmische Modelle zu erstellen.

1. Die [!UICONTROL Exclusions] Auswahl wird so lange ausgegraut, bis Sie eine oder mehrere Datenquellen für die Modellierung auswählen.
2. Nach Auswahl einer oder mehrerer Datenquellen zur Modellierung drücken Sie **[!UICONTROL Browse All Traits]**.
3. Im **[!UICONTROL Select Traits to Exclude]** Fenster werden alle Eigenschaften angezeigt, die mit den zuvor ausgewählten Datenquellen verknüpft sind. Wählen Sie die Eigenschaften aus, die Sie ausschließen möchten.
4. Sie können die Eigenschaften nach Eigenschaftstyp filtern oder die Eigenschaftsordner durchsuchen. Beachten Sie, dass Eigenschaftsordner nur die Eigenschaften anzeigen, die mit den ausgewählten Datenquellen verknüpft sind.
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>Sie können ganze Ordner ausschließen, indem Sie die Ordnereigenschaften ausschließen, anstatt die Eigenschaften im Ordner einzeln auszuschließen. In einem Ordner mit 20 Eigenschaften müssen Sie beispielsweise nur die Ordnereigenschaft ausschließen, anstatt alle Eigenschaften einzeln auszuschließen.

Wenn Sie Videolehrgänge bevorzugen, sehen Sie sich unsere Videodemonstration für den Eigenschaftsausschluss an:

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
   <td colname="col1"> <p>Excluded Traits in Models Summary View </p> </td>
   <td colname="col2"> <p>The excluded traits do not show up in the Models Summary view. <i></i> Sie können die ausgeschlossenen Eigenschaften nur im Arbeitsablauf <b><span class="uicontrol"> Modell</span></b> bearbeiten anzeigen. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Role-Based Access Controls (RBAC) </p> </td>
   <td colname="col2"> <p>Note the following limitations for companies using  RBAC:<a href="../../features/administration/administration-overview.md#administration"></a> </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">If you don't have access to view a trait, you cannot select that trait to be excluded from the model.<i></i> </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">If you don't have access to view a trait, you cannot view that trait in the excluded traits list.<i></i> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modify excluded traits after saving model </p> </td>
   <td colname="col2"> <p>You cannot modify the excluded traits after you have created and saved a model. If you want to tweak the results, you can clone the model and change the excluded traits. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximum number of traits you can exclude </p> </td>
   <td colname="col2"> <p>The maximum number of traits you can exclude from a model is 500. Use folder traits to maximize your exclusions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclude baseline trait </p> </td>
   <td colname="col2"> <p>Die Eigenschaft "Grundlinie"wird standardmäßig ausgeschlossen, daher wird sie beim Erstellen des Modells nicht in der Liste " <b><span class="uicontrol"> Ausnahmen</span></b> "angezeigt. </p> </td>
  </tr>
 </tbody>
</table>

Sehen Sie sich das unten stehende Video an, um zu erfahren, wie und warum Sie bestimmte Eigenschaften von einem [!UICONTROL Look-Alike Model]ausschließen.

[!VIDEO](https://video.tv.adobe.com/v/25569/?captions=ger)

## Verwandte Links

* [Algorithmische Eigenschaften](/help/using/features/algorithmic-models/understanding-models.md)
* [Eigenschaftsausschluss - Tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
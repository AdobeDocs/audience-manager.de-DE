---
description: Der Ausschluss von Eigenschaften bietet zusätzliche Steuerelemente in Ihrem Modellierungs-Workflow, sodass Sie dem Modell die erforderlichen Leitplanken hinzufügen können, basierend auf Ihrer Domain-Expertise und den gesetzlichen Anforderungen. Verwenden Sie die Option Ausschlüsse , um festzulegen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.
seo-description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-title: Algorithmic Models  Trait Exclusion
title: Ausschluss algorithmischer Modelle von Eigenschaften
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# Look-alike-Modellierung: Ausschluss von Eigenschaften {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] bietet zusätzliche Steuerelemente in Ihrem Modellierungs-Workflow, sodass Sie dem Modell basierend auf Ihrer Domain-Expertise und den regulatorischen Anforderungen die erforderlichen Leitplanken hinzufügen können. Verwenden Sie die Option [!UICONTROL Exclusions] , um festzulegen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.

## Nutzungsszenarios {#use-cases}

Im Folgenden finden Sie einige Anwendungsfälle, die Sie mit [!UICONTROL Trait Exclusion] beheben können:

* [!UICONTROL Trait Exclusion] können Sie bestimmte allgemeine Eigenschaften ausschließen, z. B. Site-Besuchereigenschaften, sodass das Modell nicht verzerrt wird, was zu flachen Ergebnissen führt.
* Sie können Eigenschaften, von denen Sie nichts wissen oder denen Sie nicht vertrauen, aus einer Datenquelle entfernen, um die einflussreichen Eigenschaften besser zu verstehen.
* Sie können bestimmte Eigenschaften ausschließen, z. B. demografische Eigenschaften, um bei Ihren Compliance-Verpflichtungen zu helfen.

>[!IMPORTANT]
>
>Ein wichtiger Hinweis zum dritten Anwendungsfall. Wenn der Drittanbieter ein neues demografisches Merkmal zum Daten-Feed hinzufügt (*Sie das Modell erstellt haben* wird das Merkmal automatisch vom Modell erfasst. Sie können keine Eigenschaften aus der Modellierung ausschließen, nachdem Sie das Modell erstellt haben. Siehe [Wichtige Aspekte und Einschränkungen](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Seien Sie bei der Verwendung dieser Funktion vorsichtig und arbeiten Sie mit dem Datenanbieter zusammen, um sicherzustellen, dass Sie über Änderungen an der Feed-Struktur informiert sind.

![](assets/lam_exclude_traits.png)

## Verwenden von Eigenschaftenausschlüssen {#how-to-use}

Verwenden Sie den [Modell erstellen](../../features/algorithmic-models/create-model.md#build-model), um neue algorithmische Modelle zu erstellen.

1. Die [!UICONTROL Exclusions] wird ausgegraut, bis Sie eine oder mehrere Datenquellen für die Modellierung auswählen.
2. Nachdem Sie eine oder mehrere Datenquellen für die Modellierung ausgewählt haben, drücken Sie **[!UICONTROL Browse All Traits]**.
3. Im Fenster **[!UICONTROL Select Traits to Exclude]** werden alle Eigenschaften angezeigt, die mit den zuvor ausgewählten Datenquellen verknüpft sind. Wählen Sie die Eigenschaften aus, die Sie ausschließen möchten.
4. Sie können die Eigenschaften nach Eigenschaftstyp, Eigenschaftstyp ([Geräte-ID](../../reference/ids-in-aam.md) und [Geräteübergreifende ID](../../reference/ids-in-aam.md)) filtern oder die Eigenschaftsordner durchsuchen. Beachten Sie, dass in Eigenschaftsordnern nur die Eigenschaften angezeigt werden, die mit Ihren ausgewählten Datenquellen verknüpft sind.
5. Drücken Sie **[!UICONTROL Exclude Selected Traits]**.

![Merkmal-Ausschlüsse](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>Sie können ganze Ordner ausschließen, indem Sie die Eigenschaft des Ordners ausschließen, anstatt die Eigenschaften im Ordner einzeln auszuschließen. Beispiel: In einem Ordner mit 20 Eigenschaften müssten Sie nur die Ordnereigenschaft ausschließen, anstatt alle Eigenschaften einzeln auszuschließen.

Wenn Sie Video-Tutorials bevorzugen, sehen Sie sich unsere Videodemonstration zum Ausschluss von Eigenschaften an:

>[!VIDEO](https://video.tv.adobe.com/v/38133/?quality=12&captions=ger)

Sehen Sie sich außerdem das folgende Video an, um einen detaillierten Überblick über die Funktionsweise geräteübergreifender Metriken zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/36761/?quality=12&captions=ger)

## Wichtige Aspekte und Einschränkungen {#important-aspects-and-limitations}

Bitte beachten Sie die folgenden Aspekte und Einschränkungen im Zusammenhang mit [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ausgeschlossene Eigenschaften in der Modellzusammenfassungsansicht </p> </td>
   <td colname="col2"> <p>Die ausgeschlossenen Eigenschaften <i>werden nicht angezeigt</i> in der Ansicht Modellzusammenfassung. Die ausgeschlossenen Eigenschaften können nur im Workflow Modell bearbeiten<b><span class="uicontrol"> angezeigt </span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rollenbasierte Zugriffssteuerung (RBAC) </p> </td>
   <td colname="col2"> <p>Beachten Sie die folgenden Einschränkungen für Unternehmen, die <a href="../../features/administration/administration-overview.md#administration"> RBAC verwenden</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Wenn Sie keinen Zugriff haben, um eine Eigenschaft anzuzeigen, können <i>nicht</i> diese Eigenschaft auswählen, um aus dem Modell ausgeschlossen zu werden. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Wenn Sie keinen Zugriff haben, um eine Eigenschaft anzuzeigen, <i> Sie diese Eigenschaft </i> der Liste der ausgeschlossenen Eigenschaften anzeigen (nicht). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausgeschlossene Eigenschaften nach Modellspeicherung ändern </p> </td>
   <td colname="col2"> <p>Sie können die ausgeschlossenen Eigenschaften nicht ändern, nachdem Sie ein Modell erstellt und gespeichert haben. Wenn Sie die Ergebnisse anpassen möchten, können Sie das Modell klonen und die ausgeschlossenen Eigenschaften ändern. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximale Anzahl an Eigenschaften, die ausgeschlossen werden können </p> </td>
   <td colname="col2"> <p>Die maximale Anzahl von Eigenschaften, die Sie aus einem Modell ausschließen können, beträgt 500. Verwenden Sie Ordnereigenschaften, um Ihre Ausschlüsse zu maximieren. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Baseline-Eigenschaft ausschließen </p> </td>
   <td colname="col2"> <p>Das Grundlinien-Merkmal ist standardmäßig ausgeschlossen, wird also beim Erstellen des Modells nicht in der Liste <b><span class="uicontrol"></span></b>Ausschlüsse“ angezeigt. </p> </td>
  </tr>
 </tbody>
</table>

Sehen Sie sich das folgende Video an, um zu erfahren, wie und warum Sie bestimmte Eigenschaften von einer [!UICONTROL Look-Alike Model] ausschließen sollten.

>[!VIDEO](https://video.tv.adobe.com/v/38133?captions=ger)

## Verwandte Links

* [Über algorithmische Eigenschaften](/help/using/features/algorithmic-models/understanding-models.md)
* [Eigenschaftenausschluss - Tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)

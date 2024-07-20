---
description: Der Eigenschaftenausschluss bietet zusätzliche Steuerelemente in Ihrem Modellierungs-Workflow, mit denen Sie die erforderlichen Schutzleisten zum Modell hinzufügen können, basierend auf Ihrem Domain-Know-how und Ihren gesetzlichen Anforderungen. Verwenden Sie die Option Ausschlüsse , um festzulegen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.
seo-description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-title: Algorithmic Models  Trait Exclusion
title: Algorithmische Modelle - Eigenschaftsausschluss
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# Look-alike-Modellierung: Eigenschaftsausschluss {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] bietet zusätzliche Steuerelemente in Ihrem Modellierungs-Workflow, mit denen Sie die erforderlichen Schutzleisten zum Modell hinzufügen können, basierend auf Ihrem Domain-Know-how und Ihren gesetzlichen Anforderungen. Verwenden Sie die Option [!UICONTROL Exclusions] , um festzulegen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.

## Nutzungsszenarios {#use-cases}

Im Folgenden finden Sie einige Anwendungsfälle, die Sie mit [!UICONTROL Trait Exclusion] adressieren können:

* Mit [!UICONTROL Trait Exclusion] können Sie bestimmte Sammeleigenschaften ausschließen, wie z. B. Site-Besuchereigenschaften, sodass Sie das Modell nicht beeinflussen, was zu flachen Ergebnissen führt.
* Sie können Eigenschaften entfernen, von denen Sie nicht wissen oder denen Sie nicht vertrauen, aus einer Datenquelle, um die einflussreichen Eigenschaften besser zu verstehen.
* Sie können bestimmte Eigenschaften, z. B. demografische Eigenschaften, ausschließen, um bei allen Compliance-Verpflichtungen zu helfen, die Sie möglicherweise haben.

>[!IMPORTANT]
>
>Ein wichtiger Hinweis zum dritten Anwendungsfall. Wenn der Drittanbieter für Daten eine neue demografische Eigenschaft zum Daten-Feed &quot;*hinzufügt, nachdem Sie das Modell &quot;*&quot;erstellt haben, wird die Eigenschaft automatisch vom Modell erfasst. Sie können Eigenschaften nach dem Erstellen des Modells nicht aus der Modellierung ausschließen. Siehe [Wichtige Aspekte und Einschränkungen](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Seien Sie bei der Verwendung dieser Funktion vorsichtig und arbeiten Sie mit dem Datenanbieter zusammen, um sicherzustellen, dass Sie über Änderungen an der Feed-Struktur informiert sind.

![](assets/lam_exclude_traits.png)

## Verwenden von Eigenschaftsausschlüssen {#how-to-use}

Verwenden Sie den Workflow [Modell erstellen](../../features/algorithmic-models/create-model.md#build-model) , um neue algorithmische Modelle zu erstellen.

1. Die Auswahl [!UICONTROL Exclusions] ist grau ausgeblendet, bis Sie eine oder mehrere Datenquellen für die Modellierung auswählen.
2. Nachdem Sie eine oder mehrere Datenquellen für die Modellierung ausgewählt haben, drücken Sie **[!UICONTROL Browse All Traits]**.
3. Im Fenster **[!UICONTROL Select Traits to Exclude]** werden alle Eigenschaften angezeigt, die mit den zuvor ausgewählten Datenquellen verknüpft sind. Wählen Sie die Eigenschaften aus, die Sie ausschließen möchten.
4. Sie können die Eigenschaften nach Eigenschaftstyp, Eigenschaftspopulationstyp ([Geräte-ID](../../reference/ids-in-aam.md) und [Geräteübergreifende ID](../../reference/ids-in-aam.md)) filtern oder die Eigenschaftsordner durchsuchen. Beachten Sie, dass Eigenschaftsordner nur die Eigenschaften anzeigen, die mit Ihren ausgewählten Datenquellen verknüpft sind.
5. Drücken Sie &quot;**[!UICONTROL Exclude Selected Traits]**&quot;.

![Eigenschaftsausschlüsse](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>Sie können ganze Ordner ausschließen, indem Sie die Ordnereigenschaft ausschließen, anstatt die Eigenschaften im Ordner einzeln auszuschließen. In einem Ordner mit 20 Eigenschaften müssten Sie beispielsweise nur die Ordnereigenschaft ausschließen, anstatt alle Eigenschaften einzeln auszuschließen.

Wenn Sie Video-Tutorials bevorzugen, sehen Sie sich unsere Videodemonstration für den Eigenschaftsausschluss an:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

Sehen Sie sich außerdem das folgende Video an, um sich ausführlich anzusehen, wie geräteübergreifende Metriken funktionieren.

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## Wichtige Aspekte und Einschränkungen {#important-aspects-and-limitations}

Beachten Sie die folgenden Aspekte und Einschränkungen im Zusammenhang mit [!UICONTROL Trait Exclusion]:

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
   <td colname="col2"> <p>Die ausgeschlossenen Eigenschaften <i>werden in der Modellzusammenfassungsansicht nicht</i> angezeigt. Sie können die ausgeschlossenen Eigenschaften nur im Workflow <b><span class="uicontrol"> Modell bearbeiten</span></b> sehen. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rollenbasierte Zugriffssteuerung (RBAC) </p> </td>
   <td colname="col2"> <p>Beachten Sie die folgenden Einschränkungen für Unternehmen, die <a href="../../features/administration/administration-overview.md#administration"> RBAC</a> verwenden: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Wenn Sie keinen Zugriff auf die Ansicht einer Eigenschaft haben, können Sie diese Eigenschaft <i>nicht</i> auswählen, um sie aus dem Modell auszuschließen. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Wenn Sie keinen Zugriff auf die Ansicht einer Eigenschaft haben, können Sie diese Eigenschaft <i>nicht</i> in der Liste der ausgeschlossenen Eigenschaften anzeigen. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausgeschlossene Eigenschaften nach dem Speichern des Modells ändern </p> </td>
   <td colname="col2"> <p>Sie können die ausgeschlossenen Eigenschaften nicht ändern, nachdem Sie ein Modell erstellt und gespeichert haben. Wenn Sie die Ergebnisse anpassen möchten, können Sie das Modell klonen und die ausgeschlossenen Eigenschaften ändern. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximale Anzahl von Eigenschaften, die Sie ausschließen können </p> </td>
   <td colname="col2"> <p>Die maximale Anzahl von Eigenschaften, die Sie aus einem Modell ausschließen können, beträgt 500. Verwenden Sie Ordnereigenschaften, um Ihre Ausschlüsse zu maximieren. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grundlinieneigenschaft ausschließen </p> </td>
   <td colname="col2"> <p>Die Grundlinie ist standardmäßig ausgeschlossen, sodass sie beim Erstellen des Modells nicht in der Liste <b><span class="uicontrol"> Ausschlüsse</span></b> angezeigt wird. </p> </td>
  </tr>
 </tbody>
</table>

Sehen Sie sich das folgende Video an, um zu erfahren, wie und warum bestimmte Eigenschaften von einer [!UICONTROL Look-Alike Model] ausgeschlossen werden.

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## Verwandte Links

* [Über algorithmische Eigenschaften](/help/using/features/algorithmic-models/understanding-models.md)
* [Eigenschaftenausschluss - Tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)

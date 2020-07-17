---
description: Der Eigenschaftsausschluss bietet zusätzliche Steuerelemente in Ihrem Modellarbeitsablauf, mit denen Sie die erforderlichen Schutzleisten zum Modell hinzufügen können, basierend auf Ihrer Domänenkompetenz und Ihren regulatorischen Anforderungen. Verwenden Sie die Option "Ausnahmen", um festzulegen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.
seo-description: Der Eigenschaftsausschluss bietet zusätzliche Steuerelemente in Ihrem Modellarbeitsablauf, mit denen Sie die erforderlichen Schutzleisten zum Modell hinzufügen können, basierend auf Ihrer Domänenkompetenz und Ihren regulatorischen Anforderungen. Verwenden Sie die Option "Ausnahmen", um festzulegen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.
seo-title: Algorithmischer Modelleigenschaftsausschluss
title: Algorithmischer Modelleigenschaftsausschluss
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 1%

---


# Look-alike-Modellierung: Eigenschaftsausschluss {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] bietet zusätzliche Steuerelemente in Ihrem Modellierungsarbeitsablauf, mit denen Sie die erforderlichen Schutzschienen zum Modell hinzufügen können, basierend auf Ihrer Domänenkompetenz und Ihren regulatorischen Anforderungen. Verwenden Sie die [!UICONTROL Exclusions] Option, um festzulegen, welche Eigenschaften beim Erstellen von Modellen aus einer oder mehreren Datenquellen ignoriert werden sollen.

## Nutzungsszenarios {#use-cases}

Im Folgenden finden Sie einige Anwendungsfälle, mit denen Sie sich befassen können [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] ermöglicht es Ihnen, bestimmte Auffangeigenschaften auszuschließen, wie z. B. Site-Besucher-Eigenschaften, sodass Sie das Modell nicht voreinstellen und somit zu reduzierten Ergebnissen führen.
* Sie können Eigenschaften, die Sie nicht kennen oder denen Sie nicht vertrauen, aus einer Datenquelle entfernen, um die einflussreichen Eigenschaften besser zu verstehen.
* Sie können bestimmte Eigenschaften, wie demografische Merkmale, ausschließen, um eventuell vorhandene Compliance-Verpflichtungen zu erfüllen.

>[!IMPORTANT]
>
>Ein wichtiger Hinweis zum dritten Verwendungsfall. Wenn der Drittanbieter für Daten eine neue demografische Eigenschaft zum Datenfeed hinzufügt, *nachdem Sie das Modell* erstellt haben, wird die Eigenschaft automatisch vom Modell übernommen. Sie können Eigenschaften nach dem Erstellen des Modells nicht von der Modellierung ausschließen. Siehe [Wichtige Aspekte und Einschränkungen](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Gehen Sie bei Verwendung dieser Funktion vorsichtig vor und arbeiten Sie mit dem Datenanbieter zusammen, um sicherzustellen, dass Sie über Änderungen an der Feed-Struktur informiert werden.

![](assets/lam_exclude_traits.png)

## So verwenden Sie Eigenschaftsausschlüsse {#how-to-use}

Verwenden Sie den Arbeitsablauf zum [Erstellen eines Modells](../../features/algorithmic-models/create-model.md#build-model) , um neue algorithmische Modelle zu erstellen.

1. Die [!UICONTROL Exclusions] Auswahl wird so lange ausgegraut, bis Sie eine oder mehrere Datenquellen für die Modellierung auswählen.
2. Nach Auswahl einer oder mehrerer Datenquellen zur Modellierung drücken Sie **[!UICONTROL Browse All Traits]** die Eingabetaste.
3. Im **[!UICONTROL Select Traits to Exclude]** Fenster werden alle Eigenschaften angezeigt, die mit den zuvor ausgewählten Datenquellen verknüpft sind. Wählen Sie die Eigenschaften aus, die Sie ausschließen möchten.
4. Sie können die Eigenschaften nach Eigenschaftstyp, Eigenschaftspopulationstyp ([Geräte-ID](../../reference/ids-in-aam.md) und [geräteübergreifende ID](../../reference/ids-in-aam.md)) filtern oder die Eigenschaftsordner durchsuchen. Beachten Sie, dass Eigenschaftsordner nur die Eigenschaften anzeigen, die mit den ausgewählten Datenquellen verknüpft sind.
5. Drücken Sie **[!UICONTROL Exclude Selected Traits]**.

![Eigenschaftenausschlüsse](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>Sie können ganze Ordner ausschließen, indem Sie die Ordnereigenschaft ausschließen, anstatt die Eigenschaften im Ordner einzeln auszuschließen. In einem Ordner mit 20 Eigenschaften müssen Sie beispielsweise nur die Ordnereigenschaft ausschließen, anstatt alle Eigenschaften einzeln auszuschließen.

Wenn Sie Videolehrgänge bevorzugen, sehen Sie sich unsere Videodemonstration für den Eigenschaftsausschluss an:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

Sehen Sie sich außerdem das unten stehende Video an, um sich ausführlich anzusehen, wie geräteübergreifende Metriken funktionieren.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

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
   <td colname="col1"> <p>Ausgeschlossene Eigenschaften in Ansicht der Modellzusammenfassung </p> </td>
   <td colname="col2"> <p>Die ausgeschlossenen Eigenschaften werden <i>nicht in der Ansicht "Modellzusammenfassung"angezeigt</i> . Sie können die ausgeschlossenen Eigenschaften nur im Arbeitsablauf <b><span class="uicontrol"> Modell</span></b> bearbeiten anzeigen. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rollenbasierte Zugriffskontrollen (RBAC) </p> </td>
   <td colname="col2"> <p>Beachten Sie die folgenden Einschränkungen für Firmen, die <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>verwenden: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Wenn Sie keinen Zugriff auf die Ansicht einer Eigenschaft haben, <i>können Sie diese Eigenschaft nicht</i> auswählen, um sie aus dem Modell auszuschließen. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Wenn Sie keinen Zugriff auf die Ansicht einer Eigenschaft haben, <i>können</i> Sie diese Eigenschaft nicht in der Liste der ausgeschlossenen Eigenschaften Ansicht werden. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausgeschlossene Eigenschaften nach dem Speichern des Modells ändern </p> </td>
   <td colname="col2"> <p>Sie können die ausgeschlossenen Eigenschaften nicht mehr ändern, nachdem Sie ein Modell erstellt und gespeichert haben. Wenn Sie die Ergebnisse optimieren möchten, können Sie das Modell klonen und die ausgeschlossenen Eigenschaften ändern. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximale Anzahl von Eigenschaften, die Sie ausschließen können </p> </td>
   <td colname="col2"> <p>Die maximale Anzahl von Eigenschaften, die Sie von einem Modell ausschließen können, ist 500. Verwenden Sie Ordnereigenschaften, um Ihre Ausnahmen zu maximieren. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grundlinieneigenschaft ausschließen </p> </td>
   <td colname="col2"> <p>Die Grundlinieneigenschaft wird standardmäßig ausgeschlossen, sodass sie beim Erstellen des Modells nicht in der Liste <b><span class="uicontrol"> Ausnahmen</span></b> angezeigt wird. </p> </td>
  </tr>
 </tbody>
</table>

Sehen Sie sich das unten stehende Video an, um zu erfahren, wie und warum Sie bestimmte Eigenschaften von einem [!UICONTROL Look-Alike Model]ausschließen.

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## Verwandte Links

* [Algorithmische Eigenschaften](/help/using/features/algorithmic-models/understanding-models.md)
* [Eigenschaftsausschluss - Tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
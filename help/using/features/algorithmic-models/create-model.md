---
description: Beschreibt die erforderlichen und optionalen Schritte zum Erstellen eines algorithmischen Modells in Model Builder.
keywords: Funktionsweise von Algo
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Create an Algorithmic Model
solution: Audience Manager
title: Erstellen eines algorithmischen Modells
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
exl-id: 8b7c4f57-f2c8-46f1-8924-5513fd6ede04
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# Lookalike-Modell erstellen {#create-an-algorithmic-model}

Beschreibt die erforderlichen und optionalen Schritte zum Erstellen eines [!UICONTROL Look-Alike Model].

## Modellersteller-Abschnitt

[!UICONTROL Model Builder] besteht aus den Abschnitten [!UICONTROL Basic Information] und [!UICONTROL Configuration] . Um ein Modell zu erstellen, füllen Sie die erforderlichen Felder in diesen beiden Abschnitten aus. Speichern Sie Ihr Modell, um den Algorithmus zu starten. [!DNL Audience Manager] sendet Ihnen nach Abschluss des ersten Datendurchgangs eine automatisierte Benachrichtigung. Nachdem Sie die E-Mail erhalten haben, können Sie zu [Trait Builder](../../features/traits/about-trait-builder.md) wechseln und algorithmische Eigenschaften erstellen.

>[!NOTE]
>
>* Der Modellierungsprozess wird nur einmal ausgeführt, wenn Sie ein Modell erstellen und damit keine Eigenschaften erstellen.
>* Erstellen Sie Modelle aus Datenquellen, die eine aussagekräftige Menge an Informationen enthalten. Modelle mit unzureichenden Daten werden zwar ausgeführt, aber keine Ergebnisse zurückgegeben.
>* *Erstellen Sie* Modelle mit anderen algorithmischen Eigenschaften oder Segmenten.
>* Die automatisierte E-Mail-Benachrichtigung wird nur einmal gesendet (nach der ersten Datenausführung).

## Modell erstellen

Gehen Sie wie folgt vor, um eine [!UICONTROL Look-Alike Model] zu erstellen:

1. Wechseln Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** und klicken Sie im Abschnitt [!UICONTROL Look-Alike Modeling] auf **[!UICONTROL Add New]** .
   ![Look-alike-add](assets/look-alike-add.png)
1. Im Abschnitt [Grundlegende Informationen](../../features/algorithmic-models/create-model.md#basic-information)
   * Benennen Sie das Modell.
   * *(Optional)* Geben Sie eine kurze Beschreibung des Modells ein.
   * Setzen Sie den Status für das Modell auf **[!UICONTROL Active]** oder **[!UICONTROL Inactive]**. Inaktive Modelle werden nicht ausgeführt und erzeugen keine Daten.

     ![Look-alike-basic](assets/look-alike-basic.png)
1. Im Abschnitt [Konfiguration](../../features/algorithmic-models/create-model.md#configuration):
   * Klicken Sie auf **[!UICONTROL Browse All Traits]** oder **[!UICONTROL Browse All Segments]** , um eine Eigenschaft oder ein Segment auszuwählen, mit der bzw. dem Sie ein Modell erstellen möchten. Suche nach Eigenschaften nach Name, ID, Beschreibung oder Datenquelle. Klicken Sie auf einen Ordner, während Sie suchen, um die Ergebnisse auf diesen Ordner und dessen Unterordner zu beschränken. Sie können Eigenschaften auch nach Eigenschaftstyp ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] und [!UICONTROL Algorithmic]) oder Populationstyp ([Geräte-ID](../../reference/ids-in-aam.md) und [Geräteübergreifende ID](../../reference/ids-in-aam.md)) filtern.

     ![browse-traits](assets/browse-traits.png)
   * Wählen Sie einen Lookback-Zeitraum von 30, 60 oder 90 Tagen aus. Dadurch wird ein Zeitbereich für das Modell festgelegt.
   * Der [!UICONTROL TraitWeight] ist standardmäßig ausgewählt.
   * Wählen Sie eine Datenquelle aus der Liste [!UICONTROL Available Data] aus.
   * Klicken Sie abschließend auf **[!UICONTROL Save]** .

     ![Look-alike-configuration](assets/look-alike-configuration.png)

Sehen Sie sich das folgende Video an, um einen detaillierten Überblick über die Funktionsweise geräteübergreifender Metriken zu erhalten.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Grundlegende Informationen für algorithmische Modelle {#basic-information}

<!-- r_model_basic.xml -->

[!UICONTROL Model Builder] können Sie mit den [!UICONTROL Basic Information] neue Modelle erstellen oder vorhandene bearbeiten. Um ein neues Modell zu erstellen, geben Sie einen Namen an und fahren Sie mit den [!UICONTROL Configuration] fort. Das Beschreibungsfeld ist optional.

| Feld | Beschreibung |
|---|---|
| **[!UICONTROL Name]** | Geben Sie Ihrem Modell einen kurzen, logischen Namen, der seine Funktion oder seinen Zweck beschreibt. Vermeiden Sie Abkürzungen, Sonderzeichen und Akzentzeichen. |
| **[!UICONTROL Description]** | Ein Feld für zusätzliche beschreibende Informationen zum Modell. |
| **[!UICONTROL Status]** | Aktiviert oder deaktiviert das Modell (standardmäßig aktiv). |

## Konfiguration {#configuration}

[!UICONTROL Model Builder] können Sie im Abschnitt [!UICONTROL Configuration] Eigenschaften oder Segmente zum Modell hinzufügen. Wählen Sie in diesem Abschnitt ein Grundlinien-Merkmal oder -Segment, einen Lookback-Zeitraum und Daten aus Ihren Erst- und Drittanbieter-Datenquellen aus.

<!-- r_model_configuration.xml -->

### Voraussetzungen

Füllen Sie zuerst die erforderlichen Felder im Abschnitt [!UICONTROL Basic Information] aus.

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Grundlinie oder Segment auswählen (1)</b> </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf die Schaltfläche Eigenschaft oder Segment , um eine Liste aller Eigenschaften oder Segmente anzuzeigen. Das ausgewählte Segment oder die ausgewählte Eigenschaft wird zur Grundlinie, die die Systemalgorithmen für die Modellierung verwenden. </p> <p> <p><b>Hinweis</b>: Wählen Sie als Grundlinie eine integrierte Eigenschaft, eine regelbasierte Eigenschaft oder ein Segment aus. Andernfalls werden Ihre Modelle nicht ausgeführt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Lookback-Zeitraum auswählen (2)</b> </p> </td> 
   <td colname="col2"> <p>Legt einen Zeitbereich für das Modell fest. Basierend auf Ihrer Auswahl umfasst und bewertet der Algorithmus Daten aus den vorherigen 30, 60 oder 90 Tagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Algorithmus auswählen (3)</b> </p> </td> 
   <td colname="col2"> <p>Derzeit arbeitet Model Builder nur mit unserem proprietären Algorithmus <span class="keyword"> Trait Weight </span>. <span class="keyword"> Audience Manager </span> kann in nachfolgenden Versionen weitere algorithmische Funktionen hinzufügen. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Modelldaten aus Data Source auswählen (4)</b> </p> </td> 
   <td colname="col2"> <p>Hier können Sie die Datenquellen von Erst- und Drittanbietern auswählen, die Sie im Modell verwenden möchten. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ausnahmen (5)</b> </p> </td> 
   <td colname="col2"> <p>Sie können Eigenschaften aus den Datenquellen ausschließen, die Sie für die Modellierung ausgewählt haben. Verwenden Sie die Liste <span class="wintitle"> Ausschlüsse </span> lesen Sie <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorithmische Modelle: Ausschluss von Eigenschaften</a> um mehr zu erfahren. </p> </td>
  </tr> 
 </tbody>
</table>

Sehen Sie sich das folgende Video an, um zu erfahren, wie Sie ein Look-alike-Modell für Erstanbieter erstellen, sodass Sie mehr eigene Besucher finden können, die wie Ihre Konverter aussehen.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [Grundlegendes zur Eigenschaftsgewichtung](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

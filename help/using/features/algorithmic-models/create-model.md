---
description: Beschreibt die erforderlichen und optionalen Schritte, mit denen Sie ein algorithmisches Modell in Model Builder erstellen können.
keywords: algo how works
seo-description: Beschreibt die erforderlichen und optionalen Schritte, mit denen Sie ein algorithmisches Modell in Model Builder erstellen können.
seo-title: Algorithmisches Modell erstellen
solution: Audience Manager
title: Algorithmisches Modell erstellen
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: bff108115e7ebd4375d81c1c32ec9bb7d1a207c1
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 1%

---


# Erstellen eines Look-alike-Modells {#create-an-algorithmic-model}

Beschreibt die erforderlichen und optionalen Schritte, mit denen Sie eine [!UICONTROL Look-Alike Model]erstellen können.

## Bereich &quot;Modellaufbau&quot;

[!UICONTROL Model Builder] besteht aus den [!UICONTROL Basic Information] und [!UICONTROL Configuration] Abschnitten. Um ein Modell zu erstellen, füllen Sie die erforderlichen Felder in diesen beiden Abschnitten aus. Speichern Sie Ihr Modell, um den Algorithmus Beginn. [!DNL Audience Manager] sendet Ihnen eine automatisierte Benachrichtigung nach Abschluss der ersten Datenausführung. Nachdem Sie die E-Mail erhalten haben, können Sie zum [Eigenschaften-Aufbau](../../features/traits/about-trait-builder.md) wechseln und algorithmische Eigenschaften erstellen.

>[!NOTE]
>
>* Der Modellierungsprozess wird nur einmal ausgeführt, wenn Sie ein Modell erstellen und keine Eigenschaften mit diesem erstellen.
>* Erstellen Sie Modelle aus Datenquellen, die eine aussagekräftige Menge an Informationen enthalten. Modelle mit unzureichenden Daten werden ausgeführt, aber keine Ergebnisse zurückgegeben.
>* *Erstellen Sie keine* Modelle mit anderen algorithmischen Eigenschaften oder Segmenten.
>* Die automatisierte E-Mail-Benachrichtigung wird nur einmal gesendet (nach der ersten Datenausführung).


## Modell erstellen

Gehen Sie wie folgt vor, um eine [!UICONTROL Look-Alike Model]zu erstellen:

1. Gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** und klicken Sie **[!UICONTROL Add New]** in den [!UICONTROL Look-Alike Modeling] Abschnitt.
   ![look-alike-add](assets/look-alike-add.png)
1. Im Abschnitt &quot; [Grundlegende Informationen](../../features/algorithmic-models/create-model.md#basic-information) &quot;
   * Benennen Sie das Modell.
   * *(Optional)* Geben Sie eine kurze Beschreibung des Modells ein.
   * Legen Sie den Status für das Modell auf **[!UICONTROL Active]** oder **[!UICONTROL Inactive]**fest. Inaktive Modelle werden nicht ausgeführt und erzeugen keine Daten.
      ![look-alike-basic](assets/look-alike-basic.png)
1. Im Abschnitt [Konfiguration](../../features/algorithmic-models/create-model.md#configuration) :
   * Klicken Sie auf **[!UICONTROL Browse All Traits]** oder **[!UICONTROL Browse All Segments]** , um eine Eigenschaft oder ein Segment auszuwählen, für die Sie ein Modell erstellen möchten. Suchen Sie nach Eigenschaften nach Name, ID, Beschreibung oder Datenquelle. Klicken Sie auf einen Ordner, während Sie suchen, um die Ergebnisse auf diesen Ordner und dessen Unterordner zu beschränken. Sie können Eigenschaften auch nach Eigenschaftstyp ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]und [!UICONTROL Algorithmic]) oder Populationstyp ([Geräte-ID](../../reference/ids-in-aam.md) und [geräteübergreifende ID](../../reference/ids-in-aam.md)) filtern.
      ![browse-Eigenschaften](assets/browse-traits.png)
   * Wählen Sie einen 30-, 60- oder 90-tägigen Rückblickzeitraum. Hiermit wird ein Zeitraum für das Modell festgelegt.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Wählen Sie eine Datenquelle aus der [!UICONTROL Available Data] Liste.
   * Klicken Sie **[!UICONTROL Save]** nach Abschluss des Vorgangs auf .
      ![look-alike-configuration](assets/look-alike-configuration.png)

Sehen Sie sich das unten stehende Video an, um einen detaillierten Überblick über die Funktionsweise geräteübergreifender Metriken zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/33445/)

## Grundlegende Informationen für algorithmische Modelle {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder]den [!UICONTROL Basic Information] Einstellungen können Sie neue oder vorhandene Modelle erstellen. Um ein neues Modell zu erstellen, geben Sie einen Namen ein und wechseln Sie zu den [!UICONTROL Configuration] Einstellungen. Das Beschreibungsfeld ist optional.

| Feld | Beschreibung |
|---|---|
| **[!UICONTROL Name]** | Geben Sie dem Modell einen kurzen logischen Namen, der seine Funktion oder seinen Zweck beschreibt. Vermeiden Sie Abkürzungen, Sonderzeichen und Akzentzeichen. |
| **[!UICONTROL Description]** | Ein Feld für weitere beschreibende Informationen zum Modell. |
| **[!UICONTROL Status]** | Aktiviert oder deaktiviert das Modell (standardmäßig aktiv). |

## Konfiguration {#configuration}

In [!UICONTROL Model Builder]diesem Abschnitt können Sie dem Modell Eigenschaften oder Segmente [!UICONTROL Configuration] hinzufügen. Wählen Sie in diesem Abschnitt eine Basiseigenschaft oder ein Segment, einen Rückblickzeitraum und Daten aus Ihren Erstanbieter- und Drittanbieter-Datenquellen aus.

<!-- r_model_configuration.xml -->

### Voraussetzungen

Füllen Sie zuerst die erforderlichen Felder im [!UICONTROL Basic Information] Abschnitt aus.

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
   <td colname="col1"> <p><b>Grundlegende Eigenschaft oder Segment auswählen (1)</b> </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf die Schaltfläche Eigenschaften oder Segmente, um eine Liste aller Eigenschaften oder Segmente anzuzeigen. Ihr ausgewähltes Segment oder Ihre Eigenschaft wird zur Grundlage, die die Systemalgorithmen für die Modellierung verwenden. </p> <p> <p><b>Hinweis</b>:  Wählen Sie eine integrierte Eigenschaft, eine regelbasierte Eigenschaft oder ein Segment als Grundlinie aus. Andernfalls werden Ihre Modelle nicht ausgeführt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Rückblickzeit auswählen (2)</b> </p> </td> 
   <td colname="col2"> <p>Legt einen Zeitraum für das Modell fest. Je nach Ihrer Auswahl enthält und bewertet der Algorithmus Daten aus den letzten 30, 60 oder 90 Tagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Algorithmus auswählen (3)</b> </p> </td> 
   <td colname="col2"> <p>Der Modellaufbau funktioniert derzeit nur mit unserem proprietären <span class="keyword"> Eigenschaften-Gewichtung</span> -Algorithmus. <span class="keyword"> Audience Manager</span> kann in späteren Versionen weitere algorithmische Funktionen hinzufügen. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Modelldaten aus Datenquelle auswählen (4)</b> </p> </td> 
   <td colname="col2"> <p>Ermöglicht die Auswahl der ersten und dritten Datenquellen, die Sie im Modell verwenden möchten. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ausnahmen (5)</b> </p> </td> 
   <td colname="col2"> <p>Sie können Eigenschaften aus den Datenquellen ausschließen, die Sie für die Modellierung ausgewählt haben. Verwenden Sie die <span class="wintitle"> Liste "Ausnahmen</span> "und lesen Sie <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorithmische Modelle: Eigenschaftsausschluss</a> , um mehr zu erfahren. </p> </td>
  </tr> 
 </tbody>
</table>

Sehen Sie sich das folgende Video an, um zu erfahren, wie Sie ein Erstanbieter-Look-like-Modell erstellen, damit Sie mehr eigene Besucher finden können, die wie Ihre Konverter aussehen.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [Verstehen von EigenschaftenWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)


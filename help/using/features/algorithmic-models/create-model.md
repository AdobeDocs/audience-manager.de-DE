---
description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
keywords: algo how works
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Create an Algorithmic Model
solution: Audience Manager
title: Algorithmisches Modell erstellen
topic: DIL API
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Algorithmisches Modell erstellen {#create-an-algorithmic-model}

Beschreibt die erforderlichen und optionalen Schritte zum Erstellen eines algorithmischen Modells in [!UICONTROL Model Builder].

## Modell erstellen {#build-model}

<!-- t_model_build.xml -->

### Bereich "Modellaufbau"

[!UICONTROL Model Builder] besteht aus den [!UICONTROL Basic Information] und [!UICONTROL Configuration] Abschnitten. Um ein Modell zu erstellen, füllen Sie die erforderlichen Felder in diesen beiden Abschnitten aus. Speichern Sie Ihr Modell, um den Algorithmus zu starten. [!DNL Audience Manager] sends you an automated notification after the first data run completes. Nachdem Sie die E-Mail erhalten haben, können Sie zum [Eigenschaften-Aufbau](../../features/traits/about-trait-builder.md) wechseln und algorithmische Eigenschaften erstellen.

>[!NOTE]
>
>* Der Modellprozess wird nur einmal ausgeführt, wenn Sie ein Modell erstellen und keine Eigenschaften mit diesem erstellen.
>* Erstellen Sie Modelle aus Datenquellen, die eine aussagekräftige Menge an Informationen enthalten. Modelle mit unzureichenden Daten werden ausgeführt, aber keine Ergebnisse zurückgegeben.
>* *Erstellen Sie keine* Modelle mit anderen algorithmischen Eigenschaften oder Segmenten.
>* Die automatisierte E-Mail-Benachrichtigung wird nur einmal gesendet (nach der ersten Datenausführung).


### Modell erstellen

Gehen Sie zum Erstellen eines Modells zum [!UICONTROL Models] Abschnitt und klicken Sie auf **[!UICONTROL Add New]** und befolgen Sie die folgenden Schritte:

1. Im Abschnitt [Grundlegende Informationen](../../features/algorithmic-models/create-model.md#basic-information)
   * Benennen Sie das Modell.
   * *(Optional)* Geben Sie eine kurze Beschreibung des Modells ein.
   * Legen Sie den Status für das Modell auf **[!UICONTROL Active]** oder **[!UICONTROL Inactive]** fest. Inaktive Modelle werden nicht ausgeführt und erzeugen keine Daten.
1. Im Abschnitt [Konfiguration](../../features/algorithmic-models/create-model.md#configuration) :
   * Klicken Sie auf **[!UICONTROL Browse All Traits]** oder **[!UICONTROL Browse All Segments]** , um eine Eigenschaft oder ein Segment auszuwählen, für die Sie ein Modell erstellen möchten.   Wählen Sie eine integrierte Eigenschaft, eine regelbasierte Eigenschaft oder ein Segment als Grundlinie aus. Andernfalls werden Ihre Modelle nicht ausgeführt.
   * Wählen Sie einen 30-, 60- oder 90-tägigen Rückblickzeitraum. Hiermit wird ein Zeitraum für das Modell festgelegt.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Select a data source from the  list.[!UICONTROL Available Data]
   * Click **[!UICONTROL Save]** when done.

## Grundlegende Informationen für algorithmische Modelle {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder]den [!UICONTROL Basic Information] Einstellungen können Sie neue oder vorhandene Modelle erstellen. Um ein neues Modell zu erstellen, geben Sie einen Namen ein und wechseln Sie zu den [!UICONTROL Configuration] Einstellungen. The description field is optional.

| Feld | Beschreibung |
|---|---|
| **[!UICONTROL Name]** | Give your model a short, logical name that describes its function or purpose. Avoid abbreviations, special characters, and accent marks. |
| **[!UICONTROL Description]** | A field for additional descriptive information about the model. |
| **[!UICONTROL Status]** | Activates or deactivates the model (active by default). |

## Konfiguration {#configuration}

In , the  section lets you add traits or segments to the model. [!UICONTROL Model Builder][!UICONTROL Configuration] In this section, select a baseline trait or segment, a look-back period, and data from your first and third-party data sources.

<!-- r_model_configuration.xml -->

### Voraussetzungen

Complete the required fields in the  section first.[!UICONTROL Basic Information]

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
   <td colname="col1"> <p><b>Select a Baseline Trait or Segment (1)</b> </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf die Schaltfläche Eigenschaften oder Segmente, um eine Liste aller Eigenschaften oder Segmente anzuzeigen. Ihr ausgewähltes Segment oder Ihre Eigenschaft wird zur Grundlage, die die Systemalgorithmen für die Modellierung verwenden. </p> <p> <p><b>Hinweis</b>:Wählen Sie eine integrierte Eigenschaft, eine regelbasierte Eigenschaft oder ein Segment als Grundlinie aus. Andernfalls werden Ihre Modelle nicht ausgeführt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Rückblickzeit auswählen (2)</b> </p> </td> 
   <td colname="col2"> <p>Legt einen Zeitraum für das Modell fest. Je nach Ihrer Auswahl enthält und bewertet der Algorithmus Daten aus den letzten 30, 60 oder 90 Tagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Algorithmus auswählen (3)</b> </p> </td> 
   <td colname="col2"> <p>Der Modellaufbau funktioniert derzeit nur mit unserem proprietären <span class="keyword"> Eigenschaftsgewichtsalgorithmus</span> . <span class="keyword"> Audience Manager</span> kann in späteren Versionen weitere algorithmische Funktionen hinzufügen. </p> </td>
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

>[!VIDEO](https://video.tv.adobe.com/v/23504/?captions=ger)

>[!MORE_LIKE_THIS]
>
>* [EigenschaftenGewicht verstehen](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)


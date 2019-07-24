---
description: Beschreibt die erforderlichen und optionalen Schritte, mit denen Sie ein algorithmische Modell in Modellaufbau erstellen können.
keywords: Funktionsweise
seo-description: Beschreibt die erforderlichen und optionalen Schritte, mit denen Sie ein algorithmische Modell in Modellaufbau erstellen können.
seo-title: Erstellen eines algorithmischen Modells
solution: Audience Manager
title: Erstellen eines algorithmischen Modells
topic: DIL-API
uuid: ccf 4 fc 4 e-cf 92-445 f-b 2 d 9-71 c 3 ca 624 e 26
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create an Algorithmic Model {#create-an-algorithmic-model}

Describes the required and optional steps that let you create an algorithmic model in [!UICONTROL Model Builder].

## Build a Model {#build-model}

<!-- t_model_build.xml -->

### Abschnitt "Modellaufbau «

[!UICONTROL Model Builder] besteht aus den Abschnitten [!UICONTROL Basic Information] und [!UICONTROL Configuration] Abschnitten. Um ein Modell zu erstellen, füllen Sie die erforderlichen Felder in diesen beiden Abschnitten aus. Speichern Sie das Modell, um den Algorithmus zu starten. [!DNL Audience Manager] sendet eine automatisierte Benachrichtigung, nachdem die ersten Daten abgeschlossen wurden. After you receive the email, you can go to [Trait Builder](../../features/traits/about-trait-builder.md) and create algorithmic traits.

>[!NOTE]
>
>* Der Modellierungsprozess wird nur einmal ausgeführt, wenn Sie ein Modell erstellen und keine Eigenschaften damit erstellen.
>* Erstellen Sie Modelle aus Datenquellen, die eine aussagekräftige Informationsmenge enthalten. Modelle mit nicht ausreichenden Daten werden ausgeführt, die Ergebnisse werden jedoch nicht zurückgegeben.
>* *Erstellen* Sie keine Modelle mit anderen algorithmischen Eigenschaften oder Segmenten.
>* Die automatisierte E-Mail-Benachrichtigung wird nur einmal gesendet (nach der ersten Ausführung).


### Modell erstellen

To build a model, go to the [!UICONTROL Models] section and click **[!UICONTROL Add New]** and follow the steps below:

1. In the [Basic Information](../../features/algorithmic-models/create-model.md#basic-information) section
   * Geben Sie dem Modell einen Namen.
   * *(Optional)* Geben Sie eine kurze Beschreibung des Modells ein.
   * Set the status for the model to **[!UICONTROL Active]** or **[!UICONTROL Inactive]**. Inaktive Modelle werden nicht ausgeführt und werden keine Daten generieren.
1. In the [Configuration](../../features/algorithmic-models/create-model.md#configuration) section:
   * Click **[!UICONTROL Browse All Traits]** or **[!UICONTROL Browse All Segments]** to select a trait or segment you want to model against. Wählen Sie eine persönliche Eigenschaft, eine regelbasierte Eigenschaft oder ein Segment als Grundlinie aus. Andernfalls werden Ihre Modelle nicht ausgeführt.
   * Wählen Sie einen Look-Back-Zeitraum von 30, 60 oder 90 Tagen. Dadurch wird ein Zeitbereich für das Modell festgelegt.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Select a data source from the [!UICONTROL Available Data] list.
   * Click **[!UICONTROL Save]** when done.

## Basic Information for Algorithmic Models {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], the [!UICONTROL Basic Information] settings let you create new or edit existing models. To create a new model, provide a name and move on to the [!UICONTROL Configuration] settings. Das Beschreibungsfeld ist optional.

| Feld | Beschreibung |
|---|---|
| **[!UICONTROL Name]** | Geben Sie Ihrem Modell einen kurzen, logischen Namen, der seine Funktion oder Ihren Zweck beschreibt. Vermeiden Sie Abkürzungen, Sonderzeichen und Akzentzeichen. |
| **[!UICONTROL Description]** | Ein Feld für weitere beschreibende Informationen über das Modell. |
| **[!UICONTROL Status]** | Aktiviert bzw. deaktiviert das Modell (standardmäßig aktiv). |

## Konfiguration {#configuration}

In [!UICONTROL Model Builder], the [!UICONTROL Configuration] section lets you add traits or segments to the model. Wählen Sie in diesem Abschnitt eine Grundlinie oder ein Segment, einen Look-Back-Zeitraum und Daten aus Ihren ersten und dritten Datenquellen aus.

<!-- r_model_configuration.xml -->

### Voraussetzungen

Complete the required fields in the [!UICONTROL Basic Information] section first.

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
   <td colname="col1"> <p><b>Auswählen einer Grundlinieneigenschaft oder eines Segments (1)</b> </p> </td> 
   <td colname="col2"> <p>Klicken Sie auf die Eigenschaften oder Segmentschaltfläche, um eine Liste aller Eigenschaften oder Segmente anzuzeigen. Ihr ausgewähltes Segment oder die ausgewählte Eigenschaft wird zur Ausgangslinie, die die Systemalgorithmen für das Modellieren verwenden. </p> <p> <p><b>Hinweis</b>: Wählen Sie eine persönliche Eigenschaft, eine regelbasierte Eigenschaft oder ein Segment als Grundlinie aus. Andernfalls werden Ihre Modelle nicht ausgeführt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Look-Back-Punkt auswählen (2)</b> </p> </td> 
   <td colname="col2"> <p>Legt einen Zeitbereich für das Modell fest. Basierend auf Ihrer Auswahl enthält der Algorithmus Daten aus den letzten 30, 60 oder 90 Tagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Algorithmus auswählen (3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary <span class="keyword"> Trait Weight</span> algorithm only. <span class="keyword"> Audience Manager</span> kann in nachfolgenden Versionen weitere algorithmische Funktionen hinzufügen. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Modelldaten aus Datenquelle auswählen (4)</b> </p> </td> 
   <td colname="col2"> <p>Sie können die ersten und die Drittanbieterdatenquellen auswählen, die Sie im Modell verwenden möchten. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ausnahmen (5)</b> </p> </td> 
   <td colname="col2"> <p>Sie können Eigenschaften aus den Datenquellen ausschließen, die Sie für das Modellieren ausgewählt haben. Use the <span class="wintitle"> Exclusions</span> list and read <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorithmic Models: Trait Exclusion</a> to learn more. </p> </td>
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Grundlegendes zu traitweight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)


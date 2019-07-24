---
description: Beschreibt die Schritte und Funktionen, die für den algorithmischen Eigenschaftserstellungsprozess eindeutig sind.
seo-description: Beschreibt die Schritte und Funktionen, die für den algorithmischen Eigenschaftserstellungsprozess eindeutig sind.
seo-title: Erstellen von algorithmischen Eigenschaften
solution: Audience Manager
title: Erstellen von algorithmischen Eigenschaften
uuid: 50 c 2 d 2 d 1-f 412-479 b-bb 70-4 f 139429 c 388
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Algorithmic Traits {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

To create an algorithmic trait, go to [!UICONTROL Traits] and follow the steps below:

1. Click **[!UICONTROL Create New Trait]** and select **[!UICONTROL Algorithmic]** from the drop down menu.
1. In the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section
   * Benennen Sie die Eigenschaft.
   * Wählen Sie eine Datenquelle aus.
   * Wählen Sie einen Speicherordner.
1. Expand the [!UICONTROL Configuration] pane and click **[!UICONTROL Browse All Models]**.
Dadurch wird ein neues Fenster geöffnet, mit dem Sie das Modell auswählen können, das Sie mit der Eigenschaft verwenden möchten.
1. Select a model and click **[!UICONTROL Add Selected Model to Trait]**.
Durch das Hinzufügen des Modells werden die Einstellungen für Reichweite und Genauigkeit bereitgestellt.
1. Wählen Sie die Reichweite oder Genauigkeit als Ziel aus und wählen Sie einen Wert aus den jeweiligen Dropdown-Menüs. Click **[!UICONTROL Save]** when done.

>[!MORE_ LIKE_ THIS]
>
>* [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md)


## Configuration Settings for Algorithmic Traits {#configure-settings}

In [!UICONTROL Trait Builder], the [!UICONTROL Configuration] section lets you associate an algorithmic model to a trait. Um den algorithmischen Eigenschaftserstellungsprozess abzuschließen, wählen Sie ein Modell aus und wählen Sie eine Ziel- oder Genauigkeit.

### Voraussetzungen

<!-- r_algo_trait_config_section.xml -->

* [Erstellen Sie ein algorithmische Modell](../../features/algorithmic-models/create-model.md#build-model).
* Warten Sie auf die Benachrichtigungs-E-Mail, mit der Sie wissen können, dass die Modelldaten abgeschlossen sind.
* Complete the required fields in the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section.

### Konfigurationsfelder und -einstellungen

| Oberflächenelement | Erklärung |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Click the **[!UICONTROL Update]** button to open the models window. Wählen Sie im Fenster das algorithmische Modell aus, das Sie zum Erstellen der Eigenschaft verwenden möchten. |
| **[!UICONTROL Select Goal Accuracy]** | Wählen Sie diese Option, um eine Eigenschaft basierend auf der Genauigkeit zu erstellen. Die Genauigkeit ist ein ausgewerteter Wert, der angibt, wie nahe sich potenzielle Benutzer auf Ihrer Grundlinie befinden. Die Genauigkeit der Genauigkeit liegt zwischen 0 (am wenigsten genau) und 1 (am genauesten). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | In diesem Abschnitt werden bis zu 21 Zeilen numerischer Daten angezeigt, die die Genauigkeit und Reichweitewerte für Ihr Modell anzeigen. |
| **[!UICONTROL Reach and Accuracy Slider]** | Im unteren Bereich des Diagramms können Sie mit dem Schieberegler einen numerischen Wert für Ihre Erreichbaren Ziele oder Genauigkeit festlegen. Sie können den Schieberegler festlegen und dann die Ziel- oder Genauigkeit-Schaltfläche auswählen, um eine Eigenschaft zu erstellen. |

>[!MORE_ LIKE_ THIS]
>
>* [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md)
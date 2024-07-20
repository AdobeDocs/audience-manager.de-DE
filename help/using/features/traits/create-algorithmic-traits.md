---
description: Beschreibt die Einrichtung von Schritten und Funktionen, die für die algorithmische Erstellung von Eigenschaften spezifisch sind.
seo-description: Describes set up steps and features unique to the algorithmic trait creation process.
seo-title: Create Algorithmic Traits
solution: Audience Manager
title: Erstellen algorithmischer Eigenschaften
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# Erstellen algorithmischer Eigenschaften {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Um eine algorithmische Eigenschaft zu erstellen, gehen Sie zu [!UICONTROL Traits] und führen Sie die folgenden Schritte aus:

1. Klicken Sie auf **[!UICONTROL Create New Trait]** und wählen Sie **[!UICONTROL Algorithmic]** aus dem Dropdown-Menü aus.
1. Im Abschnitt [Basisinformationen](../../features/traits/create-onboarded-rule-based-traits.md)
   * Benennen Sie die Eigenschaft.
   * Wählen Sie eine Datenquelle aus.
   * Wählen Sie einen Speicherordner aus.
1. Erweitern Sie den Bereich [!UICONTROL Configuration] und klicken Sie auf **[!UICONTROL Browse All Models]**.
Dadurch wird ein neues Fenster geöffnet, in dem Sie das Modell auswählen können, das Sie mit der Eigenschaft verwenden möchten.
1. Wählen Sie ein Modell aus und klicken Sie auf **[!UICONTROL Add Selected Model to Trait]**.
Durch Hinzufügen des Modells werden die Reichweiten- und Genauigkeitseinstellungen verfügbar gemacht.
1. Wählen Sie Reichweite oder Genauigkeit als Ziel aus und wählen Sie einen Wert aus den entsprechenden Dropdown-Menüs aus. Klicken Sie abschließend auf **[!UICONTROL Save]** .

## Konfigurationseinstellungen für algorithmische Eigenschaften {#configure-settings}

In [!UICONTROL Trait Builder] können Sie mit dem Abschnitt [!UICONTROL Configuration] ein algorithmisches Modell mit einer Eigenschaft verknüpfen. Um den Prozess der algorithmischen Eigenschaftserstellung abzuschließen, wählen Sie ein Modell aus und wählen Sie ein Reichweiten- oder Genauigkeitsziel.

### Voraussetzungen

<!-- r_algo_trait_config_section.xml -->

* [Erstellen Sie ein Look-alike-Modell](../../features/algorithmic-models/create-model.md).
* Warten Sie auf die Benachrichtigungs-E-Mail, die Ihnen mitteilt, dass die Ausführung der Modelldaten abgeschlossen ist.
* Füllen Sie die erforderlichen Felder im Abschnitt [Grundlegende Informationen](../../features/traits/create-onboarded-rule-based-traits.md) aus.

### Konfigurationsfelder und Einstellungen

| Schnittstellenelement | Erklärung |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Klicken Sie auf die Schaltfläche **[!UICONTROL Update]** , um das Modellfenster zu öffnen. Wählen Sie im Fenster das algorithmische Modell aus, das Sie zum Erstellen der Eigenschaft verwenden möchten. |
| **[!UICONTROL Select Goal Accuracy]** | Wählen Sie diese Option aus, um eine Eigenschaft basierend auf Genauigkeit zu erstellen. Die Genauigkeit ist ein Wert, der anzeigt, wie nah sich potenzielle Benutzer an Ihrer Grundlinie befinden. Die Genauigkeitsskala reicht von 0 (am wenigsten genau) bis 1 (am genauesten). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Rechts neben diesem Abschnitt finden Sie bis zu 21 Zeilen numerischer Daten, die die Genauigkeit und Reichweitenwerte für Ihr Modell anzeigen. |
| **[!UICONTROL Reach and Accuracy Slider]** | Am unteren Rand des Diagramms befindet sich der Regler, mit dem Sie einen numerischen Wert für Ihre Reichweiten- oder Genauigkeitsziele festlegen können. Sie können den Schieberegler festlegen und dann die Schaltfläche für die Reichweite oder Genauigkeit wählen, um eine Eigenschaft zu erstellen. |

>[!MORELIKETHIS]
>
>* [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md)

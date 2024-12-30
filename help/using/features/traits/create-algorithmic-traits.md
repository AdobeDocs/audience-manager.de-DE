---
description: Beschreibt die Einrichtungsschritte und -funktionen, die für den Prozess der Erstellung algorithmischer Eigenschaften einzigartig sind.
seo-description: Describes set up steps and features unique to the algorithmic trait creation process.
seo-title: Create Algorithmic Traits
solution: Audience Manager
title: Algorithmische Eigenschaften erstellen
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# Algorithmische Eigenschaften erstellen {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Um eine algorithmische Eigenschaft zu erstellen, gehen Sie zu [!UICONTROL Traits] und führen Sie die folgenden Schritte aus:

1. Klicken Sie auf **[!UICONTROL Create New Trait]** und wählen Sie **[!UICONTROL Algorithmic]** aus dem Dropdown-Menü aus.
1. Im Abschnitt [Grundlegende Informationen](../../features/traits/create-onboarded-rule-based-traits.md)
   * Benennen Sie die Eigenschaft.
   * Datenquelle auswählen.
   * Wählen Sie einen Speicherordner.
1. Erweitern Sie den [!UICONTROL Configuration] und klicken Sie auf **[!UICONTROL Browse All Models]**.
Dadurch wird ein neues Fenster geöffnet, in dem Sie das Modell auswählen können, das Sie mit der Eigenschaft verwenden möchten.
1. Wählen Sie ein Modell aus und klicken Sie auf **[!UICONTROL Add Selected Model to Trait]**.
Durch Hinzufügen des Modells werden die Reichweite und Genauigkeit von Einstellungen verfügbar gemacht.
1. Wählen Sie als Ziel Reichweite oder Genauigkeit und wählen Sie einen Wert aus den entsprechenden Dropdown-Menüs aus. Klicken Sie abschließend auf **[!UICONTROL Save]** .

## Konfigurationseinstellungen für Algorithmische Eigenschaften {#configure-settings}

[!UICONTROL Trait Builder] können Sie im Abschnitt [!UICONTROL Configuration] ein algorithmisches Modell mit einer Eigenschaft verknüpfen. Um den Prozess der Erstellung algorithmischer Eigenschaften abzuschließen, wählen Sie ein Modell aus und wählen Sie ein Ziel für die Reichweite oder Genauigkeit aus.

### Voraussetzungen

<!-- r_algo_trait_config_section.xml -->

* [Erstellen eines Lookalike-Modells](../../features/algorithmic-models/create-model.md).
* Warten Sie auf die Benachrichtigungs-E-Mail, die Ihnen mitteilt, dass die Ausführung der Modelldaten abgeschlossen ist.
* Füllen Sie die erforderlichen Felder im Abschnitt [Basisinformationen](../../features/traits/create-onboarded-rule-based-traits.md) aus.

### Konfigurationsfelder und Einstellungen

| Schnittstellenelement | Erklärung |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Klicken Sie auf die Schaltfläche **[!UICONTROL Update]** , um das Fenster Modelle zu öffnen. Wählen Sie im Fenster das algorithmische Modell aus, das Sie zum Erstellen der Eigenschaft verwenden möchten. |
| **[!UICONTROL Select Goal Accuracy]** | Wählen Sie diese Option, um eine auf Genauigkeit basierende Eigenschaft zu erstellen. Die Genauigkeit ist ein bewerteter Wert, der angibt, wie nah potenzielle Benutzende Ihrer Grundlinie sind. Die Genauigkeitsskala reicht von 0 (am wenigsten genau) bis 1 (am genauesten). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Dieser Abschnitt befindet sich rechts und zeigt bis zu 21 Zeilen mit numerischen Daten an, die die Genauigkeit und Reichweite für Ihr Modell anzeigen. |
| **[!UICONTROL Reach and Accuracy Slider]** | Der Schieberegler befindet sich am unteren Rand des Diagramms und ermöglicht es Ihnen, einen numerischen Wert für Ihre Reichweite oder Genauigkeitsziele festzulegen. Sie können den Schieberegler einstellen und dann die Zielschaltfläche „Reichweite“ oder „Genauigkeit“ wählen, um eine Eigenschaft zu erstellen. |

>[!MORELIKETHIS]
>
>* [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md)

---
description: Beschreibt die Einrichtung von Schritten und Funktionen, die für die Erstellung algorithmischer Eigenschaften spezifisch sind.
seo-description: Beschreibt die Einrichtung von Schritten und Funktionen, die für die Erstellung algorithmischer Eigenschaften spezifisch sind.
seo-title: Erstellen algorithmischer Eigenschaften
solution: Audience Manager
title: Erstellen algorithmischer Eigenschaften
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 5%

---


# Erstellen algorithmischer Eigenschaften {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Gehen Sie zum Erstellen eines algorithmischen Merkmals zu [!UICONTROL Traits] und befolgen Sie die folgenden Schritte:

1. Klicken Sie auf **[!UICONTROL Create New Trait]** und wählen Sie **[!UICONTROL Algorithmic]** aus dem Dropdown-Menü.
1. Im Abschnitt [Grundlegende Informationen](../../features/traits/create-onboarded-rule-based-traits.md)
   * Benennen Sie die Eigenschaft.
   * Wählen Sie eine Datenquelle aus.
   * Wählen Sie einen Ordner &quot;Datenspeicherung&quot;.
1. Erweitern Sie den Bereich [!UICONTROL Configuration] und klicken Sie auf **[!UICONTROL Browse All Models]**.
Dadurch wird ein neues Fenster geöffnet, in dem Sie das Modell auswählen können, das Sie mit der Eigenschaft verwenden möchten.
1. Wählen Sie ein Modell aus und klicken Sie auf **[!UICONTROL Add Selected Model to Trait]**.
Durch Hinzufügen des Modells werden die Einstellungen für Reichweite und Genauigkeit verfügbar gemacht.
1. Wählen Sie als Ziel Reichweite oder Genauigkeit aus und wählen Sie einen Wert aus den entsprechenden Dropdownmenüs. Klicken Sie abschließend auf **[!UICONTROL Save]**.

## Konfigurationseinstellungen für algorithmische Eigenschaften {#configure-settings}

In [!UICONTROL Trait Builder] können Sie im Abschnitt [!UICONTROL Configuration] ein algorithmisches Modell mit einer Eigenschaft verknüpfen. Um den Prozess zur Erstellung algorithmischer Eigenschaften abzuschließen, wählen Sie ein Modell aus und wählen Sie ein Ziel für die Reichweite oder Genauigkeit.

### Voraussetzungen

<!-- r_algo_trait_config_section.xml -->

* [Erstellen eines Look-alike-Modells](../../features/algorithmic-models/create-model.md).
* Warten Sie, bis die Benachrichtigungs-E-Mail, in der Sie wissen, dass die Modelldatenausführung abgeschlossen ist, gesendet wurde.
* Füllen Sie die erforderlichen Felder im Abschnitt [Grundlegende Informationen](../../features/traits/create-onboarded-rule-based-traits.md) aus.

### Konfigurationsfelder und Einstellungen

| Oberflächenelement | Erklärung |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Klicken Sie auf die Schaltfläche **[!UICONTROL Update]**, um das Modellfenster zu öffnen. Wählen Sie im Fenster das algorithmische Modell aus, das Sie zum Erstellen der Eigenschaft verwenden möchten. |
| **[!UICONTROL Select Goal Accuracy]** | Wählen Sie diese Option, um eine Eigenschaft basierend auf der Genauigkeit zu erstellen. Die Genauigkeit ist ein bewerteter Wert, der angibt, wie nah potenzielle Benutzer Ihrer Grundlinie sind. Die Genauigkeitsskala reicht von 0 (am wenigsten genau) bis 1 (am genauesten). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Dieser Abschnitt auf der rechten Seite enthält bis zu 21 Zeilen numerischer Daten, die die Genauigkeit und Reichweitenwerte für Ihr Modell anzeigen. |
| **[!UICONTROL Reach and Accuracy Slider]** | Am unteren Rand des Diagramms befindet sich der Schieberegler, mit dem Sie einen numerischen Wert für Ihre Reichweiten- oder Genauigkeitsziele festlegen können. Sie können den Schieberegler einstellen und dann die Schaltfläche für die Reichweite oder Genauigkeit wählen, um eine Eigenschaft zu erstellen. |

>[!MORELIKETHIS]
>
>* [Genauigkeit und Reichweite](../../features/traits/trait-accuracy-reach.md)


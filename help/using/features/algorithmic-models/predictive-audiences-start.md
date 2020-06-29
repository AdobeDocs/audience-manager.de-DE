---
description: Predictive Audiencen helfen Ihnen, unbekannte Audiencen mithilfe der Datenwissenschaft in Echtzeit in verschiedene Personengruppen zu klassifizieren.
seo-description: Predictive Audiencen helfen Ihnen, unbekannte Audiencen mithilfe der Datenwissenschaft in Echtzeit in verschiedene Personengruppen zu klassifizieren.
seo-title: Verwalten von PrognoseAudiencen
solution: Audience Manager
title: Audience Manager Predictive Audiencen
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 0%

---


# Erste Schritte mit Prognostischen Audiencen {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

## Erstellen eines Predictive Audiencen-Modells {#create-predictive-audiences}

Bevor Sie ein [!UICONTROL Predictive Audiences] Modell erstellen, müssen Sie entscheiden, welcher Erstanbieter-Datenquelle Sie Ihre [!UICONTROL Predictive Audiences] Eigenschaften und Segmente zuweisen möchten. Sie können eine vorhandene Erstanbieter-Datenquelle verwenden oder eine neue erstellen. Weitere Informationen zum Erstellen einer neuen Erstanbieter-Datenquelle finden Sie unter Datenquellen [verwalten](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) .

Sobald Sie wissen, welche Datenquelle Sie verwenden werden, führen Sie die folgenden Schritte aus.

1. Gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Klicken Sie im [!UICONTROL Predictive Audiences] Abschnitt auf **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Definieren Sie als Nächstes die Personen, nach denen Sie Ihre Audience klassifizieren möchten. Dazu wählen Sie entweder Eigenschaften oder Segmente aus, aus denen Sie Personas erstellen möchten. Verwenden Sie die Registerkarten [!UICONTROL Traits] und [!UICONTROL Segments] in der oberen linken Ecke des Bildschirms, um zwischen Ihrem Eigenschaftenkatalog und dem Segmentkatalog zu wechseln. Nachdem Sie die Eigenschaften oder Segmente identifiziert haben, die Sie als Personas verwenden möchten, klicken Sie auf das entsprechende **[!UICONTROL Add]** Symbol in der [!UICONTROL Action] Spalte.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Sie müssen mindestens zwei Eigenschaften oder zwei Segmente für Ihre Ausgangspersonen auswählen. Sie können keine Kombination aus Eigenschaften und Segmenten verwenden.
1. Klicken Sie auf **[!UICONTROL Next]** , nachdem Sie Ihre Person definiert haben.
1. Wählen Sie anschließend die zu klassifizierende Erstanbieter-Audience aus, indem Sie eine Erstanbieter-Eigenschaft oder ein Erstanbieter-Segment für diese Audience auswählen. Verwenden Sie die Registerkarten [!UICONTROL Traits] und [!UICONTROL Segments] in der oberen linken Ecke des Bildschirms, um zwischen Ihrem Eigenschaftenkatalog und dem Segmentkatalog zu wechseln. Wählen Sie die Eigenschaften oder Segmente des Erstanbieters aus, die Sie als Audience verwenden möchten, um sie dem Modell hinzuzufügen.
   ![smart-persona-select-Audience](assets/predictive-audiences-audience.png)
1. Klicken Sie auf **[!UICONTROL Next]** , nachdem Sie Ihre Audience ausgewählt haben.
1. Füllen Sie die Modelldetails aus:
   1. **[!UICONTROL Model Name]**: Geben Sie einen beschreibenden Namen für das Modell ein, damit Sie es später identifizieren können. Die Namen der vom Modell generierten Segmente werden mit dem Modellnamen Beginn.
   2. **[!UICONTROL Description]**: Geben Sie eine Beschreibung des Modells ein, mit der Sie den Verwendungsfall identifizieren können.
   3. **[!UICONTROL Data Source]**: Wählen Sie die Erstanbieter-Datenquelle aus, der die [!UICONTROL Predictive Audiences] Segmente aus diesem Modell zugewiesen werden sollen.
      ![Predictive-Audiencen-save](assets/predictive-audiences-save.png)
1. Klicken **[!UICONTROL Save]**.

## Bearbeiten prädiktiver Audiencen {#edit-predictive-audiences}

Audience Manager unterstützt keine Bearbeitung vorhandener [!UICONTROL Predictive Audiences] Modelle. Um die Konfiguration eines Modells zu ändern, müssen Sie ein neues Modell erstellen. Wenn Sie die Grenze von 10 [!UICONTROL Predictive Audiences] Modellen erreicht haben und eines Ihrer Modelle bearbeiten müssen, müssen Sie ein Modell löschen und ein neues erstellen.

## Löschen von prädiktiven Audiencen {#delete-predictive-audiences}

Um ein [!UICONTROL Predictive Audiences] Modell zu löschen, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, suchen Sie das zu löschende Modell und klicken Sie auf das **[!UICONTROL Delete]** Symbol.

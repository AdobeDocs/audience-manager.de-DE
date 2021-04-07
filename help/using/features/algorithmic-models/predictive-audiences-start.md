---
description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-title: Verwalten von PrognoseAudiencen
solution: Audience Manager
title: Erste Schritte mit vorhersagekräftigen Zielgruppen
feature: Algorithmische Modelle
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 7%

---

# Erste Schritte mit vorhersagekräftigen Zielgruppen {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

## Erstellen eines Predictive Audiencen-Modells {#create-predictive-audiences}

Bevor Sie ein [!UICONTROL Predictive Audiences]-Modell erstellen, müssen Sie entscheiden, welcher Erstanbieter-Datenquelle Sie [!UICONTROL Predictive Audiences]-Eigenschaften und -Segmente zuweisen möchten. Sie können eine vorhandene Erstanbieter-Datenquelle verwenden oder eine neue erstellen. Weitere Informationen zum Erstellen einer neuen Erstanbieter-Datenquelle finden Sie unter [Datenquellen verwalten](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html).

Sobald Sie wissen, welche Datenquelle Sie verwenden werden, führen Sie die folgenden Schritte aus.

1. Gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Klicken Sie im Abschnitt [!UICONTROL Predictive Audiences] auf **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Definieren Sie als Nächstes die Personen, nach denen Sie Ihre Audience klassifizieren möchten. Dazu wählen Sie entweder Eigenschaften oder Segmente aus, aus denen Sie Personas erstellen möchten. Verwenden Sie die Registerkarten [!UICONTROL Traits] und [!UICONTROL Segments] in der oberen linken Ecke des Bildschirms, um zwischen Ihrem Eigenschaftenkatalog und dem Segmentkatalog zu wechseln. Nachdem Sie die Eigenschaften oder Segmente identifiziert haben, die Sie als Personas verwenden möchten, klicken Sie in der Spalte [!UICONTROL Action] auf das entsprechende **[!UICONTROL Add]**-Symbol.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Sie müssen mindestens zwei Eigenschaften oder zwei Segmente für Ihre Ausgangspersonen auswählen. Sie können keine Kombination aus Eigenschaften und Segmenten verwenden.
1. Klicken Sie auf **[!UICONTROL Next]**, nachdem Sie Ihre Personas definiert haben.
1. Wählen Sie anschließend die zu klassifizierende Erstanbieter-Audience aus, indem Sie eine Erstanbieter-Eigenschaft oder ein Erstanbieter-Segment für diese Audience auswählen. Verwenden Sie die Registerkarten [!UICONTROL Traits] und [!UICONTROL Segments] in der oberen linken Ecke des Bildschirms, um zwischen Ihrem Eigenschaftenkatalog und dem Segmentkatalog zu wechseln. Wählen Sie die Eigenschaften oder Segmente des Erstanbieters aus, die Sie als Audience verwenden möchten, um sie dem Modell hinzuzufügen.
   ![smart-persona-select-Audience](assets/predictive-audiences-audience.png)
1. Klicken Sie auf **[!UICONTROL Next]**, nachdem Sie Ihre Audience ausgewählt haben.
1. Füllen Sie die Modelldetails aus:
   * **[!UICONTROL Model Name]**: Geben Sie einen beschreibenden Namen für das Modell ein, damit Sie es später identifizieren können. Die Namen der vom Modell generierten Segmente werden mit dem Modellnamen Beginn.
   * **[!UICONTROL Description]**: Geben Sie eine Beschreibung des Modells ein, mit der Sie den Verwendungsfall identifizieren können.
   * **[!UICONTROL Data Source]**: Wählen Sie die Erstanbieter-Datenquelle aus, der die  [!UICONTROL Predictive Audiences] Segmente aus diesem Modell zugewiesen werden sollen.
   * **[!UICONTROL Profile Merge Rule]**: Wählen Sie  [!UICONTROL Profile Merge Rule] die für alle von diesem Modell  [!UICONTROL segments] erstellten Prognosen zuzuweisenden Optionen aus. Wenn Ihre ausgewählte Audience eine [!UICONTROL segment] ist, empfehlen wir, dieselbe [!UICONTROL Profile Merge Rule] der Zielgruppe-Audience auszuwählen.
      ![Predictive-Audiencen-save](assets/predictive-audiences-save.png)
1. Klicken **[!UICONTROL Save]**.

## Klonen und Bearbeiten von Prädiktiven Audiencen-Modellen {#clone-predictive-audiences}

Audience Manager unterstützt keine Bearbeitung vorhandener [!UICONTROL Predictive Audiences]-Modelle. Um die Konfiguration eines Modells zu ändern, können Sie einen Klon eines vorhandenen Modells erstellen und bearbeiten. So können Sie Folgendes tun:

1. Gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Klicken Sie auf den Namen des [!UICONTROL Predictive Audiences]-Modells, das Sie klonen möchten.
3. Klicken Sie oben links im Bildschirm auf die Schaltfläche **[!UICONTROL Clone]**.
   ![Predictive-Audiencen-clone](assets/predictive-audiences-clone.png)
4. Nachdem Sie das Modell geklont haben, werden Sie zur Seite [!DNL Save & Configure] des geklonten Modells geleitet. Auf dieser Seite können Sie die Werte [!UICONTROL data source] und[!UICONTROL Profile Merge Rule] des Modells ändern. Um die Audience der Personas und der Zielgruppe des geklonten Modells zu bearbeiten, verwenden Sie die Schaltflächen [!UICONTROL Back] und [!UICONTROL Next], um zwischen den drei Registerkarten zu navigieren, oder klicken Sie auf die drei Registerkartennamen

   ![prognotive-Audiencen-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. Wenn Sie die Bearbeitung eines Modells abgeschlossen haben, klicken Sie auf **[!UICONTROL Save]**.

## Löschen prädiktiver Audiencen {#delete-predictive-audiences}

Um ein [!UICONTROL Predictive Audiences]-Modell zu löschen, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, suchen Sie das zu löschende Modell und klicken Sie auf das Symbol **[!UICONTROL Delete]**.

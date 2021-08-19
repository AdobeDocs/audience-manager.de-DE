---
description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-title: Verwalten prädiktiver Zielgruppen
solution: Audience Manager
title: Erste Schritte mit vorhersagekräftigen Zielgruppen
feature: Algorithmische Modelle
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 7%

---

# Erste Schritte mit vorhersagekräftigen Zielgruppen {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

## Erstellen eines Predictive Audiences-Modells {#create-predictive-audiences}

Bevor Sie ein [!UICONTROL Predictive Audiences]-Modell erstellen, müssen Sie entscheiden, welcher Erstanbieter-Datenquelle Sie Ihre [!UICONTROL Predictive Audiences]-Eigenschaften und -Segmente zuweisen möchten. Sie können eine vorhandene Erstanbieter-Datenquelle verwenden oder eine neue erstellen. Weitere Informationen zum Erstellen einer neuen Erstanbieter-Datenquelle finden Sie unter [Data Sources verwalten](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html) .

Sobald Sie wissen, welche Datenquelle Sie verwenden werden, führen Sie die folgenden Schritte aus.

1. Gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Klicken Sie im Abschnitt [!UICONTROL Predictive Audiences] auf **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Definieren Sie anschließend die Personas, nach denen Sie Ihre Audience klassifizieren möchten. Wählen Sie dazu Eigenschaften oder Segmente aus, aus denen Personas erstellt werden sollen. Verwenden Sie die Registerkarten [!UICONTROL Traits] und [!UICONTROL Segments] oben links im Bildschirm, um zwischen Ihrer Eigenschaft und dem Segmentkatalog zu wechseln. Nachdem Sie die Eigenschaften oder Segmente identifiziert haben, die Sie als Personas verwenden möchten, klicken Sie in der Spalte [!UICONTROL Action] auf das entsprechende **[!UICONTROL Add]**-Symbol.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Sie müssen mindestens zwei Eigenschaften oder zwei Segmente für Ihre Ausgangspersonen auswählen. Sie können keine Kombination aus Eigenschaften und Segmenten verwenden.
1. Klicken Sie auf **[!UICONTROL Next]**, nachdem Sie Ihre Personas definiert haben.
1. Wählen Sie anschließend die Erstanbieter-Zielgruppe aus, die Sie klassifizieren möchten, indem Sie eine Erstanbietereigenschaft oder ein Segment für diese Zielgruppe auswählen. Verwenden Sie die Registerkarten [!UICONTROL Traits] und [!UICONTROL Segments] oben links im Bildschirm, um zwischen Ihren Eigenschaften und dem Segmentkatalog zu wechseln. Wählen Sie die Erstanbietereigenschaft oder das Segment aus, die/das Sie als Ihre Zielgruppe verwenden möchten, um sie/es zum Modell hinzuzufügen.
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. Klicken Sie auf **[!UICONTROL Next]**, nachdem Sie Ihre Audience ausgewählt haben.
1. Füllen Sie die Modelldetails aus:
   * **[!UICONTROL Model Name]**: Geben Sie einen beschreibenden Namen für das Modell ein, damit Sie es später identifizieren können. Namen der vom Modell generierten Segmente beginnen mit dem Namen des Modells.
   * **[!UICONTROL Description]**: Geben Sie eine Beschreibung des Modells ein, mit dem Sie den Anwendungsfall identifizieren können.
   * **[!UICONTROL Data Source]**: Wählen Sie die Erstanbieter-Datenquelle aus, der die  [!UICONTROL Predictive Audiences] Segmente dieses Modells zugewiesen werden sollen.
   * **[!UICONTROL Profile Merge Rule]**: Wählen Sie die  [!UICONTROL Profile Merge Rule] zuzuweisende für alle von diesem Modell  [!UICONTROL segments] erstellten Prognosen aus. Wenn Ihre ausgewählte Zielgruppe eine [!UICONTROL segment] ist, empfehlen wir, dieselbe [!UICONTROL Profile Merge Rule] der Zielgruppe auszuwählen.
      ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. Klicken **[!UICONTROL Save]**.

## Klonen und Bearbeiten von Predictive Audience-Modellen {#clone-predictive-audiences}

Audience Manager unterstützt keine Bearbeitung vorhandener [!UICONTROL Predictive Audiences]-Modelle. Um die Konfiguration eines Modells zu ändern, können Sie einen Klon eines vorhandenen Modells erstellen und es bearbeiten. So können Sie Folgendes tun:

1. Gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Klicken Sie auf den Namen des Modells [!UICONTROL Predictive Audiences], das Sie klonen möchten.
3. Klicken Sie auf die Schaltfläche **[!UICONTROL Clone]** oben links im Bildschirm.
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. Sobald Sie das Modell klonen, gelangen Sie zur Seite [!DNL Save & Configure] des geklonten Modells. Auf dieser Seite können Sie die [!UICONTROL data source] und die zugewiesene[!UICONTROL Profile Merge Rule] des Modells ändern. Um die Rollen und die Zielgruppe des geklonten Modells zu bearbeiten, navigieren Sie mit den Schaltflächen [!UICONTROL Back] und [!UICONTROL Next] zwischen den drei Registerkarten oder klicken Sie auf die drei Registerkartennamen

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. Wenn Sie die Bearbeitung eines Modells abgeschlossen haben, klicken Sie auf **[!UICONTROL Save]**.

## Löschen von Predictive Audiences {#delete-predictive-audiences}

Um ein [!UICONTROL Predictive Audiences]-Modell zu löschen, navigieren Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, suchen Sie das Modell, das Sie löschen möchten, und klicken Sie auf das Symbol **[!UICONTROL Delete]**.

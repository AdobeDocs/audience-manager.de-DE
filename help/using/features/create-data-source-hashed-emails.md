---
title: Konfigurieren einer Datenquelle für Hash-E-Mail-Workflows
description: Erfahren Sie, wie Sie eine Datenquelle erstellen, um Hash-E-Mails für Hash-E-Mail-Workflows zu speichern.
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
TQID: 'https://experienceleague.adobe.com/dPV7bJC5zIBkj1EX43q4FWU7XP0gs-dhBYTcW8mApL4'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
    internal-label: Audience Marketplace
subfeature_v2:
  - id: d921db59-bd4a-43dc-97e6-4ff4611f1ae8
    internal-label: Data sources
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%
---
# Konfigurieren einer Datenquelle für Hash-E-Mail-Workflows

Für Hash-E-Mail-Workflows, wie z. B. personenbasierte Ziele, müssen Sie eine Datenquelle erstellen, um die Hash-E-Mail-Adressen zu speichern.

Gehen Sie wie folgt vor, um eine Datenquelle für Hash-E-Mails zu erstellen und zu konfigurieren.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** und klicken Sie auf **[!UICONTROL Add New]**.
1. Geben Sie einen **[!UICONTROL Name]** und einen **[!UICONTROL Description]** für Ihre neue Datenquelle ein.
1. Wählen Sie im Dropdown-Menü **[!UICONTROL ID Type]** die Option **[!UICONTROL Cross Device]** aus.
   ![Bild der Audience Manager-Benutzeroberfläche mit dem Abschnitt mit den Datenquellendetails.](../features/assets/create-hashed-email-data-source.png)
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Wählen Sie im Dropdown-Menü die **[!UICONTROL Emails(SHA256, lowercased)]** für diese Datenquelle aus.

   >[!IMPORTANT]
   >
   >Diese Option kennzeichnet die Datenquelle nur als mit Daten, die mit diesem bestimmten Algorithmus gehasht wurden. Audience Manager hasst die Daten in diesem Schritt nicht. Stellen Sie sicher, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem [!DNL SHA256]-Algorithmus gehasht wurden. Andernfalls können Sie es nicht für Hash-E-Mail-Workflows verwenden.

   ![Bild der Audience Manager-Benutzeroberfläche mit dem Abschnitt zu den Datenquelleneinstellungen.](../features/assets/data-source-settings.png)

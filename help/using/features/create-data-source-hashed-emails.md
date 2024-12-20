---
title: Konfigurieren einer Datenquelle für Hash-E-Mail-Workflows
description: Erfahren Sie, wie Sie eine Datenquelle erstellen, um Hash-E-Mails für Hash-E-Mail-Workflows zu speichern.
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
source-git-commit: d55dbc4f9630e3d22dfb988f6725f33993229c48
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Konfigurieren einer Datenquelle für Hash-E-Mail-Workflows

Für Hash-E-Mail-Workflows, wie z. B. personenbasierte Ziele, müssen Sie eine Datenquelle erstellen, um die Hash-E-Mail-Adressen zu speichern.

Gehen Sie wie folgt vor, um eine Datenquelle für Hash-E-Mails zu erstellen und zu konfigurieren.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** und klicken Sie auf **[!UICONTROL Add New]**.
1. Geben Sie einen **[!UICONTROL Name]** und einen **[!UICONTROL Description]** für Ihre neue Datenquelle ein.
1. Wählen Sie im Dropdown-Menü **[!UICONTROL ID Type]** die Option **[!UICONTROL Cross Device]** aus.
   ![Audience Manager-UI-Bild, das den Abschnitt mit den Datenquellendetails anzeigt.](../features/assets/create-hashed-email-data-source.png)
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Wählen Sie im Dropdown-Menü die **[!UICONTROL Emails(SHA256, lowercased)]** für diese Datenquelle aus.

   >[!IMPORTANT]
   >
   >Diese Option kennzeichnet die Datenquelle nur als mit Daten, die mit diesem bestimmten Algorithmus gehasht wurden. Der Audience Manager hasst die Daten in diesem Schritt nicht. Stellen Sie sicher, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem [!DNL SHA256]-Algorithmus gehasht wurden. Andernfalls können Sie es nicht für Hash-E-Mail-Workflows verwenden.

   ![Bild der Audience Manager-Benutzeroberfläche mit dem Abschnitt zu den Datenquelleneinstellungen.](../features/assets/data-source-settings.png)

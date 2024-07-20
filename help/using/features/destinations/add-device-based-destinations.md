---
description: In diesem Artikel wird beschrieben, wie Sie neue gerätebasierte Ziele über die Audience Manager-Benutzeroberfläche konfigurieren.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Hinzufügen neuer gerätebasierter Ziele
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 1%

---

# Hinzufügen neuer gerätebasierter Ziele {#add-new-device-based-destinations}

In diesem Artikel wird beschrieben, wie Sie neue gerätebasierte Ziele über die Audience Manager-Benutzeroberfläche konfigurieren.

>[!IMPORTANT]
>
>Derzeit sind die meisten gerätebasierten Ziele nicht für den Self-Service-Konfigurations-Workflow qualifiziert. Wenn das gerätebasierte Ziel, das Sie hinzufügen müssen, nicht in der Zielliste angezeigt wird, wenden Sie sich an Ihren Adobe-Berater oder an den Kundensupport, um Hilfe zu erhalten.

## Überblick {#overview}

Der Prozess zum Hinzufügen eines neuen gerätebasierten Ziels besteht aus zwei Hauptschritten. Zunächst müssen Sie die Integration zwischen Audience Manager und dem Zielpartner konfigurieren. Danach können Sie ein neues gerätebasiertes Ziel erstellen.

## Voraussetzungen {#prerequisites}

Wenden Sie sich beim Erstellen des ersten gerätebasierten Ziels mit einer integrierten Plattform an die Adobe Consulting- oder Kundenunterstützung, um die ID-Synchronisierung zwischen Audience Manager und der integrierten Plattform für Ihr Konto zu aktivieren. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und der Zielplattform erforderlich.

## Schritt 1. Mit einer Zielplattform authentifizieren {#step1}

Bevor Sie ein neues gerätebasiertes Ziel erstellen können, müssen Sie die Integration zwischen Audience Manager und der Zielplattform konfigurieren. Gehen Sie dazu folgendermaßen vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!DNL Administration > Integrated Accounts]**. Wenn Sie bereits eine Integration mit einer Zielplattform konfiguriert haben, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
1. Klicken Sie auf **[!DNL Add Account]**.
1. Wählen Sie die Zielplattform aus, mit der Sie sich authentifizieren möchten, und klicken Sie auf **[!DNL Confirm]** , um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.

   ![integrated-platforms](assets/dbd-integrated-platforms.png)

1. Nachdem Sie sich bei Ihrem Zielplattformkonto authentifiziert haben, werden Sie zu dem Audience Manager weitergeleitet, in dem Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das Advertiser-Konto aus, das Sie verwenden möchten, und klicken Sie auf **[!DNL Confirm]**.

## Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2}

Nachdem Sie die Zielplattformintegration konfiguriert haben, können Sie das neue Ziel erstellen. Gehen Sie dazu folgendermaßen vor:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen bei der korrekten Identifizierung des Ziels hilft.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!DNL Audience Data > Destinations]** und klicken Sie auf **[!DNL Create Destination]**.
1. Geben Sie im Abschnitt **[!DNL Basic Information]** einen **[!DNL Name]** und einen **[!DNL Description]** für Ihr neues Ziel ein und verwenden Sie die Einstellungen in der folgenden Liste:

   ![setup](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: Wählen Sie die Zielplattform aus, an die Sie Zielgruppensegmente senden möchten.
   * **[!DNL Account]**: Wählen Sie das gewünschte Advertiser-Konto aus, das mit der ausgewählten Plattform verknüpft ist.
1. Klicken Sie auf **[!DNL Next]**.
1. Wählen Sie die [Datenexportbeschriftungen](/help/using/features/data-export-controls.md#controls-labels) aus, die Sie für dieses Ziel festlegen möchten.
1. Klicken Sie auf **[!DNL Save]**.
1. Wählen Sie im Abschnitt **[!DNL Segment Mappings]** die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
1. Speichern Sie das Ziel.

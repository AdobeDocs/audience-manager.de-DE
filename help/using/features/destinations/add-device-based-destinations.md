---
description: In diesem Artikel wird beschrieben, wie Sie neue gerätebasierte Ziele über die Benutzeroberfläche des Audience Managers konfigurieren.
seo-description: In diesem Artikel wird beschrieben, wie Sie neue gerätebasierte Ziele über die Benutzeroberfläche des Audience Managers konfigurieren.
seo-title: Hinzufügen neuer gerätebasierter Ziele
solution: Audience Manager
title: Hinzufügen neuer gerätebasierter Ziele
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 4%

---


# Hinzufügen neuer gerätebasierter Ziele {#add-new-device-based-destinations}

In diesem Artikel wird beschrieben, wie Sie neue gerätebasierte Ziele über die Benutzeroberfläche des Audience Managers konfigurieren.

>[!IMPORTANT]
>
>Derzeit sind die meisten gerätebasierten Ziele nicht für den Selbstbedienungskonfigurationsarbeitsablauf geeignet. Wenn das hinzuzufügende gerätebasierte Ziel nicht in der Liste &quot;Ziele&quot;angezeigt wird, wenden Sie sich an Ihren Adobe-Berater oder den Kundendienst, um Hilfe zu erhalten.

## Überblick {#overview}

Der Prozess zum Hinzufügen eines neuen gerätebasierten Ziels besteht aus zwei Hauptschritten. Zunächst müssen Sie die Integration zwischen Audience Manager und dem Zielpartner konfigurieren. Danach können Sie ein neues gerätebasiertes Ziel erstellen.

## Voraussetzungen {#prerequisites}

Wenden Sie sich bei der Erstellung des ersten gerätebasierten Ziels mit einer integrierten Plattform an Adobe Consulting oder den Kundendienst, um die ID-Synchronisierung zwischen Audience Manager und der integrierten Kontoplattform zu aktivieren. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und der Zielplattform erforderlich.

## Schritt 1. Authentifizierung mit einer Zielplattform {#step1}

Bevor Sie ein neues gerätebasiertes Ziel erstellen können, müssen Sie die Integration zwischen Audience Manager und der Zielplattform konfigurieren. So geht das:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!DNL Administration > Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer Zielplattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
1. Klicken **[!DNL Add Account]**.
1. Wählen Sie die Zielplattform aus, mit der Sie sich authentifizieren möchten, und klicken Sie auf **[!DNL Confirm]**, um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.

   ![integrierte Plattformen](assets/dbd-integrated-platforms.png)

1. Nachdem Sie sich bei Ihrem Zielplattformkonto authentifiziert haben, werden Sie an den Audience Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!DNL Confirm]**.

## Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2}

Nachdem Sie die Integration der Zielplattform konfiguriert haben, können Sie das neue Ziel erstellen. So geht das:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen bei der korrekten Identifizierung des Ziels hilft.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!DNL Audience Data > Destinations]** und klicken Sie auf **[!DNL Create Destination]**.
1. Geben Sie im Abschnitt **[!DNL Basic Information]** einen **[!DNL Name]** und **[!DNL Description]** für Ihr neues Ziel ein und verwenden Sie die Einstellungen in der folgenden Liste:

   ![setup](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**:  [!DNL Device-Based];
   * **[!DNL Platform]**: Wählen Sie die Zielplattform aus, an die Sie Audiencen-Segmente senden möchten.
   * **[!DNL Account]**: Wählen Sie das gewünschte Advertiser-Konto aus, das mit der ausgewählten Plattform verknüpft ist.
1. Klicken **[!DNL Next]**.
1. Wählen Sie die für dieses Ziel festzulegenden [Datenexportbezeichnungen](/help/using/features/data-export-controls.md#controls-labels).
1. Klicken **[!DNL Save]**.
1. Wählen Sie im Abschnitt **[!DNL Segment Mappings]** die Audiencen aus, die Sie an dieses Ziel senden möchten.
1. Speichern Sie das Ziel.

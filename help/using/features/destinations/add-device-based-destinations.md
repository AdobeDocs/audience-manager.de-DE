---
description: In diesem Artikel wird beschrieben, wie Sie neue gerätebasierte Ziele über die Benutzeroberfläche von Audience Manager konfigurieren.
seo-description: In diesem Artikel wird beschrieben, wie Sie neue gerätebasierte Ziele über die Benutzeroberfläche von Audience Manager konfigurieren.
seo-title: Neue gerätebasierte Ziele hinzufügen
solution: Audience Manager
title: Neue gerätebasierte Ziele hinzufügen
translation-type: tm+mt
source-git-commit: c206246a4a586d1148c18e0bce734d07963a85f6

---


# Neue gerätebasierte Ziele hinzufügen {#add-new-device-based-destinations}

In diesem Artikel wird beschrieben, wie Sie neue gerätebasierte Ziele über die Benutzeroberfläche von Audience Manager konfigurieren.

## Überblick {#overview}

Das Hinzufügen eines neuen gerätebasierten Ziels besteht aus zwei Hauptschritten. Zunächst müssen Sie die Integration zwischen Audience Manager und dem Zielpartner konfigurieren. Danach können Sie ein neues gerätebasiertes Ziel erstellen.

## Voraussetzungen {#prerequisites}

Wenden Sie sich beim Erstellen des ersten gerätebasierten Ziels mit einer integrierten Plattform an den Adobe Consulting oder die Kundenunterstützung, um die ID-Synchronisierung zwischen Audience Manager und der integrierten Plattform für Ihr Konto zu aktivieren. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und der Zielplattform erforderlich.

>[!IMPORTANT]
>
>Nicht alle gerätebasierten Ziele sind für den Selbstbedienungskonfigurationsarbeitsablauf zugelassen. Wenn das von Ihnen hinzuzufügende gerätebasierte Ziel nicht in der Liste der Ziele angezeigt wird, wenden Sie sich an Ihren Adobe-Berater oder an den Kundensupport.

## Schritt 1. Authentifizierung mit einer Zielplattform {#step1}

Bevor Sie ein neues gerätebasiertes Ziel erstellen können, müssen Sie die Integration zwischen Audience Manager und der Zielplattform konfigurieren. So geht das:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!DNL Administration > Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer Zielplattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
1. Klicken Sie auf **[!DNL Add Account]**.
1. Wählen Sie die Zielplattform aus, mit der Sie sich authentifizieren möchten, und klicken Sie auf , um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet **[!DNL Confirm]** zu werden. ![integrierte Plattformen](assets/dbd-integrated-platforms.png)
1. Nachdem Sie sich bei Ihrem Konto für die Zielplattform authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!DNL Confirm]**.

## Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2}

Nachdem Sie die Integration der Zielplattform konfiguriert haben, können Sie das neue Ziel erstellen. So geht das:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen bei der korrekten Identifizierung des Ziels hilft.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!DNL Audience Data > Destinations]** und klicken Sie auf **[!DNL Create Destination]**.
1. Geben Sie im **[!DNL Basic Information]** Abschnitt ein **[!DNL Name]** und **[!DNL Description]** für das neue Ziel ein und verwenden Sie die Einstellungen in der folgenden Liste: ![Setup](assets/dbd-new-basic.png)
   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: Wählen Sie die Zielplattform aus, an die Sie Zielgruppensegmente senden möchten.
   * **[!DNL Account]**: Wählen Sie das gewünschte Advertiser-Konto aus, das mit der ausgewählten Plattform verknüpft ist.
1. Klicken Sie auf **[!DNL Next]**.
1. Wählen Sie die [Datenexportbeschriftungen](/help/using/features/data-export-controls.md#controls-labels) aus, die Sie für dieses Ziel festlegen möchten.
1. Klicken Sie auf **[!DNL Save]**.
1. Wählen Sie im **[!DNL Segment Mappings]** Abschnitt die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
1. Speichern Sie das Ziel.

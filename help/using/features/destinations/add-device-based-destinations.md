---
description: In diesem Artikel wird beschrieben, wie Sie neue gerätebasierte Ziele aus der Benutzeroberfläche von Audience Manager konfigurieren.
seo-description: In diesem Artikel wird beschrieben, wie Sie neue gerätebasierte Ziele aus der Benutzeroberfläche von Audience Manager konfigurieren.
seo-title: Neue gerätebasierte Ziele hinzufügen
solution: Audience Manager
title: Neue gerätebasierte Ziele hinzufügen
translation-type: tm+mt
source-git-commit: d185a1d418e99abb99c36b28dfb419a1fb3b60f5

---


# Neue gerätebasierte Ziele hinzufügen {#add-new-device-based-destinations}

In diesem Artikel wird beschrieben, wie Sie neue gerätebasierte Ziele aus der Benutzeroberfläche von Audience Manager konfigurieren.

## Überblick {#overview}

Das Hinzufügen eines neuen gerätebasierten Ziels besteht aus zwei Hauptschritten. Zunächst müssen Sie die Integration zwischen Audience Manager und dem Zielpartner konfigurieren. Anschließend können Sie ein neues gerätebasiertes Ziel erstellen.

>[!IMPORTANT]
>
>Nicht alle gerätebasierten Ziele sind für den Selbstbedienungs-Workflow berechtigt. Wenn das gerätebasierte Ziel, das Sie hinzufügen müssen, nicht in der Zielgruppenliste angezeigt wird, wenden Sie sich an Ihren Adobe-Berater oder Kundensupport, um Hilfe zu erhalten.

## Schritt 1. Authentifizieren mit einer Zielplattform {#step1}

Bevor Sie ein neues gerätebasiertes Ziel erstellen können, müssen Sie die Integration zwischen Audience Manager und der Zielplattform konfigurieren. Gehen Sie wie folgt vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und wechseln **[!DNL Administration > Integrated Accounts]** Sie zu. Wenn Sie eine zuvor konfigurierte Integration mit einer Zielplattform haben, sollte sie auf dieser Seite aufgelistet werden. Andernfalls ist die Seite leer.
2. Klicken Sie auf **[!DNL Add Account]**.
3. Wählen Sie die Zielplattform aus, mit der Sie sich authentifizieren möchten, und klicken **[!DNL Confirm]** Sie auf, um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden. ![integrierte Plattformen](assets/dbd-integrated-platforms.png)
4. Sobald Sie sich für Ihr Zielplattform-Konto authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie Ihre zugeordneten Advertiserkonten sehen sollten. Wählen Sie das gewünschte Advertiserkonto aus und klicken **[!DNL Confirm]** Sie auf.

## Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2}

Nachdem Sie die Zielplattform-Integration konfiguriert haben, können Sie das neue Ziel erstellen. Gehen Sie wie folgt vor:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen dabei hilft, das Ziel richtig zu identifizieren.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und **[!DNL Audience Data > Destinations]** klicken **[!DNL Create Destination]** Sie auf.
2. Geben Sie im **[!DNL Basic Information]** Abschnitt ein **[!DNL Name]** und **[!DNL Description]** für Ihr neues Ziel ein und verwenden Sie die Einstellungen in der Liste unten: ![setup](assets/dbd-new-basic.png)
   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: Wählen Sie die Zielplattform aus, an die Zielgruppensegmente gesendet werden sollen.
   * **[!DNL Account]**: Wählen Sie das gewünschte Advertiserkonto aus, das der ausgewählten Plattform zugeordnet ist.
3. Klicken Sie auf **[!DNL Next]**.
4. Wählen Sie die [Datenexportbeschriftungen](/help/using/features/data-export-controls.md#controls-labels) aus, die Sie für dieses Ziel festlegen möchten.
5. Klicken Sie auf **[!DNL Save]**.
6. Wählen Sie im **[!DNL Segment Mappings]** Abschnitt die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
7. Speichern Sie das Ziel.


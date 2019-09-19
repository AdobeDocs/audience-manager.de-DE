---
description: Richten Sie eine Google-Gruppe ein, um Ihre DCM-Datendateien (DoubleClick Campaign Manager) in Audience Manager zu laden. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und enthält Links zu DCM-Ressourcen, die Ihnen beim Einstieg helfen.
seo-description: Richten Sie eine Google-Gruppe ein, um Ihre DCM-Datendateien (DoubleClick Campaign Manager) in Audience Manager zu laden. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und enthält Links zu DCM-Ressourcen, die Ihnen beim Einstieg helfen.
seo-title: DCM-Datendateien in Audience Manager importieren
solution: Audience Manager
title: DCM-Datendateien in Audience Manager importieren
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

Richten Sie eine Google-Gruppe ein, um Ihre DCM-Datendateien (DoubleClick Campaign Manager) in Audience Manager zu laden. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und enthält Links zu DCM-Ressourcen, die Ihnen beim Einstieg helfen.

## Integrationszusammenfassung

DCM [!DNL Google]'s ersetzt[!DNL DoubleClick for Advertisers] (DFA). Ähnlich wie bei DFA können DCM-Kunden ihre Daten in [!DNL Audience Manager] importieren, ansehen und verwenden. Sie [!DNL Audience Manager] können jedoch nicht direkt auf Ihre [!UICONTROL Data Transfer] und Ihre [!UICONTROL Match Table] Dateien zugreifen und diese importieren. Den Import dieser Dateien muss der Kunde selbst übernehmen.

Das Einrichtungsverfahren ist jedoch in der Hilfe zum [DoubleClick Kampagnen-Manager gut dokumentiert](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). Außerdem können Sie die unten aufgeführten Schritte überprüfen, um zu beginnen.

>[!CAUTION]
>
>DCM-Datendateien enthalten Daten für alle Ihre Advertiser oder Clients. Wenn Sie bestimmte Clients auslassen müssen, müssen Sie die Dateien bearbeiten, bevor Sie sie verfügbar machen [!DNL Audience Manager].

## Häufigkeit und Verfügbarkeit der Datenübertragung

[!DNL Audience Manager] überprüft und überträgt Daten einmal täglich. Die Daten sind in der Regel nach [!DNL Audience Manager] 24 Stunden verfügbar.

## Schritte

1. [Eine Gruppe erstellen](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Gruppen steuern den Zugriff auf Ihre DCM-Daten. Schließlich laden Sie diese Gruppe ein und fügen sie [!DNL Audience Manager] hinzu.

1. [Überprüfen Sie Ihren Google Cloud-Speicherstatus](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud-Speicher enthält den Datenbehälter, der Ihre [!UICONTROL Data Transfer] und [!UICONTROL Match Tables]enthält. Sie müssen einen Behälter einrichten oder sicherstellen, dass Ihre neue Gruppe Zugriff auf einen vorhandenen Datenspeicher hat.

1. [Abrufen einer Datendatei-URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   Arbeiten Sie mit Ihrem DCM-Kundenbetreuer oder Plattformlösungen-Berater zusammen. Sie erhalten eine URL zu Ihren Datendateien. [!DNL Google] kann das Format für Behälter- und Dateinamen in zukünftigen Versionen ändern. Wenden Sie sich erneut an Ihren DCM-Kundenbetreuer, um sicherzustellen, dass Sie die richtigen Formate verwenden.

1. [Legen Sie Behälterberechtigungen](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)fest.

   Mit der [!DNL Cloud Storage Manager] können Sie die Datenfreigabe und den Behälterzugriff steuern. Erteilen Sie Ihrer Gruppe Lesezugriff auf den Behälter, der Ihre [!UICONTROL Data Transfer] und [!UICONTROL Match Table] Dateien enthält.

1. [Richten Sie die Datenfreigabe](https://support.google.com/dcm/partner/answer/6206106?hl=en)ein.

   Freigegebene DCM-Benutzer-IDs werden zum Schutz der Privatsphäre verschlüsselt. Mit der Verschlüsselung werden am Ende der Datenübertragungsdatei zwei Spalten hinzugefügt `PartnerId1` und `PartnerId2`. Diese Spalten enthalten kodierte Benutzer-IDs, die für jedes Unternehmen gelten, das diese Dateien erhält.

   Als autorisierter Drittanbieter [!DNL Audience Manager] können DCM-Daten empfangen, die IDs jedoch nicht dekodieren. Auf der [!DNL Audience Manager] Seite wissen wir jedoch, wie die kodierten IDs mit unseren IDs übereinstimmen. Dies bedeutet, dass wir Benutzer mit Sicherheit und Genauigkeit abgleichen und synchronisieren können.

   >[!NOTE]
   >Sie können keine DCM-Dateien in importieren, [!DNL Audience Manager] wenn Sie bereits Daten mit zwei anderen Drittanbieterpartnern teilen.

1. Laden Sie [!DNL Audience Manager] zur Gruppe ein.

   Nachdem Sie eine Gruppe erstellt haben und ihr Zugriff auf eine Datenmenge gewährt haben, laden Sie sie ein, [!DNL Audience Manager] der Gruppe beizutreten. Senden Sie eine Einladungs-E-Mail an DFA-AAM@adobe.com. Stellen Sie sicher, dass Sie die Datendatei-URL aus Schritt 3 einschließen. Unsere internen Teams arbeiten mit Ihnen zusammen, um den Zugriff nach Annahme der Einladung zu überprüfen. 1. Richten Sie zwei Datenquellen für DCM-Daten in der [!DNL Audience Manager] Benutzeroberfläche ein.

   Benennen Sie die Datenquellen `Advertiser Analytics: DCM Platform` und `Advertiser Analytics: AAM+DCM Platform`. Legen Sie im Arbeitsablauf [Datenquellen](../../../features/manage-datasources.md#create-data-source) erstellen den ID-Typ auf `Cookie`. Geben Sie die IDs der beiden neuen Datenquellen für unsere internen Teams frei.

1. Sie können Eigenschaften ganz einfach aus den DCM-Dateien erstellen, in die Sie importieren [!DNL Audience Manager]. Siehe [Akzeptable Protokolldateien](../../../integration/media-data-integration/actionable-log-files.md) und bitten Sie Ihren [!DNL Audience Manager] Berater oder Kundendienst, die Funktion für Sie zu aktivieren.

---
description: Richten Sie eine Google-Gruppe ein, um Ihre Google Kampagne Manager-Datendateien in Audience Manager zu bringen. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und enthält Links zu Google Kampagne Manager-Ressourcen, die Ihnen beim Einstieg helfen.
seo-description: Richten Sie eine Google-Gruppe ein, um Ihre Google Kampagne Manager-Datendateien in Audience Manager zu bringen. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und enthält Links zu Google Kampagne Manager-Ressourcen, die Ihnen beim Einstieg helfen.
seo-title: Google Kampagne Manager-Datendateien in Audience Manager importieren
solution: Audience Manager
title: Google Kampagne Manager-Datendateien in Audience Manager importieren
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 3%

---


# Google Kampagne Manager-Datendateien in Audience Manager importieren {#import-dcm-data-files-into-audience-manager}

Richten Sie eine [!DNL Google] Gruppe ein, um Ihre [!DNL Google Campaign Manager] Datendateien in den Audience Manager zu laden. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und enthält Links zu [!DNL Google Campaign Manager] Ressourcen, die Ihnen beim Einstieg helfen.

## Integrationszusammenfassung

[!DNL Google Campaign Manager] [!DNL Google]&#39;s ersetzt [!DNL DoubleClick for Advertisers] (DFA). Similar to DFA, [!DNL Google Campaign Manager] customers can import, view, and work with their data in [!DNL Audience Manager]. Sie [!DNL Audience Manager] können jedoch nicht direkt auf Ihre [!UICONTROL Data Transfer] und Ihre [!UICONTROL Match Table] Dateien zugreifen und diese importieren. Den Import dieser Dateien muss der Kunde selbst übernehmen.

Das Einrichtungsverfahren ist jedoch in der [DoubleClick Kampagne Manager-Hilfe](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)gut dokumentiert. Außerdem können Sie die unten aufgeführten Schritte überprüfen, um zu beginnen.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] Datendateien enthalten Daten für alle Ihre Advertiser oder Kunden. Wenn Sie bestimmte Clients auslassen müssen, müssen Sie die Dateien bearbeiten, bevor Sie sie verfügbar machen [!DNL Audience Manager].

## Häufigkeit und Verfügbarkeit der Datenübertragung

[!DNL Audience Manager] überprüft und überträgt Daten einmal täglich. Die Daten sind in der Regel nach [!DNL Audience Manager] 24 Stunden verfügbar.

## Schritte

1. [Eine Gruppe erstellen](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Gruppen steuern den Zugriff auf Ihre [!DNL Google Campaign Manager] Daten. Schließlich laden Sie diese Gruppe ein und fügen sie [!DNL Audience Manager] hinzu.

1. [Überprüfen Sie den Status](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)Ihrer Google Cloud-Datenspeicherung.

   Die Google Cloud-Datenspeicherung enthält den Datenbehälter, in dem sich Ihr [!UICONTROL Data Transfer] und [!UICONTROL Match Tables]. Sie müssen einen Behälter einrichten oder sicherstellen, dass Ihre neue Datenspeicherung Zugriff auf einen vorhandenen Datenbehälter hat.

1. [Abrufen einer Datendatei-URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Wenden Sie sich an Ihren [!DNL Google Campaign Manager] Kundenbetreuer oder Platform Solutions Consultant. Sie erhalten eine URL zu Ihren Datendateien. [!DNL Google] kann das Format für Behälter- und Dateinamen in zukünftigen Versionen ändern. Wenden Sie sich erneut an Ihren [!DNL Google Campaign Manager] Kundenbetreuer, um sicherzustellen, dass Sie die richtigen Formate verwenden.

1. [Legen Sie Behälterberechtigungen](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)fest.

   Mit der [!DNL Cloud Storage Manager] können Sie die Datenfreigabe und den Behälterzugriff steuern. Erteilen Sie Ihrer Gruppe Lesezugriff auf den Behälter, der Ihre [!UICONTROL Data Transfer] und [!UICONTROL Match Table] Dateien enthält.

1. [Richten Sie die Datenfreigabe](https://support.google.com/dcm/partner/answer/6206106?hl=en)ein.

   Freigegebene [!DNL Google Campaign Manager] Benutzer-IDs werden zum Schutz der Privatsphäre verschlüsselt. Mit der Verschlüsselung werden am Ende der Datenübertragungsdatei zwei Spalten hinzugefügt `PartnerId1` und `PartnerId2`. Diese Spalten enthalten kodierte Benutzer-IDs, die für jede Firma, die diese Dateien erhält, spezifisch sind.

   Als autorisierter Drittanbieter [!DNL Audience Manager] können Daten empfangen, [!DNL Google Campaign Manager] die IDs jedoch nicht dekodieren. Auf der [!DNL Audience Manager] Seite wissen wir jedoch, wie die kodierten IDs mit unseren IDs übereinstimmen. Dies bedeutet, dass wir Benutzer mit Sicherheit und Genauigkeit abgleichen und synchronisieren können.

   >[!NOTE]
   >Sie können keine [!DNL Google Campaign Manager] Dateien in importieren, [!DNL Audience Manager] wenn Sie bereits Daten mit zwei Drittanbieterpartnern teilen.

1. Laden Sie [!DNL Audience Manager] zur Gruppe ein.

   Nachdem Sie eine Gruppe erstellt haben und ihr Zugriff auf eine Datenmenge gewährt haben, laden Sie sie ein, [!DNL Audience Manager] der Gruppe beizutreten. Senden Sie eine Einladungs-E-Mail an DFA-AAM@adobe.com. Stellen Sie sicher, dass Sie die Datendatei-URL aus Schritt 3 einschließen. Unsere internen Teams arbeiten mit Ihnen zusammen, um den Zugriff nach Annahme der Einladung zu überprüfen. 1. Richten Sie zwei Datenquellen für [!DNL Google Campaign Manager] Daten in der [!DNL Audience Manager] Benutzeroberfläche ein.

   Benennen Sie die Datenquellen `Advertiser Analytics: DCM Platform` und `Advertiser Analytics: AAM+DCM Platform`. Legen Sie im Arbeitsablauf [Datenquellen](../../../features/manage-datasources.md#create-data-source) erstellen den ID-Typ auf `Cookie`. Geben Sie die IDs der beiden neuen Datenquellen für unsere internen Teams frei.

1. Sie können Eigenschaften ganz einfach aus den [!DNL Google Campaign Manager] Dateien erstellen, in die Sie importieren [!DNL Audience Manager]. Siehe [Akzeptable Protokolldateien](../../../integration/media-data-integration/actionable-log-files.md) und bitten Sie Ihren [!DNL Audience Manager] Berater oder Kundendienst, die Funktion für Sie zu aktivieren.

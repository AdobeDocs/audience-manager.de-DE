---
description: Richten Sie eine Google-Gruppe ein, um Ihre Google Campaign Manager-Datendateien in Audience Manager zu laden. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und bietet Links zu Google Campaign Manager-Ressourcen, die Ihnen bei den ersten Schritten helfen.
seo-description: Richten Sie eine Google-Gruppe ein, um Ihre Google Campaign Manager-Datendateien in Audience Manager zu laden. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und bietet Links zu Google Campaign Manager-Ressourcen, die Ihnen bei den ersten Schritten helfen.
seo-title: Importieren von Google Kampagne Manager-Datendateien in Audience Manager
solution: Audience Manager
title: Importieren von Google Kampagne Manager-Datendateien in Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Berichte zur Zielgruppenoptimierung
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 7%

---

# Importieren von Google Kampagne Manager-Datendateien in Audience Manager {#import-dcm-data-files-into-audience-manager}

Richten Sie eine [!DNL Google]-Gruppe ein, um Ihre [!DNL Google Campaign Manager]-Datendateien in den Audience Manager zu bringen. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und bietet Ihnen Links zu [!DNL Google Campaign Manager] Ressourcen, die Ihnen bei den ersten Schritten helfen.

## Integrationszusammenfassung

[!DNL Google Campaign Manager] [!DNL Google]&#39;s ersetzt [!DNL DoubleClick for Advertisers] (DFA). Ähnlich wie bei DFA können [!DNL Google Campaign Manager] -Kunden ihre Daten in [!DNL Audience Manager] importieren, anzeigen und damit arbeiten. [!DNL Audience Manager] kann jedoch nicht direkt auf Ihre [!UICONTROL Data Transfer]- und [!UICONTROL Match Table]-Dateien zugreifen und diese importieren. Den Import dieser Dateien muss der Kunde selbst übernehmen.

Das Einrichtungsverfahren ist jedoch in der [DoubleClick Campaign Manager-Hilfe](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456) gut dokumentiert. Außerdem können Sie die unten aufgeführten Schritte zum Einstieg durchsehen.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] -Datendateien enthalten Daten für alle Ihre Advertiser oder Kunden. Wenn Sie bestimmte Clients weglassen müssen, müssen Sie die Dateien bearbeiten, bevor Sie sie für [!DNL Audience Manager] verfügbar machen.

## Häufigkeit und Verfügbarkeit der Datenübertragung

[!DNL Audience Manager] prüft und überträgt Daten einmal täglich. Daten sind in der Regel nach 24 Stunden in [!DNL Audience Manager] verfügbar.

## Schritte

1. [Eine Gruppe erstellen](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Gruppen steuern den Zugriff auf Ihre [!DNL Google Campaign Manager]-Daten. Schließlich laden Sie [!DNL Audience Manager] zu dieser Gruppe ein und fügen Sie sie hinzu.

1. [Überprüfen Sie Ihren Google Cloud-Speicherstatus](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud Storage enthält den Datenbehälter, der Ihre [!UICONTROL Data Transfer] und [!UICONTROL Match Tables] enthält. Sie müssen einen Behälter einrichten oder sicherstellen, dass Ihre neue Gruppe Zugriff auf einen vorhandenen Datenspeicherbehälter hat.

1. [Rufen Sie eine Datendatei-URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456) ab.

   Arbeiten Sie mit Ihrem [!DNL Google Campaign Manager] Kundenbetreuer oder Platform Solutions-Berater zusammen. Sie erhalten eine URL zu Ihren Datendateien. [!DNL Google] kann das Format für Bucket- und Dateinamen in zukünftigen Versionen ändern. Arbeiten Sie wiederum mit Ihrem [!DNL Google Campaign Manager] Kundenbetreuer zusammen, um sicherzustellen, dass Sie die richtigen Formate verwenden.

1. [Legen Sie Bucket-Berechtigungen](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission) fest.

   Mit [!DNL Cloud Storage Manager] können Sie die Datenfreigabe und den Behälterzugriff steuern. Geben Sie Ihrer Gruppe Lesezugriff auf den Bucket, der Ihre [!UICONTROL Data Transfer]- und [!UICONTROL Match Table]-Dateien enthält.

1. [Datenfreigabe einrichten](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Freigegebene [!DNL Google Campaign Manager] Benutzer-IDs werden zum Schutz der Privatsphäre verschlüsselt. Durch die Verschlüsselung werden am Ende Ihrer Datenübertragungsdatei zwei Spalten hinzugefügt: `PartnerId1` und `PartnerId2`. Diese Spalten enthalten kodierte Benutzer-IDs, die für jedes Unternehmen spezifisch sind, das diese Dateien erhält.

   Als autorisierter Drittanbieter kann [!DNL Audience Manager] [!DNL Google Campaign Manager] -Daten empfangen, die IDs jedoch nicht dekodieren. Auf der Seite [!DNL Audience Manager] wissen wir jedoch, wie die kodierten IDs mit unseren IDs übereinstimmen. Dies bedeutet, dass wir Benutzer mit Konfidenz und Genauigkeit abgleichen und synchronisieren können.

   >[!NOTE]
   >Sie können [!DNL Google Campaign Manager]-Dateien nicht in [!DNL Audience Manager] importieren, wenn Sie bereits Daten mit zwei anderen Drittanbieterpartnern teilen.

1. Laden Sie [!DNL Audience Manager] ein, um der Gruppe beizutreten.

   Nachdem Sie eine Gruppe erstellt und ihr Zugriff auf einen Datenbehälter gewährt haben, laden Sie [!DNL Audience Manager] ein, der Gruppe beizutreten. Senden Sie eine Einladungs-E-Mail an DFA-AAM@adobe.com. Stellen Sie sicher, dass Sie die URL der Datendatei aus Schritt 3 einschließen. Unsere internen Teams arbeiten mit Ihnen zusammen, um den Zugriff nach Annahme der Einladung zu überprüfen. 1. Richten Sie zwei Datenquellen für [!DNL Google Campaign Manager]-Daten in der [!DNL Audience Manager]-Benutzeroberfläche ein.

   Nennen Sie die Datenquellen `Advertiser Analytics: DCM Platform` und `Advertiser Analytics: AAM+DCM Platform`. Legen Sie im Workflow [Data Sources erstellen](../../../features/manage-datasources.md#create-data-source) den ID-Typ auf `Cookie` fest. Geben Sie die IDs der beiden neuen Datenquellen für unsere internen Teams frei.

1. Sie können Eigenschaften einfach aus den [!DNL Google Campaign Manager]-Dateien erstellen, die Sie in [!DNL Audience Manager] importieren. Siehe [Ausführbare Protokolldateien](../../../integration/media-data-integration/actionable-log-files.md) und bitten Sie Ihren [!DNL Audience Manager]-Berater oder die Kundenunterstützung, die Funktion für Sie zu aktivieren.

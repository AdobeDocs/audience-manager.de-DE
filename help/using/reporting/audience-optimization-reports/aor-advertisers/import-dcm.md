---
description: Richten Sie eine Google-Gruppe ein, um Ihre Google Campaign Manager-Datendateien in Audience Manager zu laden. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und bietet Links zu Google Campaign Manager-Ressourcen, die Ihnen bei den ersten Schritten helfen.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importieren von Google Campaign Manager-Datendateien in Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# Importieren von Google Campaign Manager-Datendateien in Audience Manager {#import-dcm-data-files-into-audience-manager}

Richten Sie eine [!DNL Google] -Gruppe ein, um Ihre [!DNL Google Campaign Manager] -Datendateien in den Audience Manager zu laden. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und stellt Ihnen Links zu [!DNL Google Campaign Manager] -Ressourcen bereit, die Ihnen bei den ersten Schritten helfen.

## Integrationszusammenfassung

[!DNL Google Campaign Manager] ist der Ersatz von [!DNL Google] für [!DNL DoubleClick for Advertisers] (DFA). Ähnlich wie bei DFA können [!DNL Google Campaign Manager] -Kunden ihre Daten in [!DNL Audience Manager] importieren, anzeigen und damit arbeiten. [!DNL Audience Manager] kann jedoch nicht direkt auf Ihre [!UICONTROL Data Transfer] - und [!UICONTROL Match Table] -Dateien zugreifen und diese importieren. Den Import dieser Dateien muss der Kunde selbst übernehmen.

Das Einrichtungsverfahren ist jedoch in der [DoubleClick Campaign Manager-Hilfe](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456) gut dokumentiert. Außerdem können Sie die unten aufgeführten Schritte durchsehen, um zu beginnen.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] -Datendateien enthalten Daten für alle Ihre Advertiser oder Kunden. Wenn Sie bestimmte Clients weglassen müssen, müssen Sie die Dateien bearbeiten, bevor Sie sie für [!DNL Audience Manager] verfügbar machen.

## Häufigkeit und Verfügbarkeit der Datenübertragung

[!DNL Audience Manager] prüft und überträgt Daten einmal täglich. Daten sind in der Regel in [!DNL Audience Manager] nach 24 Stunden verfügbar.

## Schritte

1. [Erstellen Sie eine Gruppe](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Gruppen steuern den Zugriff auf Ihre [!DNL Google Campaign Manager] -Daten. Schließlich laden Sie diese Gruppe ein und fügen [!DNL Audience Manager] hinzu.

1. [Überprüfen Sie Ihren Google Cloud-Speicherstatus](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud Storage enthält den Datenbehälter , der Ihre [!UICONTROL Data Transfer] und Ihre [!UICONTROL Match Tables] enthält. Sie müssen einen Behälter einrichten oder sicherstellen, dass Ihre neue Gruppe Zugriff auf einen vorhandenen Datenspeicherbehälter hat.

1. [Rufen Sie eine Datendatei-URL ab](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Arbeiten Sie mit Ihrem [!DNL Google Campaign Manager] -Kundenbetreuer oder Platform Solutions-Berater zusammen. Sie erhalten eine URL zu Ihren Datendateien. [!DNL Google] kann das Format für Bucket- und Dateinamen in zukünftigen Versionen ändern. Arbeiten Sie wiederum mit Ihrem [!DNL Google Campaign Manager] -Kundenbetreuer zusammen, um sicherzustellen, dass Sie die richtigen Formate verwenden.

1. [Legen Sie Bucket-Berechtigungen fest](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   Mit dem [!DNL Cloud Storage Manager] können Sie die Datenfreigabe und den Behälterzugriff steuern. Gewähren Sie Ihrer Gruppe Lesezugriff auf den Bucket, der Ihre [!UICONTROL Data Transfer] - und [!UICONTROL Match Table] -Dateien enthält.

1. [Richten Sie die Datenfreigabe ein](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Freigegebene [!DNL Google Campaign Manager] Benutzer-IDs werden zum Schutz der Privatsphäre verschlüsselt. Durch die Verschlüsselung werden am Ende Ihrer Datenübertragungsdatei zwei Spalten hinzugefügt: `PartnerId1` und `PartnerId2`. Diese Spalten enthalten kodierte Benutzer-IDs, die für jedes Unternehmen spezifisch sind, das diese Dateien erhält.

   Als autorisierter Drittanbieter kann [!DNL Audience Manager] [!DNL Google Campaign Manager] -Daten empfangen, die IDs jedoch nicht dekodieren. Auf der Seite [!DNL Audience Manager] wissen wir jedoch, wie die kodierten IDs mit unseren IDs übereinstimmen. Dies bedeutet, dass wir Benutzer mit Konfidenz und Genauigkeit synchronisieren können.

   >[!NOTE]
   >Sie können [!DNL Google Campaign Manager] -Dateien nicht in [!DNL Audience Manager] importieren, wenn Sie bereits Daten mit zwei anderen Drittanbieterpartnern teilen.

1. Laden Sie [!DNL Audience Manager] ein, um der Gruppe beizutreten.

   Nachdem Sie eine Gruppe erstellt und ihr Zugriff auf einen Datenbehälter gewährt haben, laden Sie [!DNL Audience Manager] ein, der Gruppe beizutreten. Senden Sie eine Einladungs-E-Mail an dfaaam@adobe.com. Stellen Sie sicher, dass Sie die URL der Datendatei aus Schritt 3 einschließen. Unsere internen Teams arbeiten mit Ihnen zusammen, um den Zugriff nach Annahme der Einladung zu überprüfen. 1. Richten Sie zwei Datenquellen für [!DNL Google Campaign Manager] -Daten in der [!DNL Audience Manager]-Benutzeroberfläche ein.

   Nennen Sie die Datenquellen &quot;`Advertiser Analytics: DCM Platform`&quot; und &quot;`Advertiser Analytics: AAM+DCM Platform`&quot;. Setzen Sie im Workflow [Data Sources erstellen](../../../features/manage-datasources.md#create-data-source) den ID-Typ auf `Cookie`. Geben Sie die IDs der beiden neuen Datenquellen für unsere internen Teams frei.

1. Sie können Eigenschaften einfach aus den [!DNL Google Campaign Manager] -Dateien erstellen, die Sie in [!DNL Audience Manager] importieren. Siehe [Ausführbare Protokolldateien](../../../integration/media-data-integration/actionable-log-files.md) und bitten Sie Ihren [!DNL Audience Manager] -Berater oder die Kundenunterstützung, die Funktion für Sie zu aktivieren.

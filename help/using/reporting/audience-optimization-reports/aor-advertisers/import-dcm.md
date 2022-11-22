---
description: Richten Sie eine Google-Gruppe ein, um Ihre Google Campaign Manager-Datendateien in Audience Manager zu laden. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und bietet Links zu Google Campaign Manager-Ressourcen, die Ihnen bei den ersten Schritten helfen.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importieren von Google Kampagne Manager-Datendateien in Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 6%

---

# Importieren von Google Kampagne Manager-Datendateien in Audience Manager {#import-dcm-data-files-into-audience-manager}

Richten Sie eine [!DNL Google] -Gruppe, um Ihre [!DNL Google Campaign Manager] Datendateien in Audience Manager. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und stellt Links zu [!DNL Google Campaign Manager] Ressourcen, die Ihnen bei den ersten Schritten helfen.

## Integrationszusammenfassung

[!DNL Google Campaign Manager] [!DNL Google]&#39;s ersetzt [!DNL DoubleClick for Advertisers] (DFA). Ähnlich wie DFA [!DNL Google Campaign Manager] -Kunden können ihre Daten in [!DNL Audience Manager]. Aber [!DNL Audience Manager] kann nicht direkt auf Ihre [!UICONTROL Data Transfer] und [!UICONTROL Match Table] Dateien. Den Import dieser Dateien muss der Kunde selbst übernehmen.

Das Einrichtungsverfahren ist jedoch gut dokumentiert im [Hilfe zu DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Außerdem können Sie die unten aufgeführten Schritte zum Einstieg durchsehen.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] -Datendateien enthalten Daten für alle Ihre Advertiser oder Kunden. Wenn Sie bestimmte Clients weglassen müssen, müssen Sie die Dateien bearbeiten, bevor Sie sie für [!DNL Audience Manager].

## Häufigkeit und Verfügbarkeit der Datenübertragung

[!DNL Audience Manager] prüft und überträgt Daten einmal täglich. Daten sind in der Regel verfügbar unter [!DNL Audience Manager] nach 24 Stunden.

## Schritte

1. [Eine Gruppe erstellen](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Gruppen steuern den Zugriff auf Ihre [!DNL Google Campaign Manager] Daten. Schließlich laden Sie ein und fügen [!DNL Audience Manager] zu dieser Gruppe hinzu.

1. [Überprüfen des Google Cloud-Speicherstatus](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Der Google Cloud-Speicher enthält den Datenbehälter , der Ihre [!UICONTROL Data Transfer] und [!UICONTROL Match Tables]. Sie müssen einen Behälter einrichten oder sicherstellen, dass Ihre neue Gruppe Zugriff auf einen vorhandenen Datenspeicherbehälter hat.

1. [Datendatei-URL abrufen](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Arbeiten mit [!DNL Google Campaign Manager] Kundenbetreuer oder Platform Solutions-Berater. Sie erhalten eine URL zu Ihren Datendateien. [!DNL Google] kann das Format für Bucket- und Dateinamen in zukünftigen Versionen ändern. Arbeiten Sie erneut mit Ihrem [!DNL Google Campaign Manager] Kundenbetreuer , um sicherzustellen, dass Sie die richtigen Formate verwenden.

1. [Bucket-Berechtigungen festlegen](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   Die [!DNL Cloud Storage Manager] ermöglicht die Steuerung der Datenfreigabe und des Behälterzugriffs. Gewähren Sie Ihrer Gruppe Lesezugriff auf den Behälter, der Ihre [!UICONTROL Data Transfer] und [!UICONTROL Match Table] Dateien.

1. [Datenfreigabe einrichten](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Freigegeben [!DNL Google Campaign Manager] Benutzer-IDs werden zum Schutz der Privatsphäre verschlüsselt. Durch die Verschlüsselung werden am Ende Ihrer Datenübertragungsdatei 2 Spalten hinzugefügt. `PartnerId1` und `PartnerId2`. Diese Spalten enthalten kodierte Benutzer-IDs, die für jedes Unternehmen spezifisch sind, das diese Dateien erhält.

   Als autorisierter Dritter [!DNL Audience Manager] empfangen [!DNL Google Campaign Manager] -Daten, können die IDs jedoch nicht dekodieren. Im [!DNL Audience Manager] enthalten ist, wissen wir, wie die kodierten IDs mit unseren IDs übereinstimmen. Dies bedeutet, dass wir Benutzer mit Konfidenz und Genauigkeit abgleichen und synchronisieren können.

   >[!NOTE]
   >Import nicht möglich [!DNL Google Campaign Manager] Dateien in [!DNL Audience Manager] wenn Sie bereits Daten mit zwei anderen Drittanbieterpartnern teilen.

1. Einladen [!DNL Audience Manager] , um der Gruppe beizutreten.

   Nachdem Sie eine Gruppe erstellt und ihr Zugriff auf einen Datenbehälter gewährt haben, laden Sie [!DNL Audience Manager] , um der Gruppe beizutreten. Senden Sie eine Einladungs-E-Mail an dfaaam@adobe.com. Stellen Sie sicher, dass Sie die URL der Datendatei aus Schritt 3 einschließen. Unsere internen Teams arbeiten mit Ihnen zusammen, um den Zugriff nach Annahme der Einladung zu überprüfen. 1. Einrichten von zwei Datenquellen für [!DNL Google Campaign Manager] Daten in der [!DNL Audience Manager] Benutzeroberfläche.

   Benennen Sie die Datenquellen. `Advertiser Analytics: DCM Platform` und `Advertiser Analytics: AAM+DCM Platform`. Im [Data Sources erstellen](../../../features/manage-datasources.md#create-data-source) workflow, setzen Sie den ID-Typ auf `Cookie`. Geben Sie die IDs der beiden neuen Datenquellen für unsere internen Teams frei.

1. Sie können Eigenschaften einfach über die [!DNL Google Campaign Manager] Dateien, die in importiert werden [!DNL Audience Manager]. Siehe [Ausführbare Protokolldateien](../../../integration/media-data-integration/actionable-log-files.md) und fragen Sie [!DNL Audience Manager] Berater oder Kundenunterstützung , um die Funktion für Sie zu aktivieren.

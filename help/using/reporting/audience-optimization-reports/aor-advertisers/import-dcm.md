---
description: Richten Sie eine Google-Gruppe ein, um Ihre Google Campaign Manager-Datendateien in den Audience Manager zu übernehmen. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und enthält Links zu Google Campaign Manager-Ressourcen, die Ihnen bei den ersten Schritten helfen.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importieren von Google Campaign Manager-Datendateien in Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: d86769304b03161490d0c3d9eb340cee64d52034
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# Importieren von Google Campaign Manager-Datendateien in Audience Manager {#import-dcm-data-files-into-audience-manager}

Richten Sie eine [!DNL Google] ein, um Ihre [!DNL Google Campaign Manager] Datendateien in den Audience Manager zu übernehmen. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und enthält Links zu [!DNL Google Campaign Manager] Ressourcen, die Ihnen bei den ersten Schritten helfen.

## Zusammenfassung der Integration

[!DNL Google Campaign Manager] ist [!DNL Google] Ersatz für [!DNL DoubleClick for Advertisers] (DFA). Ähnlich wie bei DFA können [!DNL Google Campaign Manager] Kunden ihre Daten in [!DNL Audience Manager] importieren, anzeigen und mit ihnen arbeiten. [!DNL Audience Manager] können jedoch nicht direkt auf Ihre [!UICONTROL Data Transfer]- und [!UICONTROL Match Table]-Dateien zugreifen und diese importieren. Den Import dieser Dateien muss der Kunde selbst übernehmen.

Der Einrichtungsprozess wird jedoch in der „DoubleClick Campaign [Manager-Hilfe“ gut ](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Außerdem können Sie sich die unten aufgeführten Schritte ansehen, um loszulegen.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] Datendateien enthalten Daten für alle Ihre Werbetreibenden oder Kunden. Wenn Sie bestimmte Clients weglassen müssen, müssen Sie die Dateien bearbeiten, bevor Sie sie für [!DNL Audience Manager] verfügbar machen.

## Häufigkeit und Verfügbarkeit der Datenübertragung

[!DNL Audience Manager] sucht und überträgt Daten einmal täglich. Die Daten sind in der Regel nach 24 Stunden in [!DNL Audience Manager] verfügbar.

## Schritte

1. [Erstellen einer Gruppe](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Gruppen steuern den Zugriff auf Ihre [!DNL Google Campaign Manager]. Schließlich werden Sie [!DNL Audience Manager] zu dieser Gruppe einladen und hinzufügen.

1. [Überprüfen des Google Cloud-Speicherstatus](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Der Google-Cloud-Speicher enthält den Daten-Bucket, der Ihre [!UICONTROL Data Transfer] und [!UICONTROL Match Tables] enthält. Sie müssen einen Bucket einrichten oder sicherstellen, dass Ihre neue Gruppe Zugriff auf einen vorhandenen Datenspeicher-Bucket hat.

1. [Abrufen einer Datendatei-URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Arbeiten Sie mit Ihrem [!DNL Google Campaign Manager] Account Manager oder Platform Solutions Consultant zusammen. Sie geben Ihnen eine URL zu Ihren Datendateien. [!DNL Google] können das Format für Bucket- und Dateinamen in zukünftigen Versionen ändern. Wenden Sie sich erneut an Ihren [!DNL Google Campaign Manager] Account Manager, um sicherzustellen, dass Sie die richtigen Formate verwenden.

1. [Bucket-Berechtigungen ](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   Mit dem [!DNL Cloud Storage Manager] können Sie die Datenfreigabe und den Bucket-Zugriff steuern. Erteilen Sie Ihrer Gruppe Lesezugriff auf den Bucket, der Ihre [!UICONTROL Data Transfer]- und [!UICONTROL Match Table] enthält.

1. [Einrichten der Datenfreigabe](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Die Benutzer-IDs für freigegebene [!DNL Google Campaign Manager] werden zum Schutz der Privatsphäre verschlüsselt. Die Verschlüsselung fügt am Ende der Datenübertragungsdatei zwei Spalten hinzu, `PartnerId1` und `PartnerId2`. Diese Spalten enthalten kodierte Benutzer-IDs, die für jedes Unternehmen spezifisch sind, das diese Dateien erhält.

   Als autorisierter Drittanbieter können [!DNL Audience Manager] [!DNL Google Campaign Manager] empfangen, die IDs jedoch nicht decodieren. Auf der [!DNL Audience Manager] Seite wissen wir jedoch, wie die kodierten IDs mit unseren IDs übereinstimmen. Dies bedeutet, dass wir Benutzer mit Konfidenz und Genauigkeit abgleichen und synchronisieren können.

   >[!NOTE]
   >Sie können keine [!DNL Google Campaign Manager]-Dateien in [!DNL Audience Manager] importieren, wenn Sie bereits Daten mit zwei anderen Drittanbieterpartnern teilen.

1. Laden Sie [!DNL Audience Manager] ein, der Gruppe beizutreten.

   Nachdem Sie eine Gruppe erstellt und ihr Zugriff auf einen Daten-Bucket gewährt haben, laden Sie [!DNL Audience Manager] ein, der Gruppe beizutreten. Senden Sie eine Einladungs-E-Mail an dfaaam@adobe.com. Stellen Sie sicher, dass Sie die Datendatei-URL aus Schritt 3 einbeziehen. Unsere internen Teams werden mit Ihnen zusammenarbeiten, um den Zugriff zu überprüfen, nachdem Sie die Einladung angenommen haben. 1. Richten Sie zwei Datenquellen für die [!DNL Google Campaign Manager] von Daten in der [!DNL Audience Manager]-Benutzeroberfläche ein.

   Benennen Sie die Datenquellen `Advertiser Analytics: DCM Platform` und `Advertiser Analytics: AAM+DCM Platform`. Legen [ im Workflow „Datenquellen erstellen](../../../features/manage-datasources.md#create-data-source) den ID-Typ auf `Cookie` fest. Geben Sie die IDs der beiden neuen Datenquellen für unsere internen Teams frei.

1. Aus den [!DNL Google Campaign Manager] Dateien, die Sie in [!DNL Audience Manager] importieren, können Sie auf einfache Weise Eigenschaften erstellen. Siehe [Verwertbare Protokolldateien](../../../integration/media-data-integration/actionable-log-files.md) und bitten Sie Ihren [!DNL Audience Manager] oder die Kundenunterstützung, die Funktion für Sie zu aktivieren.

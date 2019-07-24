---
description: Richten Sie eine Google-Gruppe ein, um Ihre doubleclick Campaign Manager (DCM) Datendateien in Audience Manager zu übertragen. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und stellt Links zu den DCM-Ressourcen bereit, die Ihnen bei der Einstieg helfen.
seo-description: Richten Sie eine Google-Gruppe ein, um Ihre doubleclick Campaign Manager (DCM) Datendateien in Audience Manager zu übertragen. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und stellt Links zu den DCM-Ressourcen bereit, die Ihnen bei der Einstieg helfen.
seo-title: DCM-Datendateien in Audience Manager importieren
solution: Audience Manager
title: DCM-Datendateien in Audience Manager importieren
uuid: 3578 cfe 1-6 d 30-4 a 73-ab 75-8 d 272 bebcd 60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

Richten Sie eine Google-Gruppe ein, um Ihre doubleclick Campaign Manager (DCM) Datendateien in Audience Manager zu übertragen. Der Inhalt in diesem Abschnitt fasst den Integrationsprozess zusammen und stellt Links zu den DCM-Ressourcen bereit, die Ihnen bei der Einstieg helfen.

## Integrationszusammenfassung

DCM [!DNL Google]'s ersetzt[!DNL DoubleClick for Advertisers] (DFA). Ähnlich wie bei DFA können DCM-Kunden ihre Daten in [!DNL Audience Manager] importieren, ansehen und verwenden. But [!DNL Audience Manager] cannot directly access and import your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. Den Import dieser Dateien muss der Kunde selbst übernehmen.

However, the set up procedure is well documented in the [DoubleClick Campaign Manager Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). Außerdem können Sie die unten aufgeführten Schritte überprüfen.

>[!CAUTION]
>
>DCM-Datendateien enthalten Daten für alle Ihre Werbetreibenden oder Kunden. If you need to omit specific clients, then you must edit the files before making them available to [!DNL Audience Manager].

## Häufigkeit und Verfügbarkeit von Datenübertragungen

[!DNL Audience Manager] prüft und überträgt Daten einmal täglich. Data is usually available in [!DNL Audience Manager] after 24-hours.

## Schritte

1. [Eine Gruppe erstellen](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Gruppen steuern den Zugriff auf Ihre DCM-Daten. Eventually, you'll invite and add [!DNL Audience Manager] to this group.

1. [Überprüfen Sie Ihren Google Cloud Speicherstatus](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud Storage contains the data bucket that holds your [!UICONTROL Data Transfer] and [!UICONTROL Match Tables]. Sie müssen einen Behälter einrichten oder sicherstellen, dass Ihre neue Gruppe Zugriff auf einen vorhandenen Datenspeicher-Behälter hat.

1. [Eine Datendatei-URL abrufen](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   Arbeiten Sie mit Ihrem DCM-Kundenbetreuer oder Plattformlösungsberater zusammen. Sie stellen Ihnen eine URL für Ihre Datendateien bereit. [!DNL Google] kann das Format für Behälter und Dateinamen in zukünftigen Versionen ändern. Arbeiten Sie erneut mit Ihrem DCM-Kundenbetreuer, um sicherzustellen, dass Sie die richtigen Formate verwenden.

1. [Legen Sie die Behälterberechtigungen](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)fest.

   The [!DNL Cloud Storage Manager] lets you control data sharing and bucket access. Give your group read access to the bucket that contains your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files.

1. [Richten Sie die Datenfreigabe](https://support.google.com/dcm/partner/answer/6206106?hl=en)ein.

   Freigegebene DCM-Benutzer-IDs werden verschlüsselt, um den Datenschutz zu schützen. Encryption adds 2 columns to the end of your Data Transfer file, `PartnerId1` and `PartnerId2`. Diese Spalten enthalten kodierte Benutzer-IDs, die für jedes Unternehmen gelten, das diese Dateien erhält.

   [!DNL Audience Manager] Kann als autorisierter Drittanbieter DCM-Daten erhalten, kann die IDs aber nicht dekodieren. However, on the [!DNL Audience Manager] side, we know how the encoded IDs match our IDs. Dies bedeutet, dass wir Benutzer mit Vertrauen und Genauigkeit übereinstimmen und synchronisieren können.

   >[!NOTE]
   >You cannot import DCM files into [!DNL Audience Manager] if you're already sharing data with 2 other third-party partners.

1. Invite [!DNL Audience Manager] to join the group.

   After you create a group and give it access to a data bucket, invite [!DNL Audience Manager] to join the group. Senden Sie eine Einladungs-E-Mail an DFA-AAM@adobe.com. Achten Sie darauf, die Datendatei-URL aus Schritt 3 einzuschließen. Unsere internen Teams werden mit Ihnen zusammenarbeiten, um den Zugriff nach Annahme der Einladung zu bestätigen. 1. Set up two data sources for DCM data in the [!DNL Audience Manager] User Interface.

   Name the data sources `Advertiser Analytics: DCM Platform` and `Advertiser Analytics: AAM+DCM Platform`. In the [Create Data Sources](../../../features/manage-datasources.md#create-data-source) workflow, set the ID type to `Cookie`. Geben Sie die IDs der beiden neuen Datenquellen für unsere internen Teams frei.

1. You can easily create traits from the DCM files you import into [!DNL Audience Manager]. See [Actionable Log Files](../../../integration/media-data-integration/actionable-log-files.md) and ask your [!DNL Audience Manager] consultant or Customer Care to enable the feature for you.

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

DCM [!DNL Google]&#39;s ersetzt[!DNL DoubleClick for Advertisers] (DFA). Ähnlich wie bei DFA können DCM-Kunden ihre Daten in [!DNL Audience Manager] importieren, ansehen und verwenden. Sie können jedoch [!DNL Audience Manager] nicht direkt auf Ihre [!UICONTROL Data Transfer] und [!UICONTROL Match Table] Dateien zugreifen und diese importieren. Den Import dieser Dateien muss der Kunde selbst übernehmen.

Das eingerichtete Verfahren wird jedoch in der [doubleclick Campaign Manager-Hilfe gut dokumentiert](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). Außerdem können Sie die unten aufgeführten Schritte überprüfen.

>[!CAUTION]
>
>DCM-Datendateien enthalten Daten für alle Ihre Werbetreibenden oder Kunden. Wenn Sie bestimmte Clients weglassen müssen, müssen Sie die Dateien bearbeiten, bevor [!DNL Audience Manager]Sie sie zur Verfügung stellen.

## Häufigkeit und Verfügbarkeit von Datenübertragungen

[!DNL Audience Manager] prüft und überträgt Daten einmal täglich. Daten sind in der Regel nach [!DNL Audience Manager] 24 Stunden verfügbar.

## Schritte

1. [Eine Gruppe erstellen](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Gruppen steuern den Zugriff auf Ihre DCM-Daten. Schließlich werden Sie diese Gruppe einladen und dieser [!DNL Audience Manager] Gruppe hinzufügen.

1. [Überprüfen Sie Ihren Google Cloud Speicherstatus](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud Storage enthält den Datenbehälter, der Ihre [!UICONTROL Data Transfer] und [!UICONTROL Match Tables]. Sie müssen einen Behälter einrichten oder sicherstellen, dass Ihre neue Gruppe Zugriff auf einen vorhandenen Datenspeicher-Behälter hat.

1. [Eine Datendatei-URL abrufen](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   Arbeiten Sie mit Ihrem DCM-Kundenbetreuer oder Plattformlösungsberater zusammen. Sie stellen Ihnen eine URL für Ihre Datendateien bereit. [!DNL Google] kann das Format für Behälter und Dateinamen in zukünftigen Versionen ändern. Arbeiten Sie erneut mit Ihrem DCM-Kundenbetreuer, um sicherzustellen, dass Sie die richtigen Formate verwenden.

1. [Legen Sie die Behälterberechtigungen](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)fest.

   Mit dieser [!DNL Cloud Storage Manager] Option können Sie die Freigabe von Daten und den Zugriff auf Behälter steuern. Geben Sie Ihrer Gruppe Zugriff auf das Behälter, das Ihre [!UICONTROL Data Transfer] und [!UICONTROL Match Table] Ihre Dateien enthält.

1. [Richten Sie die Datenfreigabe](https://support.google.com/dcm/partner/answer/6206106?hl=en)ein.

   Freigegebene DCM-Benutzer-IDs werden verschlüsselt, um den Datenschutz zu schützen. Die Verschlüsselung fügt dem Ende Ihrer Datenübertragdatei zwei Spalten hinzu und `PartnerId1``PartnerId2`. Diese Spalten enthalten kodierte Benutzer-IDs, die für jedes Unternehmen gelten, das diese Dateien erhält.

   [!DNL Audience Manager] Kann als autorisierter Drittanbieter DCM-Daten erhalten, kann die IDs aber nicht dekodieren. Andererseits wissen [!DNL Audience Manager] wir jedoch, wie die kodierten IDs mit unseren IDs übereinstimmen. Dies bedeutet, dass wir Benutzer mit Vertrauen und Genauigkeit übereinstimmen und synchronisieren können.

   >[!NOTE]
   >DCM-Dateien können nicht importiert [!DNL Audience Manager] werden, wenn Sie bereits Daten für zwei andere Drittanbieter-Partner freigeben.

1. Einladung zur [!DNL Audience Manager] Gruppe einladen.

   Nachdem Sie eine Gruppe erstellt und Zugriff auf einen Datenbehälter erteilt haben, laden [!DNL Audience Manager] Sie sie zur Gruppe ein. Senden Sie eine Einladungs-E-Mail an DFA-AAM@adobe.com. Achten Sie darauf, die Datendatei-URL aus Schritt 3 einzuschließen. Unsere internen Teams werden mit Ihnen zusammenarbeiten, um den Zugriff nach Annahme der Einladung zu bestätigen. 1. Richten Sie zwei Datenquellen für DCM-Daten in der [!DNL Audience Manager] Benutzeroberfläche ein.

   Benennen Sie die Datenquellen `Advertiser Analytics: DCM Platform` und `Advertiser Analytics: AAM+DCM Platform`. Legen Sie [im Arbeitsablauf &quot;Data Sources](../../../features/manage-datasources.md#create-data-source) erstellen&quot; den ID-Typ auf `Cookie`. Geben Sie die IDs der beiden neuen Datenquellen für unsere internen Teams frei.

1. Sie können einfach Eigenschaften aus den DCM-Dateien erstellen, in [!DNL Audience Manager]die Sie importieren. Siehe [Aktionsfähige Protokolldateien](../../../integration/media-data-integration/actionable-log-files.md) und bitten Sie Ihren [!DNL Audience Manager] Berater oder die Kundenunterstützung, die Funktion für Sie zu aktivieren.

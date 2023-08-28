---
description: Um Daten von Ihrem eigenen Amazon S3-Behälter an Audience Manager zu senden, müssen Sie zunächst die Konfiguration einer dedizierten Amazon S3-Rolle anfordern.
solution: Audience Manager
title: Nutzen Sie die kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre eingehenden Dateien.
feature: Inbound Data Transfers
source-git-commit: ff023fb57e2653ca65323313a37852d379e4b00c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# Nutzen Sie die kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre eingehenden Dateien. {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Um Daten von Ihrem eigenen Amazon S3-Behälter an Audience Manager zu senden, müssen Sie zunächst die Konfiguration einer dedizierten Amazon S3-Rolle anfordern.

Gehen Sie dazu wie folgt vor:

1. Wenden Sie sich an die Kundenunterstützung und fordern Sie eine alternative Methode zum Senden von Dateien an den Audience Manager an.
2. Stellen Sie dem Kundendienst die [!DNL Amazon Resource Name (ARN)] für eine Rolle in Ihrem Amazon S3-Konto, mit der Sie Dateien senden. _Diese Rolle muss erstellt werden, bevor Sie sich an die Kundenunterstützung wenden_. Nachdem die Konfiguration abgeschlossen ist, stellt Ihnen die Kundenunterstützung die [!DNL Amazon Resource Name (ARN)] für die neu erstellte Rolle.
3. Bearbeiten Sie die Berechtigungen Ihrer vorhandenen Amazon S3-Rolle, um die von der Kundenunterstützung bereitgestellte Rolle zu übernehmen.

>[!NOTE]
>
>Stellen Sie beim Übertragen von eingehenden Daten an den Audience Manager Amazon S3 sicher, dass Sie die `bucket-owner-full-control` [Zugriffssteuerungsliste](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) damit Audience Manager die Daten korrekt verarbeitet.
><br>
>Beispiel für den Amazon Web Services-Befehl: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`.


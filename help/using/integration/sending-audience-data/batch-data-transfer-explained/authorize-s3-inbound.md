---
description: Um Daten von Ihrem eigenen Amazon S3-Behälter an Audience Manager zu senden, müssen Sie zunächst die Konfiguration einer dedizierten Amazon S3-Rolle anfordern.
solution: Audience Manager
title: Nutzen Sie die kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre eingehenden Dateien.
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
source-git-commit: 65963c462f2a5abb1e2597b3d943628baa9d4730
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Nutzen Sie die kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre eingehenden Dateien. {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Um Daten von Ihrem eigenen Amazon S3-Behälter an Audience Manager zu senden, müssen Sie zunächst die Konfiguration einer dedizierten Amazon S3-Rolle anfordern.

Gehen Sie dazu wie folgt vor:

1. Wenden Sie sich an die Kundenunterstützung und fordern Sie eine alternative Methode zum Senden von Dateien an den Audience Manager an.
2. Stellen Sie der Kundenunterstützung die [!DNL Amazon Resource Name (ARN)] für eine Rolle in Ihrem Amazon S3-Konto zur Verfügung, die Sie zum Senden von Dateien verwenden werden. _Diese Rolle muss erstellt werden, bevor Sie sich an die Kundenunterstützung wenden_. Nachdem die Konfiguration abgeschlossen ist, stellt die Kundenunterstützung Ihnen den [!DNL Amazon Resource Name (ARN)] für die neu erstellte Rolle bereit.
3. Bearbeiten Sie die Berechtigungen Ihrer vorhandenen Amazon S3-Rolle, um die von der Kundenunterstützung bereitgestellte Rolle zu übernehmen.

>[!NOTE]
>
>Stellen Sie beim Übertragen der eingehenden Daten an den Amazon S3-Audience Manager sicher, dass Sie die Zugriffssteuerungsliste `bucket-owner-full-control` [2} verwenden, damit Audience Manager die Daten korrekt verarbeiten kann.](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html)
>
>Beispiel für den Amazon Web Services-Befehl: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`

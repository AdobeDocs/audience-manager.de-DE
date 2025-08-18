---
description: Um Daten von Ihrem eigenen Amazon S3-Bucket an Audience Manager zu senden, müssen Sie zunächst die Konfiguration einer dedizierten Amazon S3-Rolle anfordern.
solution: Audience Manager
title: Nutzen Sie die kontenübergreifenden Amazon S3-Bucket-Berechtigungen für Ihre eingehenden Dateien
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
source-git-commit: 65963c462f2a5abb1e2597b3d943628baa9d4730
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Nutzen Sie die kontenübergreifenden Amazon S3-Bucket-Berechtigungen für Ihre eingehenden Dateien {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Um Daten von Ihrem eigenen Amazon S3-Bucket an Audience Manager zu senden, müssen Sie zunächst die Konfiguration einer dedizierten Amazon S3-Rolle anfordern.

Gehen Sie dazu wie folgt vor.

1. Wenden Sie sich an die Kundenunterstützung und fordern Sie eine alternative Methode zum Senden von Dateien an Audience Manager an.
2. Geben Sie der Kundenunterstützung die [!DNL Amazon Resource Name (ARN)] für eine Rolle in Ihrem Amazon S3-Konto, die Sie zum Senden von Dateien verwenden werden. _Diese Rolle muss erstellt werden, bevor Sie sich an die Kundenunterstützung wenden_. Nach Abschluss der Konfiguration stellt Ihnen die Kundenunterstützung die [!DNL Amazon Resource Name (ARN)] für die neu erstellte Rolle bereit.
3. Bearbeiten Sie die Berechtigungen Ihrer bestehenden Amazon S3-Rolle, um die von der Kundenunterstützung bereitgestellte Rolle zu übernehmen.

>[!NOTE]
>
>Stellen Sie beim Übertragen eingehender Daten an den Audience Manager Amazon S3-Bucket sicher, dass Sie die `bucket-owner-full-control` [Zugriffssteuerungsliste](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) verwenden, damit Audience Manger die Daten korrekt verarbeitet.
>
>Beispiel für den Amazon Web Services-Befehl: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`

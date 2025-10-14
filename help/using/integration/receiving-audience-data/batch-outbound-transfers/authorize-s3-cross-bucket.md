---
description: Der Prozess der ausgehenden Datenübertragung für Kunden, die den Amazon Simple Storage Service (Amazon S3) verwenden, erfordert, dass wir Sie nach Ihrem Amazon S3-Zugriffsschlüssel und -Geheimschlüssel fragen, um die ausgehenden Datendateien an Ihren Bucket zu senden.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Nutzen Sie die kontenübergreifenden Amazon S3-Bucket-Berechtigungen für Ihre ausgehenden Dateien
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 9c0254e8a29ffeb0353ed6faa898b74bcae7cef1
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Nutzen Sie die kontenübergreifenden Amazon S3-Bucket-Berechtigungen für Ihre ausgehenden Dateien {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Der [!UICONTROL Outbound Data Transfer] für Kunden, die [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) verwenden, erfordert, dass wir Sie nach Ihrem [!DNL Amazon S3] Zugriffsschlüssel und geheimen Schlüssel fragen, um die ausgehenden Datendateien an Ihren Bucket zu senden.

Wenn Sie Ihren [!DNL Amazon S3] Zugriffsschlüssel und geheimen Schlüssel nicht mit uns teilen möchten, wenden Sie sich an Ihren [!DNL Audience Manager] Berater oder die Kundenunterstützung und dieser wird [!DNL Cross-Account Bucket Permissions] für Sie einrichten.

Sie müssen nur unsere [!DNL Amazon S3]-Konto-ID zu einer Zulassungsliste für den [!DNL S3] hinzufügen, in dem Sie die ausgehenden Datendateien empfangen möchten, wie in der [Dokumentation zu Amazon S3 &#x200B;](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Ihr [!DNL Audience Manager] oder die Kundenunterstützung werden Ihnen unsere [!DNL Amazon S3] Account-ID zur Verfügung stellen.

>[!NOTE]
>
>Aufgrund der Objektgrößenbeschränkung von Amazon S3 unterstützt Audience Manager Aufspaltungsgrößen von bis zu 1 TB. Wenn Sie keine Aufspaltungsgröße angeben, wird das 1 TB-Limit automatisch angewendet.


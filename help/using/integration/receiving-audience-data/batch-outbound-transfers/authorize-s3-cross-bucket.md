---
description: Der Prozess der ausgehenden Datenübertragung für Kunden, die den Amazon Simple Storage Service (Amazon S3) verwenden, erfordert, dass wir Sie nach Ihrem Amazon S3-Zugriffsschlüssel und -Geheimschlüssel fragen, um die ausgehenden Datendateien an Ihren Bucket zu senden.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Nutzen Sie die kontenübergreifenden Amazon S3-Bucket-Berechtigungen für Ihre ausgehenden Dateien
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
TQID: 'https://experienceleague.adobe.com/Ji1ltYPv4eoY5-eZiX62JyQ5SJzdMjFZdKeRzJnwKZg'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: bcf89bb2-9d92-4897-90ec-483950be810f
    internal-label: Outbound data transfers
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%
---
# Nutzen Sie die kontenübergreifenden Amazon S3-Bucket-Berechtigungen für Ihre ausgehenden Dateien {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Der [!UICONTROL Outbound Data Transfer] für Kunden, die [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) verwenden, erfordert, dass wir Sie nach Ihrem [!DNL Amazon S3] Zugriffsschlüssel und geheimen Schlüssel fragen, um die ausgehenden Datendateien an Ihren Bucket zu senden.

Wenn Sie Ihren [!DNL Amazon S3] Zugriffsschlüssel und geheimen Schlüssel nicht mit uns teilen möchten, wenden Sie sich an Ihren [!DNL Audience Manager] Berater oder die Kundenunterstützung und dieser wird [!DNL Cross-Account Bucket Permissions] für Sie einrichten.

Sie müssen nur unsere [!DNL Amazon S3]-Konto-ID zu einer Zulassungsliste für den [!DNL S3] hinzufügen, in dem Sie die ausgehenden Datendateien empfangen möchten, wie in der [Dokumentation zu Amazon S3 &#x200B;](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Ihr [!DNL Audience Manager] oder die Kundenunterstützung werden Ihnen unsere [!DNL Amazon S3] Account-ID zur Verfügung stellen.

>[!NOTE]
>
>Aufgrund der Objektgrößenbeschränkung von Amazon S3 unterstützt Audience Manager Aufspaltungsgrößen von bis zu 1 TB. Wenn Sie keine Aufspaltungsgröße angeben, wird das 1 TB-Limit automatisch angewendet.


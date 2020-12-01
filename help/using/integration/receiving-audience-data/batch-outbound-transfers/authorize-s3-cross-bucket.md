---
description: Der Ausgehende Datenübertragungsprozess für Kunden, die Amazon Simple Datenspeicherung Service (Amazon S3) verwenden, erfordert, dass wir Ihren Amazon S3-Zugriffsschlüssel und -geheimen Schlüssel anfordern, um die ausgehenden Datendateien an Ihren Behälter zu liefern.
seo-description: Der Ausgehende Datenübertragungsprozess für Kunden, die Amazon Simple Datenspeicherung Service (Amazon S3) verwenden, erfordert, dass wir Ihren Amazon S3-Zugriffsschlüssel und -geheimen Schlüssel anfordern, um die ausgehenden Datendateien an Ihren Behälter zu liefern.
seo-title: Nutzen der kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre ausgehenden Dateien
solution: Audience Manager
title: Nutzen der kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre ausgehenden Dateien
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 14%

---


# Nutzen der kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre ausgehenden Dateien {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Der [!UICONTROL Outbound Data Transfer]-Prozess für Kunden, die [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) verwenden, erfordert, dass wir Ihren [!DNL Amazon S3]-Zugriffsschlüssel und -geheimen Schlüssel anfordern, um die ausgehenden Datendateien an Ihren Behälter zu liefern.

Wenn Sie Ihren [!DNL Amazon S3]-Zugriffsschlüssel und -geheimen Schlüssel nicht für uns freigeben möchten, wenden Sie sich an Ihren [!DNL Audience Manager]-Berater oder an den Kundendienst und richten [!DNL Cross-Account Bucket Permissions] für Sie ein. Sie müssen Ihre [!DNL Amazon S3] Konto-ID nur einer Zulassungsliste für den [!DNL S3]-Behälter hinzufügen, in dem Sie die ausgehenden Datendateien erhalten möchten, wie in der [Amazon S3-Dokumentation](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html) beschrieben. Ihr [!DNL Audience Manager]-Berater oder der Kundendienst stellt Ihnen unsere [!DNL Amazon S3] Konto-ID zur Verfügung.
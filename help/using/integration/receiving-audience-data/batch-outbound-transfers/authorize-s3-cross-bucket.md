---
description: Der Prozess der ausgehenden Datenübertragung für Kunden, die Amazon Simple Storage Service (Amazon S3) verwenden, erfordert, dass wir Ihren Amazon S3-Zugriffsschlüssel und -geheimen Schlüssel anfordern, um die ausgehenden Datendateien an Ihren Bucket zu senden.
seo-description: Der Prozess der ausgehenden Datenübertragung für Kunden, die Amazon Simple Storage Service (Amazon S3) verwenden, erfordert, dass wir Ihren Amazon S3-Zugriffsschlüssel und -geheimen Schlüssel anfordern, um die ausgehenden Datendateien an Ihren Bucket zu senden.
seo-title: Nutzen der kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre ausgehenden Dateien
solution: Audience Manager
title: Nutzen der kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre ausgehenden Dateien
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Ausgehende Datenübertragungen
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 14%

---

# Nutzen der kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre ausgehenden Dateien {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Der [!UICONTROL Outbound Data Transfer]-Prozess für Kunden, die [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) verwenden, erfordert, dass wir nach Ihrem [!DNL Amazon S3]-Zugriffsschlüssel und geheimen Schlüssel fragen, um die ausgehenden Datendateien an Ihren Bucket zu senden.

Wenn Sie Ihren [!DNL Amazon S3]-Zugriffsschlüssel und geheimen Schlüssel nicht für uns freigeben möchten, wenden Sie sich an Ihren [!DNL Audience Manager]-Berater oder an die Kundenunterstützung und richten [!DNL Cross-Account Bucket Permissions] für Sie ein. Sie müssen nur die [!DNL Amazon S3]-Konto-ID zu einer Zulassungsliste für den [!DNL S3]-Bucket hinzufügen, an den Sie die ausgehenden Datendateien erhalten möchten, wie in der [Amazon S3-Dokumentation](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html) beschrieben. Ihr [!DNL Audience Manager] -Berater oder die Kundenunterstützung stellt Ihnen unsere [!DNL Amazon S3] -Konto-ID zur Verfügung.

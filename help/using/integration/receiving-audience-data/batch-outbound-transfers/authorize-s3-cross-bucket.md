---
description: Der Prozess zur Übertragung ausgehender Daten für Kunden, die Amazon Simple Storage Service (Amazon S3) verwenden, erfordert, dass wir Ihren Amazon S3-Zugriffsschlüssel und geheimen Schlüssel anfordern, um die ausgehenden Datendateien an Ihren Behälter zu liefern.
seo-description: Der Prozess zur Übertragung ausgehender Daten für Kunden, die Amazon Simple Storage Service (Amazon S3) verwenden, erfordert, dass wir Ihren Amazon S3-Zugriffsschlüssel und geheimen Schlüssel anfordern, um die ausgehenden Datendateien an Ihren Behälter zu liefern.
seo-title: Nutzen Sie die kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre ausgehenden Dateien
solution: Audience Manager
title: Nutzen Sie die kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre ausgehenden Dateien
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Nutzen Sie die kontoübergreifenden Bucket-Zugriffsrechte von Amazon S3 für Ihre ausgehenden Dateien {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Der [!UICONTROL Outbound Data Transfer] Prozess für Kunden, die [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) verwenden, erfordert, dass wir Ihren [!DNL Amazon S3] Zugriffsschlüssel und geheimen Schlüssel anfordern, um die ausgehenden Datendateien an Ihren Behälter zu liefern.

Wenn Sie Ihren [!DNL Amazon S3] Zugriffsschlüssel und geheimen Schlüssel nicht für uns freigeben möchten, wenden Sie sich an Ihren [!DNL Audience Manager] Berater oder an den Kundendienst, und diese werden für Sie eingerichtet [!DNL Cross-Account Bucket Permissions] . Sie müssen nur unsere [!DNL Amazon S3] Konto-ID für den [!DNL S3] Behälter, für den Sie die ausgehenden Datendateien erhalten möchten, wie in der [Amazon S3-Dokumentation](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)beschrieben, auf eine Whitelist setzen. Ihr [!DNL Audience Manager] Berater oder die Kundenunterstützung stellen Ihnen unsere [!DNL Amazon S3] Konto-ID zur Verfügung.
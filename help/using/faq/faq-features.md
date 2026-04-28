---
description: Häufige produkt- und funktionsbezogene Fragen und Probleme.
keywords: audience manager cookies
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: Häufig gestellte Fragen zu Produktfunktionen
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
TQID: https://experienceleague.adobe.com/gsJ4qXlNDpfWmTq0jjmtjfUWI60yRr7uBTxZjsF-pQE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f2fdbb191013b0bcb9bdab0529e3b7f3c872fd54
workflow-type: tm+mt
source-wordcount: 428
ht-degree: 75%

---

# Häufig gestellte Fragen zu Produktfunktionen{#product-features-and-functions-faq}

Häufige produkt- und funktionsbezogene Fragen und Probleme.

 

<!-- 

faq_features_functions.xml

 -->

**Was ist meine Organisations-ID und wie finde ich sie?**

Die *`Organization ID`* ist eine eindeutige ID, mit der Ihr Unternehmen in [!DNL Audience Manager] und in [!DNL Adobe Experience Cloud] identifiziert wird. Sie besteht aus einer 24-stelligen alphanumerischen Zeichenfolge, bei der die der Groß- und Kleinschreibung berücksichtigt wird, gefolgt von [!UICONTROL @AdobeOrg].

Eine *`Organization ID`* sieht beispielsweise so aus: `1FD6776A524453CC0A490D44@AdobeOrg`.

Die *`Organization ID`* wird von der [DIL](../dil/dil-overview.md)-API von Audience Manager, dem [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) und anderen [!DNL Experience Cloud]-Lösungen verwendet. Benutzer mit Administratorberechtigungen können die *`Organization ID`* in der [!DNL Adobe Admin Console] finden. Siehe [Häufig gestellte Fragen zur Administration – Benutzerverwaltung](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

 

**Kann ich Eigenschaften oder Ziele stapelweise erstellen?**

Ja. Siehe [Tools zur Massenverwaltung](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>Die [!UICONTROL Bulk Management Tools] werden von [!DNL Audience Manager] *nicht* unterstützt. Sie werden nur zur Vereinfachung und als Höflichkeit zur Verfügung gestellt. Bei Massenänderungen sollten Sie stattdessen mit den [Audience Manager-APIs](../api/api.md) arbeiten.

 

**When performing a bulk ID export to a destination, some of the customer IDs are missing. Why does that happen?**

When a device ID ([AAM UUID](../reference/ids-in-aam.md)) is linked to multiple CRM IDs ([DPUUIDs](../reference/ids-in-aam.md)), only the latest mapping gets exported. This is why you may see a lower than expected number of device IDs being exported.

 

**Kann [!DNL Audience Manager] den Bedarf an Tags oder Pixeln von Drittanbietern reduzieren und die Seitenladezeiten verbessern?**

Wenn [!DNL Audience Manager] in Ihren Drittdatenpartner integriert ist, können Sie dessen Pixel und Tags durch einen Server-zu-Server-ID-Aufruf an [!DNL Audience Manager] ersetzen. In diesem Fall würde [!DNL Audience Manager] einen einzelnen ID-Aufruf auslösen, wenn wir einen Benutzer zum ersten Mal sehen, und diese Informationen mit Ihrem Partner synchronisieren. Dadurch entfällt die Notwendigkeit, von jeder Seite mehrere Pixel aufzurufen. Die Reduzierung von Pixelaufrufen kann die Seitenladezeit verbessern.

 

**Ich habe einen Daten-Feed abonniert. Wo werden diese Daten gespeichert?**

Ihr Daten-Feed und alle im Feed enthaltenen Eigenschaften werden als Unterordner und Eigenschaften in [!DNL Audience Manager] angezeigt. Gehen Sie zu **[!UICONTROL Audience Data > Traits]** und erweitern Sie den Ordner [!UICONTROL 3rd-Party Data], um Ihre Eigenschaften anzuzeigen oder Segmente und Modelle mit diesen Daten zu erstellen.

 

**Was ist [!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager verwendete [!UICONTROL Tag Insertion Manager] (TIM) zum Erstellen und Verwalten von [!UICONTROL data collection code (DIL)]. Diese Funktion ist mittlerweile veraltet und wurde zuerst durch [!UICONTROL Dynamic Tag Manager (DTM)] und später durch [!DNL Adobe Experience Platform Tags] ersetzt. For more information, see [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

 

**Gibt es einen Unterschied zwischen Adobe Analytics- und Audience Manager-Segmenten?**

Ja. Eine ausführliche Beschreibung der Unterschiede finden Sie unter [Grundlegendes zu Segmenten in Analytics und Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

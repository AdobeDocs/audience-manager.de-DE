---
description: Beschreibt die Authentifizierungsanforderungen und die Textformatierung, die in der DIL-Dokumentation auf Klassenebene verwendet werden.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Erste Schritte mit DIL-APIs auf Klassenebene
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
TQID: https://experienceleague.adobe.com/RlkKHc2IuInFWfWOnTKS94XhBmbDbQYjtQZI40DsU-8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 203
ht-degree: 0%

---

# Erste Schritte mit DIL-APIs auf Klassenebene{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung des [!DNL Data Integration Library (DIL)] und der [!DNL DIL] eingestellt.
>
>Bestehende Kundinnen und Kunden können ihre [!DNL DIL] Implementierung weiterhin nutzen. Adobe wird jedoch keine [!DNL DIL] über diesen Punkt hinaus entwickeln. Kundinnen und Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) auf ihre langfristige Datenerfassungsstrategie hin zu überprüfen.
>
>Kunden, die nach Juli 2023 neue Datenerfassungsintegrationen implementieren möchten, sollten stattdessen [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) verwenden.

Mit den DIL-APIs auf Klassenebene können Sie Audience Manager-Objekte programmgesteuert erstellen und damit arbeiten. Die APIs auf Klassenebene arbeiten mit den anderen Funktionen auf Instanzebene zusammen, um Werte festzulegen oder Daten zurückzugeben.

## Erste Schritte mit DIL-APIs auf Klassenebene {#get-started}

Beschreibt die Authentifizierungsanforderungen und die Textformatierung, die in der [!UICONTROL DIL] auf Klassenebene verwendet werden.

<!-- 

c_class_start.xml

 -->

Beim Arbeiten mit [!UICONTROL DIL]-APIs auf Klassenebene:

* Für den Zugriff sind ein Partnername und eine Container-Namespace-ID (NSID) erforderlich. Wenden Sie sich an Ihren Audience Manager Account Manager, um diese Informationen zu erhalten.
* Ersetzen Sie einen *(kursiv*) Beispieltext in der API-Dokumentation durch den Wert, die ID oder eine andere Variable, wie von der Methode benötigt, mit der Sie arbeiten.
* [!UICONTROL DIL] schreibt codierte Daten in ein Ziel-Cookie. Leerzeichen werden beispielsweise als `%20` und Semikolons als `%3B` codiert.

---
description: Beschreibt die Authentifizierungsanforderungen und die Textformatierung, die in der DIL-Dokumentation auf Klassenebene verwendet werden.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Erste Schritte mit DIL-APIs auf Klassenebene
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '203'
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

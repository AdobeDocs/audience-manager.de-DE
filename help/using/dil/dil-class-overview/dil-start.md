---
description: Beschreibt Authentifizierungsanforderungen und die Textformatierung, die in der DIL-Dokumentation auf Klassenebene verwendet werden.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Erste Schritte mit DIL-APIs auf Klassenebene
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 8%

---

# Erste Schritte mit DIL-APIs auf Klassenebene{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Ab Juli 2023 hat die Adobe die Entwicklung der [!DNL Data Integration Library (DIL)] und [!DNL DIL] -Erweiterung.
><br>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] Implementierung. Die Adobe wird sich jedoch nicht entwickeln [!DNL DIL] über diesen Punkt hinaus. Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie.
><br>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) anstatt.

Mit DIL-APIs auf Klassenebene können Sie Audience Manager-Objekte programmgesteuert erstellen und verwenden. Die APIs auf Klassenebene arbeiten mit den anderen Funktionen auf Instanzebene, um Werte festzulegen oder Daten zurückzugeben.

## Erste Schritte mit DIL-APIs auf Klassenebene {#get-started}

Beschreibt Authentifizierungsanforderungen und die Textformatierung, die auf Klassenebene verwendet werden [!UICONTROL DIL] Dokumentation.

<!-- 

c_class_start.xml

 -->

Beim Arbeiten mit der Klassenebene [!UICONTROL DIL] APIs:

* Für den Zugriff sind ein Partnername und eine Container-Namespace-ID (NSID) erforderlich. Wenden Sie sich an Ihren Kundenbetreuer, um diese Informationen zu erhalten.
* Beispiel ersetzen *kursiv* Text in der API-Dokumentation mit -Wert, -ID oder einer anderen -Variablen, wie von der verwendeten -Methode benötigt.
* [!UICONTROL DIL] schreibt kodierte Daten in ein Ziel-Cookie. Leerzeichen werden beispielsweise als `%20` und Semikolons als `%3B`.

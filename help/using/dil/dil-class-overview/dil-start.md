---
description: Beschreibt Authentifizierungsanforderungen und die Textformatierung, die in der DIL-Dokumentation auf Klassenebene verwendet werden.
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
>Ab Juli 2023 hat Adobe die Entwicklung der Erweiterung [!DNL Data Integration Library (DIL)] und der Erweiterung [!DNL DIL] eingestellt.
>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] -Implementierung verwenden. Adobe wird jedoch nicht mehr [!DNL DIL] als bisher entwickeln. Kunden wird empfohlen, das [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie zu bewerten.
>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten stattdessen das [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) verwenden.

Mit DIL-APIs auf Klassenebene können Sie Audience Manager-Objekte programmgesteuert erstellen und verwenden. Die APIs auf Klassenebene arbeiten mit den anderen Funktionen auf Instanzebene, um Werte festzulegen oder Daten zurückzugeben.

## Erste Schritte mit DIL-APIs auf Klassenebene {#get-started}

Beschreibt Authentifizierungsanforderungen und die Textformatierung, die in der Dokumentation auf Klassenebene [!UICONTROL DIL] verwendet werden.

<!-- 

c_class_start.xml

 -->

Beim Arbeiten mit den Klassenebenen-APIs [!UICONTROL DIL]:

* Für den Zugriff sind ein Partnername und eine Container-Namespace-ID (NSID) erforderlich. Wenden Sie sich an Ihren Kundenbetreuer, um diese Informationen zu erhalten.
* Ersetzen Sie jeden Beispieltext *kursiv* in der API-Dokumentation durch den Wert, die ID oder eine andere Variable, wie von der Methode, mit der Sie arbeiten, benötigt wird.
* [!UICONTROL DIL] schreibt kodierte Daten in ein Ziel-Cookie. Leerzeichen werden beispielsweise als `%20` und Semikolons als `%3B` kodiert.

---
description: Fügen Sie das Zielgruppen-Management-Modul zu Adobe Analytics AppMeasurement hinzu, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager-Data Integration Library-Code (DIL) ein Pixel von der Seite sendet.
keywords: Zielgruppenanalyse; Analyse; ssf; Serverseitige Weiterleitung
seo-description: Fügen Sie das Zielgruppen-Management-Modul zu Adobe Analytics AppMeasurement hinzu, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager-Data Integration Library-Code (DIL) ein Pixel von der Seite sendet.
seo-title: Implementieren des Zielgruppen-Management-Moduls
solution: Audience Manager
title: Implementieren des Zielgruppen-Management-Moduls
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics-Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: 8fc6c96bf9e8216ef4458989c87f1f93ea9f0347
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 4%

---

# Weiterleiten von Daten von [!DNL Adobe Analytics] an [!DNL Audience Manager] {#implement-the-audience-management-module}

Führen Sie die Schritte in diesem Tutorial aus, um [!DNL Analytics]-Daten an [!DNL Audience Manager] weiterzuleiten, anstatt dass der [!DNL Audience Manager] [!UICONTROL Data Integration Library]-Code ([!DNL DIL]) ein Pixel von der Seite sendet.

>[!TIP]
>
>Es wird empfohlen, [!DNL Adobe Experience Platform Launch] zu verwenden, um [!UICONTROL Analytics] Daten an [!DNL Audience Manager] weiterzuleiten. Durch die Verwendung von [!UICONTROL Launch] müssen Sie keinen Code manuell in [!DNL AppMeasurement] kopieren, wie auf dieser Seite dargestellt.

## Voraussetzungen {#prereqs}

Zusätzlich zur Aktivierung der Erweiterungen oder Implementierung des in diesem Dokument beschriebenen Codes müssen Sie auch:

* Implementieren Sie den [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html).
* Aktivieren Sie [Serverseitige Weiterleitung](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) für Report Suites in [!UICONTROL Adobe Analytics Admin Console].

## Implementierung {#implementation}

Je nach der von Ihnen verwendeten Tag-Management-Lösung gibt es zwei Methoden zur Implementierung der Datenweiterleitung von [!DNL Adobe Analytics] zu [!DNL Audience Manager].

### Implementierung mit [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] empfiehlt die Verwendung der  [](https://experienceleague.adobe.com/docs/launch/using/home.html?lang=en) Launch-Erweiterung zum Instrumentieren  [!DNL Adobe Analytics] und  [!DNL Audience Manager] Verwenden Ihrer Eigenschaften. In diesem Fall müssen Sie keinen Code manuell kopieren. Stattdessen müssen Sie die Datenfreigabe in der [!DNL Analytics Launch]-Erweiterung aktivieren, wie in der Abbildung unten dargestellt. Weitere Informationen finden Sie in der Dokumentation zur [Adobe Analytics-Erweiterung](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Wenn Sie die [!DNL Adobe Analytics]-Erweiterung installieren, installieren Sie *nicht* auch die [!DNL Audience Manager]-Erweiterung. Die Weiterleitung von Daten aus der [!DNL Analytics]-Erweiterung ersetzt die [!DNL Audience Manager]-Erweiterungsfunktion.

![So aktivieren Sie die Datenfreigabe von der Adobe Analytics-Erweiterung für Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Definierte Codeelemente {#code-elements-defined}

Die folgende Tabelle definiert wichtige Variablen im Codebeispiel.

| Parameter | Beschreibung |
|--- |--- |
| `partner` | Erforderlich. Dies ist ein Partnername, der Ihnen von [!DNL Adobe] zugewiesen wird. Dies wird manchmal auch als Ihre [!UICONTROL partner ID] oder Partner-Subdomäne bezeichnet.  Wenden Sie sich an Ihren [!DNL Adobe]-Berater oder an die [Kundenunterstützung](https://helpx.adobe.com/de/marketing-cloud/contact-support.html), wenn Sie Ihren Partnernamen nicht kennen. |
| `containerNSID` | Erforderlich. Die meisten Kunden können einfach `"containerNSID":0` festlegen. Wenn Ihr Unternehmen jedoch ID-Synchronisationen mit einem anderen Container anpassen muss, können Sie diese Container-ID hier angeben. |
| `uuidCookie` | Optional. Mit dieser Konfiguration können Sie ein [!DNL Adobe] -Cookie in der Erstanbieterdomäne setzen. Dieses [!DNL cookie] enthält die [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Erforderlich. Der Parameter `namespace` ist erforderlich, wenn Sie das [!DNL AudienceManagement]-Modul verwenden, das mit [!UICONTROL AppMeasurement] Version 2.10 oder neuer integriert ist. Für dieses [!UICONTROL AudienceManagement]-Modul müssen Sie [!UICONTROL Adobe Experience Platform Identity Service] 3.3 oder höher verwenden. <br><br>Die  [!UICONTROL Experience Cloud Organization ID] ist die ID, die ein Unternehmen erhält, wenn es sich für  [!UICONTROL Experience Cloud]anmeldet. Erfahren Sie mehr über die Organisations-ID Ihres Unternehmens in [Organisationen und Kontoverknüpfung](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Ergebnisse: Datenweiterleitung an [!DNL Audience Manager] {#results-data-forwarding}

Ihre [!DNL Analytics]-Implementierung sendet Daten an [!DNL Audience Manager], nachdem Sie über Folgendes verfügen:

* [!UICONTROL Server-Side Forwarding] aktiviert (wenden Sie sich an Ihren Berater über diese Funktion);
* [!DNL Adobe Experience Platform Identity Service] implementiert;
* Befolgte die Implementierungsschritte in diesem Tutorial.

Dieser Prozess sendet Daten an [!DNL Audience Manager]:

* Bei Seitenansichtsaufrufen;
* über getrackte Links;
* Aus Video-Meilensteinen und Heartbeat-Videoansichten.

>[!NOTE]
>
>Die Variablen, die von [!DNL Analytics] an [!DNL Audience Manager] gesendet werden, verwenden spezielle Präfixe. Sie müssen diese Präfixe beim Erstellen von [!DNL Audience Manager]-Eigenschaften verstehen und berücksichtigen. Weitere Informationen zu diesen Präfixen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md).

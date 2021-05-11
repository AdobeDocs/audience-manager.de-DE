---
description: hinzufügen Sie das Audience Management Module an Adobe Analytics AppMeasurement, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager-Data Integration Library-Code (DIL) ein Pixel von der Seite sendet.
keywords: Analyse der Audience; Analyse; ssf; serverseitige Weiterleitung
seo-description: hinzufügen Sie das Audience Management Module an Adobe Analytics AppMeasurement, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager-Data Integration Library-Code (DIL) ein Pixel von der Seite sendet.
seo-title: Implementieren des Audience Management-Moduls
solution: Audience Manager
title: Implementieren des Audience Management-Moduls
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics-Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 4%

---

# Weiterleiten von Daten von [!DNL Adobe Analytics] an [!DNL Audience Manager] {#implement-the-audience-management-module}

Führen Sie die Schritte in diesem Lernprogramm aus, um [!DNL Analytics]-Daten an [!DNL Audience Manager] weiterzuleiten, anstatt dass der [!DNL Audience Manager] [!UICONTROL Data Integration Library]-Code ([!DNL DIL]) ein Pixel von der Seite sendet.

>[!TIP]
>
>Es wird empfohlen, [!DNL Adobe Experience Platform Launch] zu verwenden, um [!UICONTROL Analytics]-Daten an [!DNL Audience Manager] weiterzuleiten. Bei Verwendung von [!UICONTROL Launch] müssen Sie keinen Code manuell in [!DNL AppMeasurement] kopieren, wie auf dieser Seite gezeigt.

## Voraussetzungen {#prereqs}

Zusätzlich zur Aktivierung der Erweiterungen oder Implementierung des in diesem Dokument beschriebenen Codes müssen Sie auch:

* Implementieren Sie den [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html).
* Aktivieren Sie [Serverseitige Weiterleitung](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) für Report Suites in [!UICONTROL Adobe Analytics Admin Console].

## Implementierung {#implementation}

Es gibt zwei Methoden zur Implementierung der Datenweiterleitung von [!DNL Adobe Analytics] zu [!DNL Audience Manager], je nach der von Ihnen verwendeten Tag-Management-Lösung.

### Implementierung mit [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] empfiehlt die Verwendung der  [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launchextension zum Instrumentieren  [!DNL Adobe Analytics] und  [!DNL Audience Manager] auf Ihren Eigenschaften. In diesem Fall müssen Sie keinen Code manuell kopieren. Stattdessen müssen Sie die Datenfreigabe in der Erweiterung [!DNL Analytics Launch] aktivieren, wie in der Abbildung unten dargestellt. Siehe auch die Dokumentation zur [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager).

>[!TIP]
>
>Wenn Sie die Erweiterung [!DNL Adobe Analytics] installieren, *installieren Sie nicht* auch die Erweiterung [!DNL Audience Manager]. Die [!DNL Audience Manager]-Erweiterungsfunktion wird durch das Weiterleiten von Daten aus der [!DNL Analytics]-Erweiterung ersetzt.

![So aktivieren Sie die Datenfreigabe von der Adobe Analytics-Erweiterung auf Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## &lt; a0/> definierte Codeelemente{#code-elements-defined}

Die folgende Tabelle definiert wichtige Variablen im Codebeispiel.

| Parameter | Beschreibung |
|--- |--- |
| `partner` | Erforderlich. Dies ist ein Partnername, der Ihnen von [!DNL Adobe] zugewiesen wird. Es wird manchmal auch als [!UICONTROL partner ID]- oder Partner-Subdomäne bezeichnet.  Wenden Sie sich an Ihren [!DNL Adobe]-Berater oder [Kundendienst](https://helpx.adobe.com/de/marketing-cloud/contact-support.html), wenn Sie Ihren Partnernamen nicht kennen. |
| `containerNSID` | Erforderlich. Die meisten Kunden können einfach `"containerNSID":0` einstellen. Wenn Ihre Firma jedoch ID-Synchronisierungen mit einem anderen Container anpassen muss, können Sie diese Container-ID hier angeben. |
| `uuidCookie` | Optional. Mit dieser Konfiguration können Sie ein [!DNL Adobe]-Cookie in der Erstanbieterdomäne setzen. Dieses [!DNL cookie] enthält die [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Erforderlich. Der Parameter `namespace` ist erforderlich, wenn Sie das [!DNL AudienceManagement]-Modul verwenden, das mit [!UICONTROL AppMeasurement] Version 2.10 oder neuer integriert ist. Für dieses [!UICONTROL AudienceManagement]-Modul müssen Sie [!UICONTROL Adobe Experience Platform Identity Service] 3.3 oder höher verwenden. <br><br>Die ID  [!UICONTROL Experience Cloud Organization ID] ist die ID, die eine Firma bei der Anmeldung für die  [!UICONTROL Experience Cloud]ID bereitstellt. Informationen zur Organisations-ID Ihrer Firma finden Sie unter [Organisationen und Kontoverknüpfung](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Ergebnisse: Daten, die an [!DNL Audience Manager] {#results-data-forwarding} weitergeleitet werden

Ihre [!DNL Analytics]-Implementierung sendet Daten an [!DNL Audience Manager], nachdem Sie Folgendes haben:

* Aktiviert [!UICONTROL Server-Side Forwarding] (sprechen Sie mit Ihrem Berater über diese Funktion)
* Implementierung von [!DNL Adobe Experience Platform Identity Service];
* Folgen Sie den Implementierungsschritten in diesem Lernprogramm.

Dieser Prozess sendet Daten an [!DNL Audience Manager]:

* Bei Seitenaufrufen zur Ansicht;
* von verfolgten Links;
* Von Video-Meilenstein- und Heartbeat-Video-Ansichten.

>[!NOTE]
>
>Die Variablen, die von [!DNL Analytics] an [!DNL Audience Manager] gesendet werden, verwenden spezielle Präfixe. Sie müssen diese Präfixe verstehen und berücksichtigen, wenn Sie [!DNL Audience Manager]-Eigenschaften erstellen. Weitere Informationen zu diesen Präfixen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md).

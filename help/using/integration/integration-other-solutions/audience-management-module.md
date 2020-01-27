---
description: Fügen Sie das Zielgruppen-Management-Modul zu Adobe Analytics AppMeasurement hinzu, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager Data Integration Library (DIL)-Code ein Pixel von der Seite sendet.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Fügen Sie das Zielgruppen-Management-Modul zu Adobe Analytics AppMeasurement hinzu, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager Data Integration Library (DIL)-Code ein Pixel von der Seite sendet.
seo-title: Implementieren des Zielgruppen-Management-Moduls
solution: Audience Manager
title: Implementieren des Zielgruppen-Management-Moduls
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 7e8ba292f2f901b1323d30d682066b49df885a0c

---


# Weiterleiten von Daten von Adobe Analytics an Audience Manager {#implement-the-audience-management-module}

Führen Sie die Schritte in diesem Lernprogramm aus, um [!DNL Analytics] Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager-Code [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) ein Pixel von der Seite sendet.

>[!TIP]
>
>Es wird empfohlen, Daten [!UICONTROL Adobe Launch] an Audience Manager weiterzuleiten [!UICONTROL Analytics] . Durch die Verwendung [!UICONTROL Launch]müssen Sie keinen Code manuell in kopieren, wie auf dieser Seite gezeigt [!UICONTROL AppMeasurement].

## Voraussetzungen {#prereqs}

Zusätzlich zur Aktivierung der Erweiterungen oder Implementierung des in diesem Dokument beschriebenen Codes müssen Sie auch:

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Aktivieren Sie die [serverseitige Weiterleitung](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) für Report Suites im [!UICONTROL Adobe Analytics Admin Console].

## Implementierung {#implementation}

Es gibt zwei Methoden, um die Datenweiterleitung von Adobe Analytics an Audience Manager zu implementieren, je nachdem, welche Tag-Management-Lösung Sie verwenden.

### Implementierung mit Adobe Launch

Adobe empfiehlt, Adobe Analytics und Audience Manager mit der Erweiterung [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) zu instrumentieren. In diesem Fall müssen Sie keinen Code manuell kopieren. Stattdessen müssen Sie die Datenfreigabe in der Analytics Launch-Erweiterung aktivieren, wie in der folgenden Abbildung dargestellt. Siehe auch die Dokumentation zur [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Wenn Sie die Adobe Analytics-Erweiterung installieren, installieren Sie *nicht* auch die Audience Manager-Erweiterung. Das Weiterleiten von Daten aus der Analytics-Erweiterung ersetzt die Audience Manager-Erweiterungsfunktion.

![So aktivieren Sie die Datenfreigabe von der Adobe Analytics-Erweiterung auf Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementierung mit Adobe Digital Tag Management (DTM) oder einer anderen Tag-Management-Lösung


>[!WARNING]
>
>Adobe hat Pläne veröffentlicht, DTM bis Ende 2020 zu verlängern. Weitere Informationen und Termine finden Sie unter DTM-Pläne für einen Sunset in den [Adobe-Community-Foren](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

So implementieren Sie die [!UICONTROL Audience Management Module] Anwendung mit [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) oder einer anderen Tag-Management-Lösung:

1. Herunterladen [!UICONTROL AppMeasurement] mit dem [Analytics-Code-Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (Version 1.5 oder höher erforderlich).
1. Aktualisieren Sie Ihren [!UICONTROL AppMeasurement] Code auf die in der heruntergeladenen ZIP-Datei enthaltene Version.
1. Kopieren Sie den gesamten Code aus `AppMeasurement_Module_AudienceManagement.js` der ZIP-Datei. Fügen Sie sie in die `appMeasurement.js` Datei direkt über dem Text ein, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Fügen Sie den Code `s.loadModule("AudienceManagement");`direkt über dem `AppMeasurement_Module_AudienceManagement.js` Code hinzu, den Sie im vorherigen Schritt hinzugefügt haben.
1. Aktualisieren und kopieren Sie den unten stehenden Code und fügen Sie ihn der `doPlugins` Funktion in Ihrer `AppMeasurement.js` Datei hinzu.

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>Die `audienceManagement.setup` Funktion verwendet Parameter mit der `DIL.create` Funktion Audience Manager, die Sie in diesem Code konfigurieren können. Weitere Informationen zu diesen Parametern finden Sie unter [DIL-Erstellung](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code-Elemente definiert {#code-elements-defined}

Die folgende Tabelle definiert wichtige Variablen im Codebeispiel.

| Parameter | Beschreibung |
|--- |--- |
| `partner` | Erforderlich. Dies ist ein von Adobe zugewiesener Name des Partners. Manchmal wird sie als &quot;Partner-ID&quot;oder &quot;Partner-Subdomäne&quot;bezeichnet.  Wenden Sie sich an Ihren Adobe-Berater oder [Kundendienst](https://helpx.adobe.com/marketing-cloud/contact-support.html) , wenn Sie Ihren Partnernamen nicht kennen. |
| `containerNSID` | Erforderlich. Die meisten Kunden können einfach einstellen `"containerNSID":0` . Wenn Ihr Unternehmen jedoch ID-Synchronisierungen mit einem anderen Behälter anpassen muss, können Sie diese Behälter-ID hier angeben. |
| `uuidCookie` | Optional. Mit dieser Konfiguration können Sie ein Adobe-Cookie in der Erstanbieterdomäne einrichten. Dieses Cookie enthält die [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Erforderlich. Der `namespace` Parameter ist erforderlich, wenn Sie das AudienceManagement-Modul mit [!UICONTROL AppMeasurement] Version 2.10 oder neuer verwenden. Für dieses [!UICONTROL AudienceManagement] Modul müssen Sie [!UICONTROL Experience Cloud ID Service] 3.3 oder höher verwenden. <br> Die ID [!UICONTROL Experience Cloud Organization ID] ist die ID, die ein Unternehmen bei der Anmeldung für die [!UICONTROL Experience Cloud]ID erhält. Erfahren Sie mehr über die Organisations-ID Ihres Unternehmens in [Organisationen und Kontoverknüpfung](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Ergebnisse: Datenweiterleitung an Audience Manager {#results-data-forwarding}

Ihre [!DNL Analytics] Implementierung sendet Daten an Audience Manager, nachdem Sie Folgendes haben:

* Aktiviert [!UICONTROL Server-Side Forwarding] (sprechen Sie mit Ihrem Berater über diese Funktion)
* Experience Cloud ID-Dienst implementiert;
* Folgen Sie den Implementierungsschritten in diesem Lernprogramm.

Dieser Prozess sendet Daten an [!DNL Audience Manager]:

* Aufrufe bei Seitenansichten;
* von verfolgten Links;
* Von Video-Meilenstein- und Heartbeat-Videoansichten.

>[!NOTE]
>
>Die Variablen, die an Audience Manager gesendet werden, [!DNL Analytics] verwenden spezielle Präfixe. Sie müssen diese Präfixe beim Erstellen von Audience Manager-Eigenschaften verstehen und berücksichtigen. Weitere Informationen zu diesen Präfixen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md).
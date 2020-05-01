---
description: Hinzufügen Sie das Audience Management Module an Adobe Analytics AppMeasurement, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager Data Integration Library (DIL)-Code ein Pixel von der Seite sendet.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Hinzufügen Sie das Audience Management Module an Adobe Analytics AppMeasurement, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager Data Integration Library (DIL)-Code ein Pixel von der Seite sendet.
seo-title: Implementieren des Audience Management-Moduls
solution: Audience Manager
title: Implementieren des Audience Management-Moduls
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Weiterleiten von Daten von Adobe Analytics an Audience Manager {#implement-the-audience-management-module}

Führen Sie die in diesem Lernprogramm beschriebenen Schritte aus, um [!DNL Analytics] Daten an den Audience Manager weiterzuleiten, anstatt dass der Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL])-Code ein Pixel von der Seite sendet.

>[!TIP]
>
>Es wird empfohlen, die Daten [!DNL Adobe Experience Platform Launch] an den Audience Manager weiterzuleiten [!UICONTROL Analytics] . Durch die Verwendung [!UICONTROL Launch]müssen Sie keinen Code manuell in kopieren, wie auf dieser Seite gezeigt [!UICONTROL AppMeasurement].

## Voraussetzungen {#prereqs}

Zusätzlich zur Aktivierung der Erweiterungen oder Implementierung des in diesem Dokument beschriebenen Codes müssen Sie auch:

* Implementieren Sie den [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html).
* Aktivieren Sie die [serverseitige Weiterleitung](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) für Report Suites im [!UICONTROL Adobe Analytics Admin Console].

## Implementierung {#implementation}

Es gibt zwei Methoden, um die Datenweiterleitung von Adobe Analytics an Audience Manager zu implementieren, je nachdem, welche Tag-Management-Lösung Sie verwenden.

### Implementierung mit Adobe Experience Platform Launch

Adobe empfiehlt, Adobe Analytics und Audience Manager mit der Erweiterung [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) zu instrumentieren. In diesem Fall müssen Sie keinen Code manuell kopieren. Stattdessen müssen Sie die Datenfreigabe in der Analytics Launch-Erweiterung aktivieren, wie in der folgenden Abbildung dargestellt. Siehe auch die Dokumentation zur [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Wenn Sie die Adobe Analytics-Erweiterung installieren, installieren Sie *nicht* auch die Audience Manager-Erweiterung. Durch das Weiterleiten von Daten aus der Analytics-Erweiterung wird die Audience Manager-Erweiterungsfunktion ersetzt.

![So aktivieren Sie die Datenfreigabe von der Adobe Analytics-Erweiterung auf Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementierung mit Adobe Digital Tag Management (DTM) oder einer anderen Tag-Management-Lösung


>[!WARNING]
>
>Adobe hat Pläne veröffentlicht, DTM bis Ende 2020 zu verlängern. Weitere Informationen und Termine finden Sie unter DTM-Pläne für einen Sunset in den [Adobe-Community-Foren](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

So implementieren Sie die [!UICONTROL Audience Management Module] Anwendung mit [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) oder einer anderen Tag-Management-Lösung:

1. Herunterladen [!UICONTROL AppMeasurement] mit dem [Analytics-Code-Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html) (Version 1.5 oder höher erforderlich).
1. Aktualisieren Sie Ihren [!UICONTROL AppMeasurement] Code auf die Version, die in der heruntergeladenen ZIP-Datei enthalten ist.
1. Kopieren Sie den gesamten Code aus `AppMeasurement_Module_AudienceManagement.js` der ZIP-Datei. Fügen Sie sie in die `appMeasurement.js` Datei direkt über dem Text ein, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Hinzufügen den Code, `s.loadModule("AudienceManagement");`direkt über dem `AppMeasurement_Module_AudienceManagement.js` Code, den Sie gerade im vorherigen Schritt hinzugefügt haben.
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
>Die `audienceManagement.setup` Funktion verwendet Parameter gemeinsam mit der Audience Manager- `DIL.create` Funktion, die Sie in diesem Code konfigurieren können. Weitere Informationen zu diesen Parametern finden Sie unter [DIL-Erstellung](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code-Elemente definiert {#code-elements-defined}

Die folgende Tabelle definiert wichtige Variablen im Codebeispiel.

| Parameter | Beschreibung |
|--- |--- |
| `partner` | Erforderlich. Dies ist ein von Adobe zugewiesener Name des Partners. Manchmal wird sie als &quot;Partner-ID&quot;oder &quot;Partner-Subdomäne&quot;bezeichnet.  Wenden Sie sich an Ihren Adobe-Berater oder [Kundendienst](https://helpx.adobe.com/marketing-cloud/contact-support.html) , wenn Sie Ihren Partnernamen nicht kennen. |
| `containerNSID` | Erforderlich. Die meisten Kunden können einfach einstellen `"containerNSID":0` . Wenn Ihre Firma jedoch ID-Synchronisierungen mit einem anderen Container anpassen muss, können Sie diese Container-ID hier angeben. |
| `uuidCookie` | Optional. Mit dieser Konfiguration können Sie ein Adobe-Cookie in der Erstanbieterdomäne einrichten. Dieses Cookie enthält die [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Erforderlich. Der `namespace` Parameter ist erforderlich, wenn Sie das AudienceManagement-Modul mit [!UICONTROL AppMeasurement] Version 2.10 oder neuer verwenden. Für dieses [!UICONTROL AudienceManagement] Modul müssen Sie [!UICONTROL Adobe Experience Platform Identity Service] 3.3 oder höher verwenden. <br> Die ID [!UICONTROL Experience Cloud Organization ID] ist die ID, die eine Firma bei der Anmeldung für die [!UICONTROL Experience Cloud]ID bereitstellt. Erfahren Sie mehr über die Organisations-ID Ihrer Firma in [Organisationen und Kontoverknüpfung](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Ergebnisse: Datenübermittlung an Audience Manager {#results-data-forwarding}

Ihre [!DNL Analytics] Implementierung sendet Daten an Audience Manager, nachdem Sie:

* Aktiviert [!UICONTROL Server-Side Forwarding] (sprechen Sie mit Ihrem Berater über diese Funktion)
* Implementiert den Identitätsdienst für Adobe Experience Platform;
* Folgen Sie den Implementierungsschritten in diesem Lernprogramm.

Dieser Prozess sendet Daten an [!DNL Audience Manager]:

* Bei Seitenaufrufen zur Ansicht;
* von verfolgten Links;
* Von Video-Meilenstein- und Heartbeat-Video-Ansichten.

>[!NOTE]
>
>Die Variablen, die an Audience Manager gesendet werden, verwenden spezielle Präfixe [!DNL Analytics] . Sie müssen diese Präfixe beim Erstellen von Audience Manager-Eigenschaften verstehen und berücksichtigen. Weitere Informationen zu diesen Präfixen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md).
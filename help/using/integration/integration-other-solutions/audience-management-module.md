---
description: Fügen Sie das Zielgruppen-Management-Modul zu Adobe Analytics AppMeasurement hinzu, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager Data Integration Library (DIL)-Code ein Pixel von der Seite senden muss.
keywords: Audience Analytics; Analytics; SSF; Server-seitige Weiterleitung
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implementieren des Audience Management-Moduls
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---

# Weiterleiten von Daten von [!DNL Adobe Analytics] an [!DNL Audience Manager] {#implement-the-audience-management-module}

Führen Sie die Schritte in diesem Tutorial aus, um [!DNL Analytics] Daten an [!DNL Audience Manager] weiterzuleiten, anstatt den [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL])-Code ein Pixel von der Seite senden zu lassen.

>[!TIP]
>
>Es wird empfohlen, [!DNL Adobe Experience Platform Tags] zu verwenden, um [!UICONTROL Analytics] Daten an [!DNL Audience Manager] weiterzuleiten. Durch die Verwendung von [!UICONTROL Tags] müssen Sie -Code nicht manuell in [!DNL AppMeasurement] kopieren, wie auf dieser Seite dargestellt.

## Voraussetzungen {#prereqs}

Zusätzlich zur Aktivierung der Erweiterungen oder Implementierung des in diesem Dokument beschriebenen Codes müssen Sie auch Folgendes tun:

* Implementieren Sie den [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=de).
* Aktivieren [&#x200B; (Server-seitige Weiterleitung](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=de) für Report Suites im [!UICONTROL Adobe Analytics Admin Console].

## Implementierung {#implementation}

Je nach der verwendeten Tag-Management-Lösung gibt es zwei Methoden, um die Datenweiterleitung von [!DNL Adobe Analytics] an [!DNL Audience Manager] zu implementieren.

### Implementierung mithilfe von [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] empfiehlt die Verwendung der [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=de)-Erweiterung, um [!DNL Adobe Analytics] und [!DNL Audience Manager] in Ihren Eigenschaften zu instrumentieren. In diesem Fall müssen Sie keinen Code manuell kopieren. Stattdessen müssen Sie die Datenfreigabe in der [!DNL Analytics]-Erweiterung aktivieren, wie in der Abbildung unten dargestellt. Siehe auch die Dokumentation zur [Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=de#adobe-audience-manager)Erweiterung.

>[!TIP]
>
>Wenn Sie die [!DNL Adobe Analytics]-Erweiterung installieren *installieren Sie* auch die [!DNL Audience Manager]-Erweiterung. Die Weiterleitungsdaten aus der [!DNL Analytics]-Erweiterung ersetzen die Funktionalität der [!DNL Audience Manager]-Erweiterung.

![Aktivieren der Datenfreigabe von der Adobe Analytics-Erweiterung für Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Definierte Code-Elemente {#code-elements-defined}

In der folgenden Tabelle werden wichtige Variablen im Code-Beispiel definiert.

| Parameter | Beschreibung |
|--- |--- |
| `partner` | Erforderlich. Dies ist ein Partnername, der Ihnen von [!DNL Adobe] zugewiesen wurde. Dies wird manchmal als Ihre [!UICONTROL partner ID]- oder Partner-Subdomain bezeichnet.  Wenden Sie sich an Ihren [!DNL Adobe] oder [Kundenunterstützung](https://helpx.adobe.com/de/marketing-cloud/contact-support.html), wenn Sie Ihren Partnernamen nicht kennen. |
| `containerNSID` | Erforderlich. Die meisten Kunden können einfach `"containerNSID":0` festlegen. Wenn Ihr Unternehmen jedoch ID-Synchronisierungen mit einem anderen Container anpassen muss, können Sie diese Container-ID hier angeben. |
| `uuidCookie` | Optional. Mit dieser Konfiguration können Sie ein [!DNL Adobe]-Cookie in der Erstanbieter-Domain setzen. Dieses [!DNL cookie] enthält die [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Erforderlich. Der `namespace`-Parameter ist erforderlich, wenn Sie das [!DNL AudienceManagement]-Modul verwenden, das mit [!UICONTROL AppMeasurement] Version 2.10 oder neuer gebündelt ist. Dieses [!UICONTROL AudienceManagement] erfordert die Verwendung von [!UICONTROL Adobe Experience Platform Identity Service] 3.3 oder neuer. <br><br>Die [!UICONTROL Experience Cloud Organization ID] ist die ID, die einem Unternehmen bei der Anmeldung zum [!UICONTROL Experience Cloud] bereitgestellt wird. Erfahren Sie die Organisations-ID Ihres Unternehmens unter [Organisationen und Kontoverknüpfung](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=de). |

## Ergebnisse: Datenweiterleitung an [!DNL Audience Manager] {#results-data-forwarding}

Ihre [!DNL Analytics]-Implementierung sendet Daten an [!DNL Audience Manager], nachdem Sie Folgendes erreicht haben:

* [!UICONTROL Server-Side Forwarding] aktiviert (bitte mit Ihrem Berater über diese Funktion sprechen);
* die [!DNL Adobe Experience Platform Identity Service] umgesetzt hat;
* Die Implementierungsschritte in diesem Tutorial wurden befolgt.

Dieser Prozess sendet Daten an [!DNL Audience Manager]:

* Bei Seitenaufrufen;
* Von getrackten Links;
* Aus Video-Meilenstein- und Heartbeat-Videoansichten.

>[!NOTE]
>
>Die Variablen, die von [!DNL Audience Manager] an [!DNL Analytics] gesendet werden, verwenden spezielle Präfixe. Sie müssen diese Präfixe verstehen und berücksichtigen, wenn Sie [!DNL Audience Manager] Eigenschaften erstellen. Weitere Informationen zu diesen Präfixen finden Sie unter [Präfixanforderungen für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md).

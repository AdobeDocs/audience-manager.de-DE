---
description: Auf dieser Seite wird das Erstellen von WCA-Audiencen (Facebook Website Custom ) erläutert, um webbasierte Audience Manager-Audiencen an Facebook zu senden, damit das Targeting von Online-Anzeigen transparenter wird.
seo-description: Auf dieser Seite wird das Erstellen von WCA-Audiencen (Facebook Website Custom ) erläutert, um webbasierte Audience Manager-Audiencen an Facebook zu senden, damit das Targeting von Online-Anzeigen transparenter wird.
seo-title: Facebook-WCA-Integration
solution: Audience Manager
title: Facebook-WCA-Integration
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 2%

---


# [!DNL Facebook WCA] Integration {#facebook-wca-integration}

Auf dieser Seite wird das Erstellen von [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) Pixeln zum Senden von webbasierten [!DNL Audience Manager] Segmenten an [!DNL Facebook]das Targeting von Anzeigen mit verbesserter Transparenz veranschaulicht.

## Überblick {#overview}

[Mit den benutzerspezifischen Audiencen der Facebook-Website (WCA)](https://www.facebook.com/business/help/449542958510885) können Sie eine Liste von Personen erstellen, die bestimmte Seiten besucht oder bestimmte Aktionen auf Ihrer Website durchgeführt haben. [!DNL Audience Manager] ermöglicht die Aktivierung bei der [!DNL WCA] Verwendung von [!DNL URL] Zielen, mit denen Sie eine benutzerspezifische pixelbasierte Integration konfigurieren können, um webbasierte Audiencen für das Targeting zu senden [!DNL Facebook] .

![Facebook-WCA-Integration](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Für diese Funktion müssen Sie die Option [!UICONTROL Website] Audience für soziale Plattformen in [URL-Zielen](/help/using/features/destinations/create-url-destination.md)auswählen. Social-Plattformen erfordern, dass die Werber-Informationen beim Versand an ihre Plattform nicht maskiert werden. Bitte beachten Sie, dass dies bedeutet, dass die Zielplattform/der Zielpartner Informationen in Ihrem Werber sehen kann [!DNL URL].

## Voraussetzungen {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] Segmente, die für die Zuweisung zu Ihrem neuen [!DNL Facebook] Ziel bereit sind. Hier [erfahren Sie, wie Sie ein Segment](/help/using/features/segments/segment-builder.md) in der [!DNL Audience Manager] Benutzeroberfläche erstellen.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 oder neuer. Laden Sie die neueste Version **[hier](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**herunter.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) Version 9.0 oder neuer, von **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**herunterzuladen. Wenn Sie zum Importieren von Daten auch[serverseitige Weiterleitungen (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)verwenden,[!DNL Audience Manager]müssen Sie AppMeasurement Version 2.12 oder höher verwenden. Herunterladen[!DNL AppMeasurement]mit dem[Analytics Code-Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).

Es wird empfohlen, die Bibliotheken in den Schritten 3 und 4 mithilfe von [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) oder [Adobe Dynamisches Tag-Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html)zu installieren oder zu aktualisieren.

## Schritt 1: Erstellen Sie eine [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Erstellen Sie ein neues [!UICONTROL URL Destination] in [!DNL Audience Manager] und benennen Sie es [!DNL Facebook Website Custom Audiences]. Verwenden Sie beim Erstellen des Ziels die unten stehenden Einstellungen. Sie können auch auf der Seite &quot;URL-Ziel [konfigurieren&quot;nachsehen](/help/using/features/destinations/create-url-destination.md) .

### Basisinformationen

* **[!UICONTROL Category]**: Benutzerspezifisch
* **[!UICONTROL Type]**: [!DNL URL]
* Aktivieren Sie das **[!UICONTROL Auto-fill Destination Mapping]** Kontrollkästchen und wählen Sie dann **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Select the option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Diese Exportbezeichnung verhindert, dass Daten von Drittanbietern und Daten aus Gerätediagrammen in die Segmente aufgenommen werden.

### Konfiguration

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Durch Auswahl dieser [!UICONTROL URL Type] Option werden die Informationen zum Werber [!DNL Audience Manager] beim [!DNL URL] Auslösen eines [!DNL Facebook WCA] Pixels nicht verdeckt.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* Geben Sie im Feld **[!UICONTROL Base URL]** und **[!UICONTROL Secure URL]** das [!DNL Facebook WCA] Pixel ein.
* **[!UICONTROL Delimiter]**: `,`

Basisbeispiel [!DNL URL] : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Beispiel eines Pixels, das von der Seite ausgelöst wird. Dieses Beispiel zeigt einen Benutzer, der für drei [!DNL Audience Manager] Segmente qualifiziert ist, mit den IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beschreibung |
---------|----------|
| `id` | Ihre [!DNL Facebook] Pixel-ID, die Sie in der [!DNL Facebook Ad Manager] Benutzeroberfläche finden können, wenn Sie Pixel für die Audience erstellen. |
| `ev` | Event.     Dies ist ein beliebiger Wert, der in der [!DNL Facebook Ad Manager] Benutzeroberfläche angezeigt wird, sobald das Pixel auf der Site ausgelöst wird. Weitere Informationen finden Sie unter [!UICONTROL Include] Element in [Schritt 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Ein zusätzlicher Parameter, der in der [!DNL Facebook Ad Manager] Benutzeroberfläche gefüllt wird, sobald das Pixel auf der Site ausgelöst wird. `segID` ist auch willkürlich. |
| `%ALIAS%` | Ein [!DNL Audience Manager] Makro, das dynamisch durch die [!DNL Audience Manager] [!UICONTROL segment] IDs ersetzt wird, für die sich der Site-Besucher qualifiziert, mit Komma, |

Die [!UICONTROL URL destination] Konfiguration sollte wie in der folgenden Abbildung aussehen:

![Zielkonfiguration](/help/using/integration/assets/facebook-wca.png)

Speichern Sie die [!UICONTROL destination]. Anschließend können Sie mit dem Schritt **Segmentzuordnungen** fortfahren.

## Schritt 2 - Segmentzuordnungen - Segment dem Ziel zuordnen {#step-2-segment-mappings}

Ordnen Sie im Arbeitsablauf [URL-Ziel](/help/using/features/destinations/create-url-destination.md) konfigurieren das entsprechende Segment Ihrem neu erstellten zu [!UICONTROL destination]. Beachten Sie, dass der Zuordnungswert automatisch mit dem [!DNL Audience Manager] Wert gefüllt wird [!UICONTROL segment ID].

Geben Sie ggf. ein Enddatum ein, andernfalls leer lassen, wenn kein Enddatum angegeben ist.

## Schritt 3: Erstellen eines [!UICONTROL Audience] In [!DNL Facebook Ads Manager] {#step-3-create-audience}

Siehe [Erstellen einer benutzerspezifischen Website-Audience](https://www.facebook.com/business/help/666509013483225) in der [!DNL Facebook] Hilfedokumentation. Wählen Sie die [!UICONTROL Create Audience] Optionen in der folgenden Tabelle aus:

| Element | Beschreibung |
---------|----------|
| Website-Traffic | Benutzerdefinierte Kombination |
| Einschließlich | <ul><li>Wählen Sie **[!UICONTROL Event]** > Auswählen **[!UICONTROL Adobe-Audience-Manager-Segment]**. Dies war der Wert des `ev` Parameters im Beispielpixel in Schritt 1. Beachten Sie, dass die Option oder die Option in der Benutzeroberfläche angezeigt werden **[!UICONTROL Event]** kann, wenn das Pixel noch nicht ausgelöst wird oder **[!UICONTROL Adobe-Audience-Manager-Segment]** nicht [!DNL Facebook] .</li><li>Hinzufügen eines Parameters: Wählen Sie `segID`.</li><li><p>Wählen Sie den Operator **enthält** .</p><p>Dies ist angesichts der Tatsache, dass Besucher für mehrere Segmente qualifiziert sein können, wichtig, da [!UICONTROL segment IDs] der Pixelparameter möglicherweise mehrere Segmente enthält. Die Verwendung des Operators &quot;Gleich&quot;(`=`) kann Ihre Besucher nicht für die Audience qualifizieren, und Sie werden eine niedrigere Lautstärke beobachten.</p></li><li>Hinzufügen einen Wert: Geben Sie die [!DNL Audience Manager] Segment-ID ein.</li></ul> |
| Hinzufügen neue Bedingung | Optionale Einstellung. |
| Im letzten | Optionale Einstellung. |
| Name der Audience | Es wird empfohlen, denselben [!DNL Audience Manager] Segmentnamen zur Konsistenz zu verwenden, es sei denn, Sie fügen dieser Audience zusätzliche Bedingungen hinzu. |

## Schritt 4: Zuweisen des [!UICONTROL Audience] Formulars zu einem [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Weisen Sie die [!DNL Custom Audience]Anzeige nach dem Erstellen einer Kampagne zu. Erstellen Sie eine neue Kampagne oder bearbeiten Sie eine vorhandene, und Sie finden, dass Ihre neu erstellte Audience in der [!DNL Facebook] Benutzeroberfläche aufgelistet ist. Ihre Kampagne der Anzeige Zielgruppe Benutzer, die beim Besuch Ihrer Site das Pixelfeuer auf ihrem Browser gesehen haben, sofern diese in das Segment einbezogen [!DNL Audience Manager] werden.

## Zusammenfassung {#summary}

Nachdem Sie Ihr [!DNL Audience Manager] Segment nun dem [!DNL Facebook WCA] Ziel zugewiesen haben, [!DNL Audience Manager] wird das [!DNL Facebook WCA] Pixel selektiv an Benutzer eines bestimmten Segments mit der entsprechenden Segment-ID in Pixel ausgelöst, um das Segment zu füllen [!DNL Facebook Audience]. Dies führt zu einem allmählichen Anstieg, je mehr [!DNL Facebook Audience] das Tag auf die entsprechende Audience Ihrer Site ausgelöst wird.

>[!NOTE]
>
> Wenn ein Benutzer aus dem [!DNL Audience Manager] Segment herausfällt, gibt es derzeit keine Möglichkeit, ihn zu [!DNL Audience Manager] informieren, [!DNL Facebook] um ihn aus dem Segment zu entfernen [!DNL Custom Audience].


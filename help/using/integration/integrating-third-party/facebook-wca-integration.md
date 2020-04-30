---
description: Auf dieser Seite wird der Vorgang zum Erstellen von WCA-Pixeln (Facebook Website Custom Audiencen) erläutert, um webbasierte Audience Manager-Audiencen an Facebook zu senden und damit das Targeting von Online-Anzeigen mit verbesserter Transparenz zu ermöglichen.
seo-description: Auf dieser Seite wird der Vorgang zum Erstellen von WCA-Pixeln (Facebook Website Custom Audiencen) erläutert, um webbasierte Audience Manager-Audiencen an Facebook zu senden und damit das Targeting von Online-Anzeigen mit verbesserter Transparenz zu ermöglichen.
seo-title: Facebook-WCA-Integration
solution: Audience Manager
title: Facebook-WCA-Integration
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Facebook-WCA-Integration {#facebook-wca-integration}

Auf dieser Seite wird der Vorgang zum Erstellen von WCA-Pixeln (Facebook Website Custom Audiencen) erläutert, um webbasierte Audience Manager-Audiencen an Facebook zu senden und damit das Targeting von Online-Anzeigen mit verbesserter Transparenz zu ermöglichen.

## Überblick {#overview}

[Mit den benutzerspezifischen Audiencen der Facebook-Website (WCA)](https://www.facebook.com/business/help/449542958510885) können Sie eine Liste von Personen erstellen, die bestimmte Seiten besucht oder bestimmte Aktionen auf Ihrer Website durchgeführt haben. Audience Manager ermöglicht die Aktivierung in WCA mithilfe von URL-Zielen, mit denen Sie eine benutzerspezifische pixelbasierte Integration konfigurieren können, um webbasierte Audiencen zum Targeting an Facebook zu senden.

![Facebook-WCA-Integration](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Für diese Funktion müssen Sie die Option &quot;Website-Audience für soziale Plattformen&quot;in [URL-Zielen](/help/using/features/destinations/create-url-destination.md)auswählen. Social-Plattformen erfordern, dass die Werber-Informationen beim Versand an ihre Plattform nicht maskiert werden. Bitte beachten Sie, dass dies bedeutet, dass die Zielplattform/der Zielpartner Informationen in Ihrer Werber-URL sehen kann.

## Voraussetzungen {#prerequisites}

1. Facebook-Anzeigenkonto
2. Audiencen-Manager-Segmente, die Ihrem neuen Facebook-Ziel zugewiesen werden können. Hier [erfahren Sie, wie Sie ein Segment](/help/using/features/segments/segment-builder.md) in der Benutzeroberfläche von Audience Manager erstellen.
3. Adobe Experience Platform Identity Service (ECID) Version 4.1.0 oder neuer. Laden Sie die neueste Version **[hier](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**herunter.
4. Audience Manager Data Integration Library (DIL) Version 9.0 oder neuer, **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**herunterzuladen. Wenn Sie zum Importieren von Daten in Audience Manager[serverseitige Weiterleitungen (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)verwenden, müssen Sie stattdessen AppMeasurement Version 2.12 oder höher verwenden. Laden Sie AppMeasurement mit dem[Analytics-Code-Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)herunter.

Es wird empfohlen, die Bibliotheken in den Schritten 3 und 4 mithilfe von [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) oder [Adobe Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html)zu installieren oder zu aktualisieren.

## Schritt 1: Erstellen eines Facebook-Ziels in Audience Manager {#step-1-create-facebook-destination}

Erstellen Sie im Audiencen-Manager ein neues URL-Ziel und geben Sie ihm einen Namen für benutzerdefinierte Audiencen der Facebook-Website. Verwenden Sie beim Erstellen des Ziels die unten stehenden Einstellungen. Sie können auch auf der Seite &quot;URL-Ziel [konfigurieren&quot;nachsehen](/help/using/features/destinations/create-url-destination.md) .

**Basisinformationen**

* **Kategorie**: Benutzerdefiniert
* **Typ**: URL
* Aktivieren Sie das Kontrollkästchen Zielzuordnung **automatisch ausfüllen** und wählen Sie dann **Segment-ID** aus.

**Datenexportbeschriftungen**

Wählen Sie die Option **Dieses Ziel kann eine Kombination mit persönlich identifizierbaren Informationen (PII)** aktivieren.

>[!NOTE]
>
> Diese Exportbezeichnung verhindert, dass Daten von Drittanbietern und Daten aus Gerätediagrammen in die Segmente aufgenommen werden.

**Konfiguration**

* **URL-Typ**: Wählen Sie **Website-Audience für soziale Plattformen**. Wenn Sie diese Option für den URL-Typ auswählen, verdeckt Audience Manager beim Auslösen eines Facebook-WCA-Pixels nicht die URL-Informationen des Werbers.
* **Serialisieren**: Wählen Sie **Aktivieren**.
* Geben Sie im Feld **Basis-URL** und **Sichere URL** das Facebook-WCA-Pixel ein.
* **Trennzeichen**: ,

Beispiel für eine Basis-URL: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Beispiel eines Pixels, das von der Seite ausgelöst wird. Dieses Beispiel zeigt einen Benutzer, der für drei Audience Manager-Segmente qualifiziert ist, mit den IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parameter | Beschreibung |
---------|----------|
| `id` | Ihre Facebook-Pixel-ID, die Sie in der Benutzeroberfläche von Facebook Ad Manager finden können, wenn Sie Audiencen-Pixel erstellen. |
| `ev` | Ereignis. Dies ist ein beliebiger Wert, der in der Benutzeroberfläche von Facebook Ad Manager angezeigt wird, sobald das Pixel auf der Site ausgelöst wird. Weitere Informationen finden Sie unter Einbeziehen in [Schritt 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Ein zusätzlicher Parameter, der in der Benutzeroberfläche von Facebook Ad Manager gefüllt wird, sobald das Pixel auf der Site ausgelöst wird. `segID` ist auch willkürlich. |
| `%ALIAS%` | Ein Audience Manager-Makro, das dynamisch durch die Audience Manager-Segment-IDs ersetzt wird, für die sich der Site-Besucher qualifiziert, durch Komma getrennt, |

Die URL-Zielkonfiguration sollte wie in unten stehender Abbildung aussehen:

![Zielkonfiguration](/help/using/integration/assets/facebook-wca.png)

Speichern Sie das Ziel. Anschließend können Sie mit dem Schritt **Segmentzuordnungen** fortfahren.

## Schritt 2 - Segmentzuordnungen - Segment dem Ziel zuordnen {#step-2-segment-mappings}

Ordnen Sie im Arbeitsablauf zum [Konfigurieren des URL-Ziels](/help/using/features/destinations/create-url-destination.md) das entsprechende Segment Ihrem neu erstellten Ziel zu. Beachten Sie, dass der Zuordnungswert automatisch mit der Segment-ID von Audience Manager ausgefüllt wird.

Geben Sie ggf. ein Enddatum ein, andernfalls leer lassen, wenn kein Enddatum angegeben ist.

## Schritt 3: Erstellen einer Audience im Facebook Ads Manager {#step-3-create-audience}

Siehe [Erstellen einer benutzerspezifischen Website-Audience](https://www.facebook.com/business/help/666509013483225) in der Facebook-Hilfedokumentation. Wählen Sie in der unten stehenden Tabelle die Optionen Audience erstellen aus:


| Element | Beschreibung |
---------|----------|
| Website-Traffic | Benutzerdefinierte Kombination |
| Einschließlich | <ul><li>Wählen Sie **Ereignis** > **Adobe-Audience-Manager-Segment** auswählen. Dies war der Wert des Parameters ev im Beispielpixel in Schritt 1. Beachten Sie, dass die Option &quot; **Ereignis** &quot;oder &quot; **Adobe-Audience-Manager-Segment** &quot;in der Facebook-Benutzeroberfläche möglicherweise nicht angezeigt wird, wenn das Pixel noch nicht ausgelöst wird.</li><li>Hinzufügen eines Parameters: Wählen Sie `segID`.</li><li><p>Wählen Sie den Operator **enthält** .</p><p>Dies ist wichtig, da sich Besucher für mehrere Segmente qualifizieren können, kann es mehrere Segment-IDs im Pixelparameter geben. Die Verwendung des Operators Gleich (=) qualifiziert Ihre Besucher möglicherweise nicht für die Audience, und Sie werden eine niedrigere Lautstärke beobachten.</p></li><li>Hinzufügen einen Wert: Geben Sie die Segment-ID des Audience-Managers ein.</li></ul> |
| Hinzufügen neue Bedingung | Optionale Einstellung. |
| Im letzten | Optionale Einstellung. |
| Name der Audience | Es wird empfohlen, denselben Segmentnamen des Audience-Managers für Konsistenz zu verwenden, es sei denn, Sie fügen dieser Audience zusätzliche Bedingungen hinzu. |

## Schritt 4: Zuweisen der Audience zu einer Kampagne im Facebook Ads Manager {#step-4-assign-audience-to-campaign}

Nachdem Sie die benutzerdefinierte Audience erstellt haben, weisen Sie sie einer Kampagne der Anzeige zu. Erstellen Sie eine neue Kampagne oder bearbeiten Sie eine vorhandene, und Ihre neu erstellte Audience wird in der Facebook-Benutzeroberfläche aufgelistet. Ihre Kampagne der Anzeige Zielgruppe Benutzer, die beim Besuch Ihrer Site das Pixelfeuer in ihrem Browser gesehen haben, sofern Audience Manager sie in das Segment einbezieht.

## Zusammenfassung {#summary}

Nachdem Sie das Segment &quot;Audience-Manager&quot;nun dem Facebook-WCA-Ziel zugewiesen haben, löst Audience Manager das Facebook-WCA-Pixel selektiv an Benutzer eines bestimmten Segments aus, wobei die entsprechende Segment-ID in Pixel angegeben wird, um die Facebook-Audience zu füllen. Dies führt zu einem allmählichen Anstieg der Facebook-Audience, je mehr das Tag auf die entsprechende Audience Ihrer Site ausgelöst wird.

>[!NOTE]
>
> Wenn ein Benutzer aus dem Segment &quot;Audience-Manager&quot;herausfällt, kann der Audience-Manager Facebook derzeit nicht darüber informieren, dass der Benutzer aus der Audience &quot;Benutzerdefiniert&quot;entfernt wird.


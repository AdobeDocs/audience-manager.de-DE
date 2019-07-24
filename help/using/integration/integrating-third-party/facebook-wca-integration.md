---
description: Diese Seite illustriert den Vorgang der Erstellung benutzerdefinierter Facebook-Zielgruppen (WCA)-Pixel zum Versand webbasierter Audience Manager-Zielgruppensegmente an Facebook für das Online-Anzeigen-Targeting mit verbesserter Transparenz.
seo-description: Diese Seite illustriert den Vorgang der Erstellung benutzerdefinierter Facebook-Zielgruppen (WCA)-Pixel zum Versand webbasierter Audience Manager-Zielgruppensegmente an Facebook für das Online-Anzeigen-Targeting mit verbesserter Transparenz.
seo-title: Facebook WCA-Integration
solution: Audience Manager
title: Facebook WCA-Integration
translation-type: tm+mt
source-git-commit: 56999c1968a486bed0e2e672a4de1774d049e09d

---


# Facebook WCA Integration {#facebook-wca-integration}

Diese Seite illustriert den Vorgang der Erstellung benutzerdefinierter Facebook-Zielgruppen (WCA)-Pixel zum Versand webbasierter Audience Manager-Zielgruppensegmente an Facebook für das Online-Anzeigen-Targeting mit verbesserter Transparenz.

## Überblick {#overview}

[Mit benutzerdefinierten Zielgruppen (WCA) für Facebook](https://www.facebook.com/business/help/449542958510885) können Sie eine Liste der Personen erstellen, die bestimmte Seiten besucht oder bestimmte Aktionen auf Ihrer Website unternommen haben. Audience Manager aktiviert die Aktivierung in WCA mithilfe von URL-Zielen, mit denen Sie eine benutzerdefinierte pixelbasierte Integration konfigurieren können, um webbasierte Zielgruppen an Facebook für das Targeting zu senden.

![Facebook WCA-Integration](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> This capability requires that you select the Website audience for social platforms option in [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination). Soziale Plattformen erfordern, dass Referrer-Informationen nicht maskiert werden, wenn sie an ihre Plattform gesendet werden. Beachten Sie, dass das bedeutet, dass die Zielplattform/-partner Informationen in Ihrer Referrer-URL anzeigen kann.

## Voraussetzungen {#prerequisites}

1. Facebook-Anzeigenkonto
2. Audience Manager-Segmente bereit, die Sie Ihrem neuen Facebook-Ziel zuweisen können. Here is [how to create a segment](/help/using/features/segments/segment-builder.md) in the Audience Manager UI.
3. Adobe Experience Cloud ID-Dienst (ECID) Version 4.1.0 oder neuer. Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternatively, if you use [Server-Side Forwarding (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to import data into Audience Manager, you must use AppMeasurement version 2.12 or newer. Download AppMeasurement using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

We recommend that you install or upgrade the libraries in steps 3 and 4 using [Adobe Launch](https://docs.adobelaunch.com/) or [Adobe Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Step 1 - Create a Facebook Destination in Audience Manager {#step-1-create-facebook-destination}

Erstellen Sie in Audience Manager ein neues URL-Ziel und geben Sie ihm benutzerdefinierte Zielgruppen für Facebook ein. Verwenden Sie die folgenden Einstellungen, wenn Sie das Ziel erstellen. You can also refer to the [Configure a URL Destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) page.

**Basisinformationen**

* **Kategorie**: Benutzerspezifisch
* **Typ**: URL
* Select the **Auto-fill Destination Mapping** check box, then select **Segment ID**.

**Datenexportbeschriftungen**

Select the option **This destination may enable a combination with personally identifiable information (PII)**.

>[!NOTE]
>
> Diese Exportbezeichnung verhindert, dass Daten von Drittanbietern und aus Gerätediagrammen abgeleitete Daten in die Segmente aufgenommen werden.

**Konfiguration**

* **URL-Typ**: Wählen **Sie die Zielgruppe "Website" für soziale Plattformen** aus. Durch Auswahl dieser Option "URL-Typ" verdeckt Audience Manager die URL-Informationen der verweisenden Stelle beim Auslösen eines Facebook-WCA-Pixels nicht.
* **Serialisieren**: Wählen Sie **Aktivieren**.
* In the **Base URL** and **Secure URL** field, enter the Facebook WCA pixel.
* **Trennzeichen**: ,

Base URL example: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Beispiel für ein aus der Seite ausgelöstes Pixel. Dieses Beispiel zeigt einen Benutzer, der sich für drei Audience Manager-Segmente qualifiziert, mit den IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parameter | Beschreibung |
---------|----------|
| `id` | Ihre Facebook-Pixel-ID, die Sie in der Benutzeroberfläche von Facebook Ad Manager finden können, wenn Sie Zielgruppenpixel erstellen. |
| `ev` | Ereignis. Dies ist ein beliebiger Wert, der in der Benutzeroberfläche von Facebook Ad Manager angezeigt wird, sobald das Pixel auf der Site ausgelöst wird. See the Include item in [Step 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), for more information. |
| `cd[segID]` | Ein weiterer Parameter, der beginnt, innerhalb der Facebook Ad Manager-Benutzeroberfläche auszufüllen, sobald das Pixel auf der Site ausgelöst wird. `segID` ist auch willkürlich. |
| `%ALIAS%` | Ein Audience Manager-Makro, das dynamisch durch die Segment Manager-Segment-IDs ersetzt wird, für die der Site-Besucher qualifiziert ist, durch Komma getrennt wird, |

Ihre URL-Zielkonfiguration sollte wie folgt aussehen:

![Konfiguration der Destintion](/help/using/integration/assets/facebook-wca.png)

Speichern Sie das Ziel. Then, you can proceed to the **Segment Mappings** step.

## Step 2 - Segment Mappings - Map Segment to Destination {#step-2-segment-mappings}

In the [Configure URL destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) workflow, map the applicable segment to your newly created destination. Beachten Sie, dass der Zuordnungswert automatisch mit der Segment-Manager-Segment-ID ausgefüllt wird.

Geben Sie ggf. ein Enddatum ein, andernfalls leer lassen Sie das Enddatum.

## Step 3 - Create an Audience within Facebook Ads Manager {#step-3-create-audience}

See [Create a Website Custom Audience](https://www.facebook.com/business/help/666509013483225) in the Facebook help documentation. Wählen Sie in der Tabelle unten die Option Zielgruppe erstellen:


| Element | Beschreibung |
---------|----------|
| Website-Traffic | Benutzerdefinierte Kombination |
| Einschließlich | <ul><li>Select **Event** &gt; Select **Adobe-Audience-Manager-Segment**. Dies war der Wert des ev-Parameters im Beispiel-Pixel in Schritt 1. Note that if the pixel is yet to fire, the **Event** option or **Adobe-Audience-Manager-Segment** may not appear in the Facebook UI.</li><li>Add a parameter: Select `segID`.</li><li><p>Select the **contains** operator.</p><p>Dies ist wichtig, wenn sich Besucher für mehrere Segmente qualifizieren können. Es kann mehrere Segment-IDs im Pixel-Parameter geben. Die Verwendung des Gleichheitsoperators (=) qualifiziert Ihre Besucher möglicherweise nicht für die Zielgruppe und Sie werden ein geringeres Volumen beobachten.</p></li><li>Fügen Sie einen Wert hinzu: Geben Sie die Segment-ID des Audience Manager ein.</li></ul> |
| Neue Bedingung hinzufügen | Optionale Einstellung. |
| Im letzten | Optionale Einstellung. |
| Zielgruppenname | Wir empfehlen, dass Sie denselben Segmentnamen für Audience Manager für Konsistenz verwenden, es sei denn, Sie fügen dieser Zielgruppe zusätzliche Bedingungen hinzu. |

## Step 4 - Assign the Audience to a Campaign in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

Nachdem Sie die benutzerspezifische Zielgruppe erstellt haben, weisen Sie sie einer Werbekampagne zu. Erstellen Sie eine neue Kampagne oder bearbeiten Sie eine vorhandene, und Sie finden Ihre neu erstellte Zielgruppe in der Facebook-Benutzeroberfläche. Ihre Werbekampagne zielt auf Benutzer ab, die das Pixel in ihrem Browser beim Besuch Ihrer Site gesehen haben, wenn Audience Manager diese im Segment enthält.

## Zusammenfassung {#summary}

Nachdem Sie Ihr Audience Manager-Segment dem Facebook WCA-Ziel zugewiesen haben, löst Audience Manager das Facebook WCA-Pixel für Benutzer eines bestimmten Segments mit der entsprechenden Segment-ID im Pixel selektiv aus, um die Facebook-Zielgruppe auszufüllen. Dies führt zu einem allmählichen Anstieg der Facebook-Zielgruppe, je mehr das Tag auf die entsprechende Zielgruppe auf Ihrer Site ausgelöst wird.

>[!NOTE]
>
> Wenn ein Benutzer aus dem Audience Manager-Segment ausfällt, gibt es derzeit keine Möglichkeit für Audience Manager, Facebook zu benachrichtigen, um den Benutzer aus der benutzerdefinierten Zielgruppe zu entfernen.


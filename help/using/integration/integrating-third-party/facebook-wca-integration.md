---
description: Diese Seite illustriert den Vorgang der Erstellung benutzerdefinierter Facebook-Zielgruppen (WCA)-Pixel zum Versand webbasierter Audience Manager-Zielgruppensegmente an Facebook für das Online-Anzeigen-Targeting mit verbesserter Transparenz.
seo-description: Diese Seite illustriert den Vorgang der Erstellung benutzerdefinierter Facebook-Zielgruppen (WCA)-Pixel zum Versand webbasierter Audience Manager-Zielgruppensegmente an Facebook für das Online-Anzeigen-Targeting mit verbesserter Transparenz.
seo-title: Facebook WCA-Integration
solution: Audience Manager
title: Facebook WCA-Integration
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Facebook WCA-Integration {#facebook-wca-integration}

Diese Seite illustriert den Vorgang der Erstellung benutzerdefinierter Facebook-Zielgruppen (WCA)-Pixel zum Versand webbasierter Audience Manager-Zielgruppensegmente an Facebook für das Online-Anzeigen-Targeting mit verbesserter Transparenz.

## Überblick {#overview}

[Mit benutzerdefinierten Zielgruppen (WCA) für Facebook](https://www.facebook.com/business/help/449542958510885) können Sie eine Liste der Personen erstellen, die bestimmte Seiten besucht oder bestimmte Aktionen auf Ihrer Website unternommen haben. Audience Manager aktiviert die Aktivierung in WCA mithilfe von URL-Zielen, mit denen Sie eine benutzerdefinierte pixelbasierte Integration konfigurieren können, um webbasierte Zielgruppen an Facebook für das Targeting zu senden.

![Facebook WCA-Integration](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Diese Funktion erfordert, dass Sie [in URL-Zielen die Zielgruppe Website für die Option Social-Plattformen auswählen](/help/using/features/destinations/create-url-destination.md). Soziale Plattformen erfordern, dass Referrer-Informationen nicht maskiert werden, wenn sie an ihre Plattform gesendet werden. Beachten Sie, dass das bedeutet, dass die Zielplattform/-partner Informationen in Ihrer Referrer-URL anzeigen kann.

## Voraussetzungen {#prerequisites}

1. Facebook-Anzeigenkonto
2. Audience Manager-Segmente bereit, die Sie Ihrem neuen Facebook-Ziel zuweisen können. So erstellen Sie [ein Segment](/help/using/features/segments/segment-builder.md) in der Benutzeroberfläche von Audience Manager.
3. Adobe Experience Cloud ID-Dienst (ECID) Version 4.1.0 oder neuer. Laden Sie die neueste Version **[hier herunter](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Audience Manager Data Integration Library (DIL) Version 9.0 oder neuer, herunterladbar von **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Wenn Sie zum Importieren von Daten in Audience Manager die [serverseitige Weiterleitung (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) verwenden, müssen Sie alternativ appmeasurement Version 2.12 oder neuer verwenden. Laden Sie appmeasurement mit dem [Analytics Code-Manager herunter](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

Wir empfehlen, die Bibliotheken in den Schritten 3 und 4 mithilfe von [Adobe Launch](https://docs.adobelaunch.com/) oder [Adobe Dynamisches Tag-Management zu installieren oder zu aktualisieren](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Schritt 1: Erstellen eines Facebook-Ziels in Audience Manager {#step-1-create-facebook-destination}

Erstellen Sie in Audience Manager ein neues URL-Ziel und geben Sie ihm benutzerdefinierte Zielgruppen für Facebook ein. Verwenden Sie die folgenden Einstellungen, wenn Sie das Ziel erstellen. Sie können auch auf die [Seite URL-Ziel](/help/using/features/destinations/create-url-destination.md) konfigurieren verweisen.

**Basisinformationen**

* **Kategorie**: Benutzerspezifisch
* **Typ**: URL
* Aktivieren Sie **das Kontrollkästchen Zielzuordnung** für automatisches Ausfüllen und wählen **Sie Segment-ID**.

**Datenexportbeschriftungen**

Wählen Sie die Option **Dieses Ziel, um eine Kombination mit persönlich identifizierbaren Informationen (PII) zu aktivieren**.

>[!NOTE]
>
> Diese Exportbezeichnung verhindert, dass Daten von Drittanbietern und aus Gerätediagrammen abgeleitete Daten in die Segmente aufgenommen werden.

**Konfiguration**

* **URL-Typ**: Wählen **Sie die Zielgruppe "Website" für soziale Plattformen** aus. Durch Auswahl dieser Option "URL-Typ" verdeckt Audience Manager die URL-Informationen der verweisenden Stelle beim Auslösen eines Facebook-WCA-Pixels nicht.
* **Serialisieren**: Wählen Sie **Aktivieren**.
* Geben Sie im Feld **Basis-URL** und **sichere URL** das Facebook WCA-Pixel ein.
* **Trennzeichen**: ,

Beispiel für Basis-URL: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Beispiel für ein aus der Seite ausgelöstes Pixel. Dieses Beispiel zeigt einen Benutzer, der sich für drei Audience Manager-Segmente qualifiziert, mit den IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parameter | Beschreibung |
---------|----------|
| `id` | Ihre Facebook-Pixel-ID, die Sie in der Benutzeroberfläche von Facebook Ad Manager finden können, wenn Sie Zielgruppenpixel erstellen. |
| `ev` | Ereignis. Dies ist ein beliebiger Wert, der in der Benutzeroberfläche von Facebook Ad Manager angezeigt wird, sobald das Pixel auf der Site ausgelöst wird. Weitere Informationen finden Sie im Einschließenden Element [in Schritt 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Ein weiterer Parameter, der beginnt, innerhalb der Facebook Ad Manager-Benutzeroberfläche auszufüllen, sobald das Pixel auf der Site ausgelöst wird. `segID` ist auch willkürlich. |
| `%ALIAS%` | Ein Audience Manager-Makro, das dynamisch durch die Segment Manager-Segment-IDs ersetzt wird, für die der Site-Besucher qualifiziert ist, durch Komma getrennt wird, |

Ihre URL-Zielkonfiguration sollte wie folgt aussehen:

![Konfiguration der Destintion](/help/using/integration/assets/facebook-wca.png)

Speichern Sie das Ziel. Anschließend können Sie mit dem Schritt **"Segmentzuordnungen** " fortfahren.

## Schritt 2 - Segmentzuordnungen - Segment dem Ziel zuordnen {#step-2-segment-mappings}

Ordnen Sie [das gewünschte Segment im Ziel](/help/using/features/destinations/create-url-destination.md#) -Workflow "URL konfigurieren" Ihrem neu erstellten Ziel zu. Beachten Sie, dass der Zuordnungswert automatisch mit der Segment-Manager-Segment-ID ausgefüllt wird.

Geben Sie ggf. ein Enddatum ein, andernfalls leer lassen Sie das Enddatum.

## Schritt 3: Erstellen einer Zielgruppe in Facebook-Anzeigen {#step-3-create-audience}

Weitere Informationen [finden Sie unter Benutzerdefinierte Zielgruppe](https://www.facebook.com/business/help/666509013483225) erstellen in der Hilfedokumentation zu Facebook. Wählen Sie in der Tabelle unten die Option Zielgruppe erstellen:


| Element | Beschreibung |
---------|----------|
| Website-Traffic | Benutzerdefinierte Kombination |
| Einschließlich | <ul><li>Wählen **Sie "Ereignis** " &gt;" **Adobe-Audience-Manager-Segment auswählen**«. Dies war der Wert des ev-Parameters im Beispiel-Pixel in Schritt 1. Wenn das Pixel noch nicht ausgelöst wird, wird die **Option "Ereignis"** oder" **Adobe-Audience-Manager-Segment** " möglicherweise nicht in der Facebook-Benutzeroberfläche angezeigt.</li><li>Fügen Sie einen Parameter hinzu: Wählen `segID`Sie.</li><li><p>Wählen Sie den **Operator enthält** .</p><p>Dies ist wichtig, wenn sich Besucher für mehrere Segmente qualifizieren können. Es kann mehrere Segment-IDs im Pixel-Parameter geben. Die Verwendung des Gleichheitsoperators (=) qualifiziert Ihre Besucher möglicherweise nicht für die Zielgruppe und Sie werden ein geringeres Volumen beobachten.</p></li><li>Fügen Sie einen Wert hinzu: Geben Sie die Segment-ID des Audience Manager ein.</li></ul> |
| Neue Bedingung hinzufügen | Optionale Einstellung. |
| Im letzten | Optionale Einstellung. |
| Zielgruppenname | Wir empfehlen, dass Sie denselben Segmentnamen für Audience Manager für Konsistenz verwenden, es sei denn, Sie fügen dieser Zielgruppe zusätzliche Bedingungen hinzu. |

## Schritt 4: Zuweisen der Zielgruppe zu einer Kampagne in Facebook-Anzeigen {#step-4-assign-audience-to-campaign}

Nachdem Sie die benutzerspezifische Zielgruppe erstellt haben, weisen Sie sie einer Werbekampagne zu. Erstellen Sie eine neue Kampagne oder bearbeiten Sie eine vorhandene, und Sie finden Ihre neu erstellte Zielgruppe in der Facebook-Benutzeroberfläche. Ihre Werbekampagne zielt auf Benutzer ab, die das Pixel in ihrem Browser beim Besuch Ihrer Site gesehen haben, wenn Audience Manager diese im Segment enthält.

## Zusammenfassung {#summary}

Nachdem Sie Ihr Audience Manager-Segment dem Facebook WCA-Ziel zugewiesen haben, löst Audience Manager das Facebook WCA-Pixel für Benutzer eines bestimmten Segments mit der entsprechenden Segment-ID im Pixel selektiv aus, um die Facebook-Zielgruppe auszufüllen. Dies führt zu einem allmählichen Anstieg der Facebook-Zielgruppe, je mehr das Tag auf die entsprechende Zielgruppe auf Ihrer Site ausgelöst wird.

>[!NOTE]
>
> Wenn ein Benutzer aus dem Audience Manager-Segment ausfällt, gibt es derzeit keine Möglichkeit für Audience Manager, Facebook zu benachrichtigen, um den Benutzer aus der benutzerdefinierten Zielgruppe zu entfernen.


---
description: Auf dieser Seite wird der Vorgang zum Erstellen von WCA-Pixeln (Facebook Website Custom Audiences) erläutert, um webbasierte Zielgruppensegmente von Audience Manager an Facebook zu senden und damit das Targeting von Online-Anzeigen mit verbesserter Transparenz zu ermöglichen.
seo-description: Auf dieser Seite wird der Vorgang zum Erstellen von WCA-Pixeln (Facebook Website Custom Audiences) erläutert, um webbasierte Zielgruppensegmente von Audience Manager an Facebook zu senden und damit das Targeting von Online-Anzeigen mit verbesserter Transparenz zu ermöglichen.
seo-title: Facebook-WCA-Integration
solution: Audience Manager
title: Facebook-WCA-Integration
translation-type: tm+mt
source-git-commit: 28d1292140a56cf1627a8921876d9483221876ca

---


# Facebook-WCA-Integration {#facebook-wca-integration}

Auf dieser Seite wird der Vorgang zum Erstellen von WCA-Pixeln (Facebook Website Custom Audiences) erläutert, um webbasierte Zielgruppensegmente von Audience Manager an Facebook zu senden und damit das Targeting von Online-Anzeigen mit verbesserter Transparenz zu ermöglichen.

## Überblick {#overview}

[Mit benutzerdefinierten Zielgruppen (WCA)](https://www.facebook.com/business/help/449542958510885) auf der Facebook-Website können Sie eine Liste der Personen erstellen, die bestimmte Seiten besucht oder bestimmte Aktionen auf Ihrer Website durchgeführt haben. Audience Manager aktiviert die Aktivierung in WCA mithilfe von URL-Zielen, mit denen Sie eine benutzerdefinierte pixelbasierte Integration konfigurieren können, um webbasierte Zielgruppen zum Targeting an Facebook zu senden.

![Facebook-WCA-Integration](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Für diese Funktion müssen Sie die Option "Zielgruppe der Website für soziale Plattformen"in den [URL-Zielen](/help/using/features/destinations/create-url-destination.md)auswählen. Für soziale Plattformen ist es erforderlich, dass Referrer-Informationen beim Senden an die Plattform nicht maskiert werden. Beachten Sie, dass dies bedeutet, dass die Zielplattform/der Partner Informationen in Ihrer verweisenden URL sehen können.

## Voraussetzungen {#prerequisites}

1. Facebook-Anzeigenkonto
2. Zielgruppen-Manager-Segmente, die Ihrem neuen Facebook-Ziel zugewiesen werden können. Hier [erfahren Sie, wie Sie ein Segment](/help/using/features/segments/segment-builder.md) in der Benutzeroberfläche von Audience Manager erstellen.
3. Adobe Experience Cloud ID-Dienst (ECID) Version 4.1.0 oder neuer. Laden Sie die neueste Version **[hier](https://github.com/Adobe-Marketing-Cloud/id-service/releases)** herunter.
4. Audience Manager Data Integration Library (DIL) Version 9.0 oder neuer, **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)** herunterzuladen. Wenn Sie zum Importieren von Daten in Audience Manager [Server-Side Forwarding (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) verwenden, müssen Sie stattdessen AppMeasurement Version 2.12 oder höher verwenden. Laden Sie AppMeasurement mit dem [Analytics-Code-Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)herunter.

Es wird empfohlen, die Bibliotheken in den Schritten 3 und 4 mit [Adobe Launch](https://docs.adobelaunch.com/) oder [Adobe Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/)zu installieren oder zu aktualisieren.

## Schritt 1: Erstellen eines Facebook-Ziels in Audience Manager {#step-1-create-facebook-destination}

Erstellen Sie ein neues URL-Ziel in Audience Manager und geben Sie ihm einen Namen für benutzerdefinierte Zielgruppen auf der Facebook-Website. Verwenden Sie beim Erstellen des Ziels die unten stehenden Einstellungen. Sie können auch auf der Seite "URL-Ziel [konfigurieren"nachsehen](/help/using/features/destinations/create-url-destination.md) .

**Basisinformationen**

* **Kategorie**: Benutzerdefiniert
* **Typ**: URL
* Aktivieren Sie das Kontrollkästchen Zielzuordnung **automatisch ausfüllen** und wählen Sie dann **Segment-ID**.

**Datenexportbeschriftungen**

Wählen Sie die Option **Dieses Ziel kann eine Kombination mit persönlich identifizierbaren Informationen (PII)** aktivieren.

>[!NOTE]
>
> Diese Exportbezeichnung verhindert, dass Daten von Drittanbietern und Daten aus Gerätediagrammen in die Segmente aufgenommen werden.

**Konfiguration**

* **URL-Typ**: Wählen Sie **Website-Zielgruppe für soziale Plattformen**. Durch Auswahl dieser Option "URL-Typ"verdeckt Audience Manager die URL-Informationen zum Referrer nicht, wenn ein Facebook-WCA-Pixel ausgelöst wird.
* **Serialisieren**: Wählen Sie **Aktivieren**.
* Geben Sie im Feld **Basis-URL** und **Sichere URL** das Facebook-WCA-Pixel ein.
* **Trennzeichen**: ,

Beispiel für eine Basis-URL: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Beispiel eines Pixels, das von der Seite ausgelöst wird. Dieses Beispiel zeigt einen Benutzer, der für drei Audience Manager-Segmente qualifiziert ist, mit den IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parameter | Beschreibung |
---------|----------|
| `id` | Ihre Facebook-Pixel-ID, die Sie in der Benutzeroberfläche von Facebook Ad Manager finden können, wenn Sie Zielgruppen-Pixel erstellen. |
| `ev` | Ereignis. Dies ist ein beliebiger Wert, der in der Benutzeroberfläche von Facebook Ad Manager angezeigt wird, sobald das Pixel auf der Site ausgelöst wird. Weitere Informationen finden Sie unter Einbeziehen in [Schritt 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Ein zusätzlicher Parameter, der in der Benutzeroberfläche von Facebook Ad Manager gefüllt wird, sobald das Pixel auf der Site ausgelöst wird. `segID` ist auch willkürlich. |
| `%ALIAS%` | Ein Audience Manager-Makro, das dynamisch durch die Segment-IDs von Audience Manager ersetzt wird, für die sich der Besucher der Site qualifiziert, durch Komma, |

Die URL-Zielkonfiguration sollte wie in unten stehender Abbildung aussehen:

![Zielkonfiguration](/help/using/integration/assets/facebook-wca.png)

Speichern Sie das Ziel. Anschließend können Sie mit dem Schritt **Segmentzuordnungen** fortfahren.

## Schritt 2 - Segmentzuordnungen - Segment dem Ziel zuordnen {#step-2-segment-mappings}

Ordnen Sie im Arbeitsablauf zum [Konfigurieren des URL-Ziels](/help/using/features/destinations/create-url-destination.md) das entsprechende Segment Ihrem neu erstellten Ziel zu. Beachten Sie, dass der Zuordnungswert automatisch mit der Segment-ID von Audience Manager ausgefüllt wird.

Geben Sie ggf. ein Enddatum ein, andernfalls leer lassen, wenn kein Enddatum angegeben ist.

## Schritt 3: Erstellen einer Zielgruppe in Facebook Ads Manager {#step-3-create-audience}

Siehe [Erstellen einer Website-benutzerdefinierten Zielgruppe](https://www.facebook.com/business/help/666509013483225) in der Facebook-Hilfedokumentation. Wählen Sie in der unten stehenden Tabelle die Optionen Zielgruppe erstellen aus:


| Element | Beschreibung |
---------|----------|
| Website-Traffic | Benutzerdefinierte Kombination |
| Einschließlich | <ul><li>Wählen Sie **Ereignis** &gt; **Adobe-Audience-Manager-Segment** auswählen. Dies war der Wert des Parameters ev im Beispielpixel in Schritt 1. Beachten Sie, dass die Option **Ereignis** oder **Adobe-Audience-Manager-Segment** in der Facebook-Benutzeroberfläche möglicherweise nicht angezeigt wird, wenn das Pixel noch nicht ausgelöst wird.</li><li>Parameter hinzufügen: Wählen Sie `segID`.</li><li><p>Wählen Sie den Operator **enthält** .</p><p>Dies ist angesichts der Tatsache, dass sich Besucher für mehrere Segmente qualifizieren können, wichtig, da der Pixelparameter möglicherweise mehrere Segment-IDs enthält. Die Verwendung des Operators Gleich (=) qualifiziert Ihre Besucher möglicherweise nicht für die Zielgruppe, und Sie werden ein geringeres Volumen beobachten.</p></li><li>Fügen Sie einen Wert hinzu: Geben Sie die Segment-ID für Audience Manager ein.</li></ul> |
| Neue Bedingung hinzufügen | Optionale Einstellung. |
| Im letzten | Optionale Einstellung. |
| Zielgruppenname | Es wird empfohlen, denselben Segmentnamen von Audience Manager zur Konsistenz zu verwenden, es sei denn, Sie fügen dieser Zielgruppe zusätzliche Bedingungen hinzu. |

## Schritt 4: Zuweisen der Zielgruppe zu einer Kampagne in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

Nachdem Sie die benutzerdefinierte Zielgruppe erstellt haben, weisen Sie sie einer Anzeigenkampagne zu. Erstellen Sie eine neue Kampagne oder bearbeiten Sie eine vorhandene, und Sie werden feststellen, dass Ihre neu erstellte Zielgruppe in der Facebook-Benutzeroberfläche aufgeführt ist. Ihre Werbekampagne richtet sich an Benutzer, die beim Besuch Ihrer Site den Pixelausbruch in ihrem Browser gesehen haben, sofern Audience Manager sie in das Segment einbezieht.

## Zusammenfassung {#summary}

Nachdem Sie Ihr Audience Manager-Segment nun dem Facebook-WCA-Ziel zugewiesen haben, löst Audience Manager das Facebook WCA-Pixel selektiv an Benutzer eines bestimmten Segments aus, wobei die entsprechende Segment-ID in Pixel angegeben wird, um die Facebook-Zielgruppe zu füllen. Dies führt zu einem allmählichen Anstieg der Facebook-Zielgruppe, je mehr das Tag für die jeweilige Zielgruppe auf Ihrer Site ausgelöst wird.

>[!NOTE]
>
> Wenn ein Benutzer aus dem Segment Audience Manager ausfällt, kann Audience Manager Facebook derzeit nicht darüber informieren, dass der Benutzer aus der benutzerdefinierten Zielgruppe entfernt wird.


---
description: Auf dieser Seite wird der Vorgang zum Erstellen von Facebook Website Custom Audiences (WCA)-Pixeln erläutert, um webbasierte Zielgruppensegmente von Audience Managern an Facebook zu senden, damit sie für das Targeting von Online-Anzeigen mit verbesserter Transparenz verwendet werden können.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook-WCA-Integration
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 8780083474d68717fe3bd4dc632d96da89929122
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Facebook WCA] Integration {#facebook-wca-integration}

Diese Seite zeigt den Prozess der Erstellung [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) Pixel zum Senden webbasierter [!DNL Audience Manager] Zielgruppensegmente in [!DNL Facebook], für das Targeting von Online-Anzeigen mit verbesserter Transparenz.

## Überblick {#overview}

[Benutzerdefinierte Zielgruppen auf der facebook-Website (WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) ermöglicht Ihnen, eine Liste von Personen zu erstellen, die bestimmte Seiten besucht oder bestimmte Aktionen auf Ihrer Website durchgeführt haben. [!DNL Audience Manager] Aktivierung in [!DNL WCA] using [!DNL URL] Ziele, mit denen Sie eine benutzerdefinierte pixelbasierte Integration konfigurieren können, um webbasierte Zielgruppen an zu senden [!DNL Facebook] für die Zielgruppenbestimmung.

![Facebook-WCA-Integration](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Für diese Funktion müssen Sie die [!UICONTROL Website] Zielgruppe für soziale Plattformen in [URL-Ziele](/help/using/features/destinations/create-url-destination.md). Social-Plattformen erfordern, dass Referrer-Informationen beim Senden an ihre Plattform nicht maskiert werden. Beachten Sie, dass dies bedeutet, dass die Zielplattform/-partner Informationen in Ihrer verweisenden Stelle sehen können. [!DNL URL].

## Voraussetzungen {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] Segmente, die für Ihre neue [!DNL Facebook] Ziel. Hier ist [Erstellen eines Segments](/help/using/features/segments/segment-builder.md) im [!DNL Audience Manager] Benutzeroberfläche.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 oder neuer. Neueste Version herunterladen **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) Version 9.0 oder neuer, heruntergeladen von **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Wenn Sie [Serverseitige Weiterleitung (Server Side Forwarding, SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) zum Importieren von Daten in [!DNL Audience Manager]verwenden, müssen Sie AppMeasurement-Version 2.12 oder höher verwenden. Download [!DNL AppMeasurement] mithilfe der [Analytics-Code-Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

Wir empfehlen, die Bibliotheken in den Schritten 3 und 4 zu installieren oder zu aktualisieren, indem Sie [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Schritt 1: Erstellen einer [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Erstellen Sie eine neue [!UICONTROL URL Destination] in [!DNL Audience Manager] und benennen Sie sie [!DNL Facebook Website Custom Audiences]. Verwenden Sie beim Erstellen des Ziels die unten stehenden Einstellungen. Weitere Informationen finden Sie unter [Konfigurieren eines URL-Ziels](/help/using/features/destinations/create-url-destination.md) Seite.

### Basisinformationen

* **[!UICONTROL Category]**: Benutzerspezifisch
* **[!UICONTROL Type]**: [!DNL URL]
* Wählen Sie die **[!UICONTROL Auto-fill Destination Mapping]** Kontrollkästchen aktivieren und dann **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Auswählen der Option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Diese Exportbezeichnung verhindert, dass Daten von Drittanbietern und Daten aus Gerätediagrammen in die Segmente aufgenommen werden.

### Konfiguration

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Durch Auswahl dieser Option [!UICONTROL URL Type] Option, [!DNL Audience Manager] verdeckt den Referrer nicht [!DNL URL] Informationen beim Auslösen einer [!DNL Facebook WCA] Pixel.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* Im **[!UICONTROL Base URL]** und **[!UICONTROL Secure URL]** eingeben. [!DNL Facebook WCA] Pixel.
* **[!UICONTROL Delimiter]**: `,`

Basis [!DNL URL] Beispiel: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Beispielpixel werden von der Seite ausgelöst. Dieses Beispiel zeigt einen Benutzer, der sich für drei qualifiziert [!DNL Audience Manager] Segmente mit den IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beschreibung |
|---------|----------|
| `id` | Ihre [!DNL Facebook] Pixel-ID, die Sie im [!DNL Facebook Ad Manager] Benutzeroberfläche beim Erstellen von Zielgruppenpixel. |
| `ev` | Event.     Dies ist ein beliebiger Wert, der im [!DNL Facebook Ad Manager] -Benutzeroberfläche, sobald das Pixel auf der Site ausgelöst wird. Siehe [!UICONTROL Include] -Element [Schritt 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), um weitere Informationen zu erhalten. |
| `cd[segID]` | Ein zusätzlicher Parameter, der in der Variablen [!DNL Facebook Ad Manager] -Benutzeroberfläche, sobald das Pixel auf der Site ausgelöst wird. `segID` ist auch willkürlich. |
| `%ALIAS%` | Ein [!DNL Audience Manager] -Makro, das dynamisch durch die [!DNL Audience Manager] [!UICONTROL segment] IDs, für die sich der Site-Besucher qualifiziert, getrennt durch Kommas , |

Ihre [!UICONTROL URL destination] -Konfiguration sollte wie in der Abbildung unten dargestellt aussehen:

![Zielkonfiguration](/help/using/integration/assets/facebook-wca.png)

Speichern Sie die [!UICONTROL destination]. Anschließend können Sie zum **Segmentzuordnungen** Schritt.

## Schritt 2: Segmentzuordnungen - Segment dem Ziel zuordnen {#step-2-segment-mappings}

Im [URL-Ziel konfigurieren](/help/using/features/destinations/create-url-destination.md) Workflow, ordnen Sie das entsprechende Segment Ihrem neu erstellten zu [!UICONTROL destination]. Beachten Sie, dass der Zuordnungswert automatisch mit dem [!DNL Audience Manager] [!UICONTROL segment ID].

Geben Sie gegebenenfalls ein Enddatum ein, andernfalls leer lassen für kein Enddatum.

## Schritt 3: Erstellen einer [!UICONTROL Audience] Innerhalb [!DNL Facebook Ads Manager] {#step-3-create-audience}

Siehe [Erstellen einer benutzerdefinierten Website-Zielgruppe](https://www.facebook.com/business/help/666509013483225) im [!DNL Facebook] Hilfe-Dokumentation. Wählen Sie die [!UICONTROL Create Audience] Optionen in der folgenden Tabelle:

| Element | Beschreibung |
|---------|----------|
| Website-Traffic | Benutzerdefinierte Kombination |
| Einschließlich | <ul><li>Auswählen **[!UICONTROL Event]** > Auswählen **[!UICONTROL Adobe-Audience-Manager-Segment]**. Dies war der Wert der `ev` -Parameter im Beispielpixel in Schritt 1. Beachten Sie Folgendes: Wenn das Pixel noch ausgelöst wird, wird die **[!UICONTROL Event]** Option oder **[!UICONTROL Adobe-Audience-Manager-Segment]** kann nicht im [!DNL Facebook] -Benutzeroberfläche.</li><li>Fügen Sie einen Parameter hinzu: Auswählen `segID`.</li><li><p>Wählen Sie die **contains** Operator.</p><p>Dies ist wichtig, da sich Besucher für mehrere Segmente qualifizieren können, kann es mehrere [!UICONTROL segment IDs] im Pixelparameter. Verwenden von gleich (`=`) werden Ihre Besucher möglicherweise nicht für die Zielgruppe qualifizieren und Sie werden ein geringeres Volumen feststellen.</p></li><li>Fügen Sie einen Wert hinzu: Geben Sie die [!DNL Audience Manager] Segment-ID.</li></ul> |
| Neue Bedingung hinzufügen | Optionale Einstellung. |
| Im letzten | Optionale Einstellung. |
| Zielgruppenname | Es wird empfohlen, dieselbe [!DNL Audience Manager] Segmentname zur Konsistenz, es sei denn, Sie fügen dieser Zielgruppe zusätzliche Bedingungen hinzu. |

## Schritt 4: Zuweisen der [!UICONTROL Audience] zu [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Nach der Erstellung [!DNL Custom Audience], weisen Sie sie einer Anzeigenkampagne zu. Erstellen Sie eine neue Kampagne oder bearbeiten Sie eine bestehende. Ihre neu erstellte Zielgruppe wird daraufhin im Abschnitt [!DNL Facebook] -Benutzeroberfläche. Ihre Werbekampagne wendet sich an Benutzer, die beim Besuch Ihrer Site das Pixelfeuer in ihrem Browser gesehen haben, sofern [!DNL Audience Manager] schließt sie in das Segment ein.

## Zusammenfassung {#summary}

Nachdem Sie die [!DNL Audience Manager] Segment [!DNL Facebook WCA] Ziel, [!DNL Audience Manager] löst selektiv die [!DNL Facebook WCA] Pixel an Benutzer eines bestimmten Segments mit der entsprechenden Segment-ID in dem Pixel an, um die [!DNL Facebook Audience]. Dies führt zu einer allmählichen Zunahme der [!DNL Facebook Audience] je mehr das Tag an die entsprechende Zielgruppe auf Ihrer Site ausgelöst wird.

>[!NOTE]
>
> Wenn ein Benutzer aus der [!DNL Audience Manager] -Segment, gibt es derzeit keine Möglichkeit für [!DNL Audience Manager] zur Information [!DNL Facebook] , um den Benutzer aus der [!DNL Custom Audience].

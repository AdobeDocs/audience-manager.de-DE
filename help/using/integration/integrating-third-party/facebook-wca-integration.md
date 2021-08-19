---
description: Auf dieser Seite wird der Vorgang zum Erstellen von Facebook Website Custom Audiences (WCA)-Pixeln erläutert, um webbasierte Zielgruppensegmente von Audience Managern an Facebook zu senden, damit sie für das Targeting von Online-Anzeigen mit verbesserter Transparenz verwendet werden können.
seo-description: Auf dieser Seite wird der Vorgang zum Erstellen von Facebook Website Custom Audiences (WCA)-Pixeln erläutert, um webbasierte Zielgruppensegmente von Audience Managern an Facebook zu senden, damit sie für das Targeting von Online-Anzeigen mit verbesserter Transparenz verwendet werden können.
seo-title: Facebook-WCA-Integration
solution: Audience Manager
title: Facebook-WCA-Integration
feature: Drittanbieterintegration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 4%

---

# [!DNL Facebook WCA] Integration {#facebook-wca-integration}

Auf dieser Seite wird der Prozess der Erstellung von [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) Pixeln zum Senden webbasierter [!DNL Audience Manager] Zielgruppensegmente an [!DNL Facebook] für das Targeting von Online-Anzeigen mit verbesserter Transparenz erläutert.

## Überblick {#overview}

[Mit facebook Website Custom Audiences (WCA) ](https://www.facebook.com/business/help/449542958510885)  können Sie eine Liste von Personen erstellen, die bestimmte Seiten besucht oder bestimmte Aktionen auf Ihrer Website durchgeführt haben. [!DNL Audience Manager] aktiviert die Aktivierung bei der  [!DNL WCA] Verwendung von  [!DNL URL] Zielen, mit denen Sie eine benutzerdefinierte pixelbasierte Integration konfigurieren können, um webbasierte Zielgruppen  [!DNL Facebook] zum Targeting an zu senden.

![Facebook-WCA-Integration](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Für diese Funktion müssen Sie die Option [!UICONTROL Website] Zielgruppe für soziale Plattformen unter [URL-Ziele](/help/using/features/destinations/create-url-destination.md) auswählen. Social-Plattformen erfordern, dass Referrer-Informationen beim Senden an ihre Plattform nicht maskiert werden. Beachten Sie, dass dies bedeutet, dass die Zielplattform/-partner Informationen in Ihrer verweisenden Stelle [!DNL URL] sehen können.

## Voraussetzungen {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] Segmente, die für die Zuweisung zu Ihrem neuen  [!DNL Facebook] Ziel bereit sind. Hier finden Sie [wie Sie ein Segment](/help/using/features/segments/segment-builder.md) in der [!DNL Audience Manager]-Benutzeroberfläche erstellen.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 oder neuer. Laden Sie die neueste Version **[hier](https://github.com/Adobe-Marketing-Cloud/id-service/releases)** herunter.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) Version 9.0 oder neuer, von  **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)** herunterladbar. Wenn Sie alternativ [Server-seitige Weiterleitung (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) verwenden, um Daten in [!DNL Audience Manager] zu importieren, müssen Sie AppMeasurement-Version 2.12 oder höher verwenden. Laden Sie [!DNL AppMeasurement] mit dem [Analytics-Code-Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html) herunter.

Es wird empfohlen, die Bibliotheken in den Schritten 3 und 4 mit [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html) zu installieren oder zu aktualisieren.

## Schritt 1: Erstellen einer [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Erstellen Sie ein neues [!UICONTROL URL Destination] in [!DNL Audience Manager] und nennen Sie es [!DNL Facebook Website Custom Audiences]. Verwenden Sie beim Erstellen des Ziels die unten stehenden Einstellungen. Weitere Informationen finden Sie auf der Seite [URL-Ziel konfigurieren](/help/using/features/destinations/create-url-destination.md) .

### Basisinformationen

* **[!UICONTROL Category]**: Benutzerspezifisch
* **[!UICONTROL Type]**: [!DNL URL]
* Aktivieren Sie das Kontrollkästchen **[!UICONTROL Auto-fill Destination Mapping]** und wählen Sie **[!UICONTROL Segment ID]** aus.

### [!UICONTROL Data Export Labels]

Wählen Sie die Option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]** aus.

>[!NOTE]
>
> Diese Exportbezeichnung verhindert, dass Daten von Drittanbietern und Daten aus Gerätediagrammen in die Segmente aufgenommen werden.

### Konfiguration

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Durch Auswahl dieser [!UICONTROL URL Type]-Option verdeckt [!DNL Audience Manager] die verweisende Stelle [!DNL URL] nicht, wenn ein [!DNL Facebook WCA]-Pixel ausgelöst wird.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* Geben Sie in die Felder **[!UICONTROL Base URL]** und **[!UICONTROL Secure URL]** das Pixel [!DNL Facebook WCA] ein.
* **[!UICONTROL Delimiter]**:  `,`

Basis [!DNL URL]-Beispiel: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Beispielpixel werden von der Seite ausgelöst. Dieses Beispiel zeigt einen Benutzer, der für drei [!DNL Audience Manager]-Segmente qualifiziert ist, mit den IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beschreibung |
|---------|----------|
| `id` | Ihre [!DNL Facebook] Pixel-ID, die Sie beim Erstellen von Zielgruppenpixel in der [!DNL Facebook Ad Manager]-Benutzeroberfläche finden können. |
| `ev` | Event.     Dies ist ein beliebiger Wert, der in der [!DNL Facebook Ad Manager] -Benutzeroberfläche angezeigt wird, sobald das Pixel auf der Site ausgelöst wird. Weitere Informationen finden Sie im Element [!UICONTROL Include] in [Schritt 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Ein zusätzlicher Parameter, der innerhalb der [!DNL Facebook Ad Manager]-Benutzeroberfläche gefüllt wird, sobald das Pixel auf der Site ausgelöst wird. `segID` ist auch willkürlich. |
| `%ALIAS%` | Ein [!DNL Audience Manager] -Makro, das dynamisch durch die [!DNL Audience Manager] [!UICONTROL segment]-IDs ersetzt wird, für die sich der Site-Besucher qualifiziert, getrennt durch Kommas , |

Ihre [!UICONTROL URL destination]-Konfiguration sollte wie in der Abbildung unten dargestellt aussehen:

![Zielkonfiguration](/help/using/integration/assets/facebook-wca.png)

Speichern Sie [!UICONTROL destination]. Anschließend können Sie mit dem Schritt **Segmentzuordnungen** fortfahren.

## Schritt 2: Segmentzuordnungen - Segment dem Ziel zuordnen {#step-2-segment-mappings}

Ordnen Sie im Workflow [URL-Ziel konfigurieren](/help/using/features/destinations/create-url-destination.md) das entsprechende Segment Ihrem neu erstellten [!UICONTROL destination] zu. Beachten Sie, dass der Zuordnungswert automatisch mit [!DNL Audience Manager] [!UICONTROL segment ID] gefüllt wird.

Geben Sie gegebenenfalls ein Enddatum ein, andernfalls leer lassen für kein Enddatum.

## Schritt 3: Erstellen einer [!UICONTROL Audience] innerhalb von [!DNL Facebook Ads Manager] {#step-3-create-audience}

Siehe [Erstellen einer benutzerdefinierten Website-Zielgruppe](https://www.facebook.com/business/help/666509013483225) in der [!DNL Facebook] -Hilfedokumentation. Wählen Sie in der unten stehenden Tabelle die Optionen [!UICONTROL Create Audience] aus:

| Element | Beschreibung |
|---------|----------|
| Website-Traffic | Benutzerdefinierte Kombination |
| Einschließlich | <ul><li>Wählen Sie **[!UICONTROL Event]** > Wählen Sie **[!UICONTROL Adobe-Audience-Manager-Segment]** aus. Dies war der Wert des Parameters `ev` im Beispielpixel in Schritt 1. Beachten Sie, dass die **[!UICONTROL Event]**-Option oder **[!UICONTROL Adobe-Audience-Manager-Segment]** in der [!DNL Facebook]-Benutzeroberfläche möglicherweise nicht angezeigt wird, wenn das Pixel noch nicht ausgelöst wird.</li><li>Fügen Sie einen Parameter hinzu: Wählen Sie `segID` aus.</li><li><p>Wählen Sie den Operator **contains** aus.</p><p>Dies ist wichtig, da sich Besucher für mehrere Segmente qualifizieren können, kann der Pixelparameter mehrere [!UICONTROL segment IDs] enthalten. Die Verwendung des Operators gleich (`=`) qualifiziert Ihre Besucher möglicherweise nicht für die Zielgruppe, und Sie werden ein geringeres Volumen feststellen.</p></li><li>Fügen Sie einen Wert hinzu: Geben Sie die Segment-ID [!DNL Audience Manager] ein.</li></ul> |
| Neue Bedingung hinzufügen | Optionale Einstellung. |
| Im letzten | Optionale Einstellung. |
| Zielgruppenname | Es wird empfohlen, für Konsistenz denselben [!DNL Audience Manager]-Segmentnamen zu verwenden, es sei denn, Sie fügen dieser Zielgruppe zusätzliche Bedingungen hinzu. |

## Schritt 4: Zuweisen von [!UICONTROL Audience] zu einem [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Nachdem Sie [!DNL Custom Audience] erstellt haben, weisen Sie ihn einer Anzeigenkampagne zu. Erstellen Sie eine neue Kampagne oder bearbeiten Sie eine bestehende. Ihre neu erstellte Zielgruppe finden Sie in der [!DNL Facebook] -Benutzeroberfläche. Ihre Werbekampagne wendet sich an Benutzer, die beim Besuch Ihrer Site das Pixelfeuer in ihrem Browser gesehen haben, wenn [!DNL Audience Manager] sie in das Segment einbezieht.

## Zusammenfassung {#summary}

Nachdem Sie Ihr [!DNL Audience Manager]-Segment nun dem [!DNL Facebook WCA]-Ziel zugewiesen haben, löst [!DNL Audience Manager] selektiv das [!DNL Facebook WCA]-Pixel an Benutzer eines bestimmten Segments aus, wobei die entsprechende Segment-ID in Pixel angegeben wird, um das [!DNL Facebook Audience] auszufüllen. Dies führt zu einem allmählichen Anstieg von [!DNL Facebook Audience], je mehr das Tag an die entsprechende Zielgruppe auf Ihrer Site gesendet wird.

>[!NOTE]
>
> Wenn ein Benutzer aus dem Segment [!DNL Audience Manager] herausfällt, gibt es derzeit keine Möglichkeit für [!DNL Audience Manager], [!DNL Facebook] darüber zu informieren, den Benutzer aus dem Segment [!DNL Custom Audience] zu entfernen.


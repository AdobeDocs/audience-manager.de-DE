---
description: Auf dieser Seite wird das Erstellen von Facebook Website Custom Audiencen (WCA)-Pixeln veranschaulicht, um webbasierte Audience Manager-Audiencen an Facebook zu senden, damit sie für das Online-Targeting mit verbesserter Transparenz optimiert werden können.
seo-description: Auf dieser Seite wird das Erstellen von Facebook Website Custom Audiencen (WCA)-Pixeln veranschaulicht, um webbasierte Audience Manager-Audiencen an Facebook zu senden, damit sie für das Online-Targeting mit verbesserter Transparenz optimiert werden können.
seo-title: Facebook-WCA-Integration
solution: Audience Manager
title: Facebook-WCA-Integration
feature: Integration von Drittanbietern
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 5%

---

# [!DNL Facebook WCA] Integration {#facebook-wca-integration}

Auf dieser Seite wird das Erstellen von [!DNL Facebook Website Custom Audiences]- ([!DNL WCA])-Pixeln zum Senden webbasierter [!DNL Audience Manager]-Audiencen an [!DNL Facebook] für das Targeting von Online-Anzeigen mit verbesserter Transparenz veranschaulicht.

## Überblick {#overview}

[Mit den benutzerspezifischen Audiencen der facebook-Website (WCA)](https://www.facebook.com/business/help/449542958510885) können Sie eine Liste von Personen erstellen, die bestimmte Seiten besucht oder bestimmte Aktionen auf Ihrer Website durchgeführt haben. [!DNL Audience Manager] ermöglicht die Aktivierung bei der  [!DNL WCA] Verwendung von  [!DNL URL] Zielen, mit denen Sie eine benutzerspezifische pixelbasierte Integration konfigurieren können, um webbasierte Audiencen  [!DNL Facebook] zum Targeting zu senden.

![Facebook-WCA-Integration](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Für diese Funktion müssen Sie die Option [!UICONTROL Website] Audience für soziale Plattformen in [URL-Ziele](/help/using/features/destinations/create-url-destination.md) auswählen. Social-Plattformen erfordern, dass die Werber-Informationen beim Versand an ihre Plattform nicht maskiert werden. Bitte beachten Sie, dass dies bedeutet, dass die Zielplattform/der Zielpartner Informationen in Ihrem Werber [!DNL URL] sehen kann.

## Voraussetzungen {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] Segmente, die für die Zuweisung zu Ihrem neuen  [!DNL Facebook] Ziel bereit sind. Hier sehen Sie [wie Sie ein Segment](/help/using/features/segments/segment-builder.md) in der [!DNL Audience Manager]-Benutzeroberfläche erstellen.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 oder neuer. Laden Sie die neueste Version **[hier](https://github.com/Adobe-Marketing-Cloud/id-service/releases)** herunter.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) Version 9.0 oder neuer, von  **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)** herunterzuladen. Alternativ dazu müssen Sie AppMeasurement Version 2.12 oder höher verwenden, wenn Sie [Serverseitige Weiterleitung (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) verwenden, um Daten in [!DNL Audience Manager] zu importieren. Laden Sie [!DNL AppMeasurement] mit dem [Analytics-Code-Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html) herunter.

Es wird empfohlen, die Bibliotheken in den Schritten 3 und 4 mit [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html) zu installieren oder zu aktualisieren.

## Schritt 1: Erstellen eines [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Erstellen Sie ein neues [!UICONTROL URL Destination] in [!DNL Audience Manager] und benennen Sie es [!DNL Facebook Website Custom Audiences]. Verwenden Sie beim Erstellen des Ziels die unten stehenden Einstellungen. Sie können auch auf die Seite [URL-Ziel konfigurieren](/help/using/features/destinations/create-url-destination.md) verweisen.

### Basisinformationen

* **[!UICONTROL Category]**: Benutzerspezifisch
* **[!UICONTROL Type]**: [!DNL URL]
* Aktivieren Sie das Kontrollkästchen **[!UICONTROL Auto-fill Destination Mapping]** und wählen Sie **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Wählen Sie die Option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Diese Exportbezeichnung verhindert, dass Daten von Drittanbietern und Daten aus Gerätediagrammen in die Segmente aufgenommen werden.

### Konfiguration

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Durch Auswahl dieser Option [!UICONTROL URL Type] verdeckt [!DNL Audience Manager] beim Auslösen eines [!DNL Facebook WCA]-Werbers nicht die [!DNL URL]-Informationen.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* Geben Sie im Feld **[!UICONTROL Base URL]** und **[!UICONTROL Secure URL]** den Pixel [!DNL Facebook WCA] ein.
* **[!UICONTROL Delimiter]**:  `,`

Beispiel für Basis [!DNL URL]: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Beispiel eines Pixels, das von der Seite ausgelöst wird. Dieses Beispiel zeigt einen Benutzer, der für drei [!DNL Audience Manager]-Segmente qualifiziert ist, mit den IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beschreibung |
---------|----------|
| `id` | Ihre [!DNL Facebook] Pixel-ID, die Sie in der [!DNL Facebook Ad Manager]-Benutzeroberfläche finden können, wenn Sie Audiencen-Pixel erstellen. |
| `ev` | Event.     Dies ist ein beliebiger Wert, der in der [!DNL Facebook Ad Manager]-Benutzeroberfläche angezeigt wird, sobald das Pixel auf der Site ausgelöst wird. Weitere Informationen finden Sie unter [!UICONTROL Include] unter [Schritt 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Ein zusätzlicher Parameter, der in der [!DNL Facebook Ad Manager]-Benutzeroberfläche gefüllt wird, sobald das Pixel auf der Site ausgelöst wird. `segID` ist auch willkürlich. |
| `%ALIAS%` | Ein [!DNL Audience Manager]-Makro, das dynamisch durch die [!DNL Audience Manager] [!UICONTROL segment]-IDs ersetzt wird, für die sich der Site-Besucher qualifiziert, durch Kommas getrennt, |

Die [!UICONTROL URL destination]-Konfiguration sollte wie in der folgenden Abbildung aussehen:

![Zielkonfiguration](/help/using/integration/assets/facebook-wca.png)

Speichern Sie [!UICONTROL destination]. Anschließend können Sie mit dem Schritt **Segmentzuordnungen** fortfahren.

## Schritt 2 - Segmentzuordnungen - Segment dem Ziel zuordnen {#step-2-segment-mappings}

Ordnen Sie im Arbeitsablauf [URL-Ziel konfigurieren](/help/using/features/destinations/create-url-destination.md) das entsprechende Segment Ihrem neu erstellten [!UICONTROL destination] zu. Beachten Sie, dass der Zuordnungswert automatisch mit [!DNL Audience Manager] [!UICONTROL segment ID] gefüllt wird.

Geben Sie ggf. ein Enddatum ein, andernfalls leer lassen, wenn kein Enddatum angegeben ist.

## Schritt 3: Erstellen eines [!UICONTROL Audience] in [!DNL Facebook Ads Manager] {#step-3-create-audience}

Siehe [Eine benutzerspezifische Audience für Websites erstellen](https://www.facebook.com/business/help/666509013483225) in der [!DNL Facebook]-Hilfedokumentation. Wählen Sie in der unten stehenden Tabelle die Optionen [!UICONTROL Create Audience] aus:

| Element | Beschreibung |
---------|----------|
| Website-Traffic | Benutzerdefinierte Kombination |
| Einschließlich | <ul><li>Wählen Sie **[!UICONTROL Event]** > **[!UICONTROL Adobe-Audience-Manager-Segment]**. Dies war der Wert des Parameters `ev` im Beispielpixel in Schritt 1. Beachten Sie, dass die Option **[!UICONTROL Event]** oder **[!UICONTROL Adobe-Audience-Manager-Segment]** in der [!DNL Facebook]-Benutzeroberfläche möglicherweise nicht angezeigt wird, wenn das Pixel noch nicht ausgelöst wird.</li><li>hinzufügen eines Parameters: Wählen Sie `segID`.</li><li><p>Wählen Sie den Operator **contains**.</p><p>Dies ist wichtig, da sich Besucher für mehrere Segmente qualifizieren können, kann der Pixelparameter mehrere [!UICONTROL segment IDs] enthalten. Wenn Sie den Operator Gleich (`=`) verwenden, sind Ihre Besucher möglicherweise nicht für die Audience qualifiziert, und Sie werden ein geringeres Volumen beobachten.</p></li><li>hinzufügen einen Wert: Geben Sie die Segment-ID [!DNL Audience Manager] ein.</li></ul> |
| hinzufügen neue Bedingung | Optionale Einstellung. |
| Im letzten | Optionale Einstellung. |
| Name der Audience | Es wird empfohlen, denselben [!DNL Audience Manager]-Segmentnamen zur Konsistenz zu verwenden, es sei denn, Sie fügen dieser Audience zusätzliche Bedingungen hinzu. |

## Schritt 4 - Zuweisen des [!UICONTROL Audience] zu einem [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Nachdem Sie das [!DNL Custom Audience] erstellt haben, weisen Sie es einer Anzeigen-Kampagne zu. Erstellen Sie eine neue Kampagne oder bearbeiten Sie eine vorhandene, und Sie finden Ihre neu erstellte Audience in der [!DNL Facebook]-Benutzeroberfläche. Ihre Kampagne der Anzeige Zielgruppe Benutzer, die beim Besuch Ihrer Site das Pixelfeuer gesehen haben, wenn [!DNL Audience Manager] sie in das Segment eingeschlossen.

## Zusammenfassung {#summary}

Nachdem Sie Ihr [!DNL Audience Manager]-Segment dem [!DNL Facebook WCA]-Ziel zugewiesen haben, löst [!DNL Audience Manager] den [!DNL Facebook WCA]-Pixel selektiv an Benutzer eines bestimmten Segments aus, wobei die entsprechende Segment-ID in Pixel angegeben ist, um das [!DNL Facebook Audience] auszufüllen. Dies führt zu einem allmählichen Anstieg des Werts [!DNL Facebook Audience], je mehr das Tag auf die entsprechende Audience Ihrer Site ausgelöst wird.

>[!NOTE]
>
> Wenn ein Benutzer aus dem Segment [!DNL Audience Manager] herausfällt, gibt es derzeit keine Möglichkeit für [!DNL Audience Manager] [!DNL Facebook],  anzuzeigen, den Benutzer aus dem Segment [!DNL Custom Audience] zu entfernen.


---
description: Auf dieser Seite wird der Prozess der Erstellung von WCA-Pixeln (Custom Audiences) der Facebook-Website veranschaulicht, mit dem webbasierte Audience Manager-Zielgruppensegmente an Facebook gesendet werden können, um das Targeting von Online-Anzeigen mit verbesserter Transparenz zu ermöglichen.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook WCA-Integration
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 6dc931b88666515cf51ab89ce1a54bbcf9995679
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# [!DNL Facebook WCA] Integration {#facebook-wca-integration}

Auf dieser Seite wird der Prozess der Erstellung von [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) Pixeln veranschaulicht, mit denen webbasierte [!DNL Audience Manager] Zielgruppensegmente an [!DNL Facebook] gesendet werden können, um das Targeting von Online-Anzeigen mit verbesserter Transparenz zu ermöglichen.

>[!IMPORTANT]
>
>Dies ist keine produktbezogene Integration zwischen Audience Manager und Facebook.

## Überblick {#overview}

[Benutzerdefinierte Facebook-Website-Zielgruppen (WCA](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) ermöglicht Ihnen die Erstellung einer Liste von Personen, die bestimmte Seiten besucht oder bestimmte Aktionen auf Ihrer Website durchgeführt haben. [!DNL Audience Manager] ermöglicht die Aktivierung in [!DNL WCA] mithilfe von [!DNL URL]-Zielen, mit denen Sie eine benutzerdefinierte pixelbasierte Integration konfigurieren können, um webbasierte Zielgruppen zum Targeting an [!DNL Facebook] zu senden.

![Facebook-WCA-Integration](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Diese Funktion erfordert, dass Sie die Option Zielgruppe für soziale Plattformen [!UICONTROL Website] unter [URL-Ziele](/help/using/features/destinations/create-url-destination.md) auswählen. Social-Media-Plattformen verlangen, dass Referrer-Informationen demaskiert werden, wenn sie an ihre Plattform gesendet werden. Bitte beachten Sie, dass dies bedeutet, dass die Zielplattform/der Zielpartner Informationen in Ihrem Referrer-[!DNL URL] sehen kann.

## Voraussetzungen {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] Segmente, die Ihrem neuen [!DNL Facebook]-Ziel zugewiesen werden können. Im Folgenden finden Sie [Erstellen eines Segments](/help/using/features/segments/segment-builder.md) in der [!DNL Audience Manager]-Benutzeroberfläche.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 oder neuer. Laden Sie die neueste Version herunter **[hier](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) Version 9.0 oder neuer, herunterladbar von **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Wenn Sie [ Server-seitige Weiterleitung (SSF) verwenden](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=de) um Daten in [!DNL Audience Manager] zu importieren, müssen Sie AppMeasurement Version 2.12 oder höher verwenden. Laden Sie [!DNL AppMeasurement] mit dem [Analytics Code Manager“ ](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=de).

Es wird empfohlen, die Bibliotheken in den Schritten 3 und 4 mithilfe von [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=de) zu installieren oder zu aktualisieren.

## Schritt 1: Erstellen eines [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Erstellen Sie eine neue [!UICONTROL URL Destination] in [!DNL Audience Manager] und benennen Sie sie [!DNL Facebook Website Custom Audiences]. Verwenden Sie beim Erstellen des Ziels die folgenden Einstellungen. Weitere Informationen finden Sie auf der Seite [Konfigurieren eines URL-](/help/using/features/destinations/create-url-destination.md)&quot;.

### Basisinformationen

* **[!UICONTROL Category]**: Benutzerdefiniert
* **[!UICONTROL Type]**: [!DNL URL]
* Aktivieren Sie das Kontrollkästchen **[!UICONTROL Auto-fill Destination Mapping]** und klicken Sie dann auf **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Wählen Sie die Option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]** aus.

>[!NOTE]
>
> Diese Exportkennzeichnung verhindert, dass aus Gerätediagrammen abgeleitete Drittanbieterdaten und -daten in die Segmente aufgenommen werden.

### Konfiguration

* **[!UICONTROL URL type]**: **[!UICONTROL Website audience for social platforms]** auswählen. Durch Auswahl dieser [!UICONTROL URL Type] Option verdeckt [!DNL Audience Manager] die Referrer-[!DNL URL] beim Auslösen eines [!DNL Facebook WCA] Pixels nicht.
* **[!UICONTROL Serialize]**: **[!UICONTROL Enable]** auswählen.
* Geben Sie im Feld **[!UICONTROL Base URL]** und **[!UICONTROL Secure URL]** das [!DNL Facebook WCA] Pixel ein.
* **[!UICONTROL Delimiter]**: `,`

[!DNL URL]: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Beispielpixel, das von der Seite ausgelöst wird. Dieses Beispiel zeigt einen Benutzer, der sich für drei [!DNL Audience Manager]-Segmente qualifiziert, mit den IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beschreibung |
|---------|----------|
| `id` | Ihre [!DNL Facebook]-Pixel-ID, die Sie beim Erstellen von Zielgruppen-Pixeln in der [!DNL Facebook Ad Manager]-Benutzeroberfläche finden. |
| `ev` | Ereignis. Dies ist ein beliebiger Wert, der in der [!DNL Facebook Ad Manager]-Benutzeroberfläche angezeigt wird, sobald das Pixel vor Ort zu feuern beginnt. Weitere Informationen finden Sie unter dem [!UICONTROL Include] in [Schritt ](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)). |
| `cd[segID]` | Ein zusätzlicher Parameter, der in der [!DNL Facebook Ad Manager]-Benutzeroberfläche angezeigt wird, sobald das Pixel vor Ort ausgelöst wird. `segID` ist auch willkürlich. |
| `%ALIAS%` | Ein [!DNL Audience Manager] Makro, das dynamisch durch die [!DNL Audience Manager] [!UICONTROL segment] IDs ersetzt wird, für die der Site-Besucher qualifiziert ist, getrennt durch Komma , |

Ihre [!UICONTROL URL destination] sollte wie in der Abbildung unten aussehen:

![Zielkonfiguration](/help/using/integration/assets/facebook-wca.png)

Speichern Sie die [!UICONTROL destination]. Anschließend können Sie mit dem Schritt **Segmentzuordnungen** fortfahren.

## Schritt 2: Segmentzuordnungen - Segment dem Ziel zuordnen {#step-2-segment-mappings}

Ordnen Sie im Workflow [URL-Ziel konfigurieren](/help/using/features/destinations/create-url-destination.md) das entsprechende Segment Ihrer neu erstellten [!UICONTROL destination] zu. Beachten Sie, dass der Zuordnungswert automatisch mit dem [!DNL Audience Manager] [!UICONTROL segment ID] ausgefüllt wird.

Geben Sie ggf. ein Enddatum ein. Andernfalls lassen Sie es für kein Enddatum leer.

## Schritt 3: Erstellen eines [!UICONTROL Audience] in [!DNL Facebook Ads Manager] {#step-3-create-audience}

Siehe [Erstellen einer benutzerdefinierten Website-Zielgruppe](https://www.facebook.com/business/help/666509013483225) in der [!DNL Facebook]-Hilfedokumentation. Wählen Sie die [!UICONTROL Create Audience] Optionen in der folgenden Tabelle aus:

| Element | Beschreibung |
|---------|----------|
| Website-Traffic | Benutzerdefinierte Kombination |
| Einschließlich | <ul><li>Wählen Sie **[!UICONTROL Event]** > **[!UICONTROL Adobe-Audience-Manager-Segment]** auswählen aus. Dies war der Wert des `ev` im Beispielpixel in Schritt 1. Beachten Sie, dass die **[!UICONTROL Event]**-Option oder -**[!UICONTROL Adobe-Audience-Manager-Segment]** möglicherweise nicht in der [!DNL Facebook] Benutzeroberfläche angezeigt wird, wenn das Pixel noch nicht ausgelöst wurde.</li><li>Parameter hinzufügen: `segID` auswählen.</li><li><p>Wählen Sie den **enthält**-Operator aus.</p><p>Dies ist wichtig, da Besucher sich möglicherweise für mehrere Segmente qualifizieren und der Pixelparameter mehrere [!UICONTROL segment IDs] enthalten kann. Die Verwendung des Operators „ist gleich (`=`)“ qualifiziert Ihre Besucher möglicherweise nicht für die Zielgruppe, und Sie werden eine niedrigere Lautstärke feststellen.</p></li><li>Wert hinzufügen: Geben Sie die ID des [!DNL Audience Manager] Segments ein.</li></ul> |
| Neue Bedingung hinzufügen | Optionale Einstellung. |
| Im letzten | Optionale Einstellung. |
| Zielgruppenname | Es wird empfohlen, aus Konsistenzgründen denselben [!DNL Audience Manager]-Segmentnamen zu verwenden, es sei denn, Sie fügen dieser Zielgruppe zusätzliche Bedingungen hinzu. |

## Schritt 4: [!UICONTROL Audience] einem [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] zuweisen {#step-4-assign-audience-to-campaign}

Nachdem Sie die [!DNL Custom Audience] erstellt haben, weisen Sie sie einer Anzeigenkampagne zu. Erstellen Sie eine neue Kampagne oder bearbeiten Sie eine vorhandene, und Ihre neu erstellte Audience wird in der [!DNL Facebook] Benutzeroberfläche aufgelistet. Ihre Anzeigenkampagne richtet sich an Benutzende, die beim Besuch Ihrer Site die Pixelfeuerung in ihrem Browser gesehen haben, falls [!DNL Audience Manager] sie in das Segment einbezieht.

## Zusammenfassung {#summary}

Nachdem Sie nun Ihr [!DNL Audience Manager] Segment dem [!DNL Facebook WCA] Ziel zugewiesen haben, löst [!DNL Audience Manager] das [!DNL Facebook WCA] Pixel für Benutzer eines bestimmten Segments mit der entsprechenden Segment-ID im Pixel selektiv aus, um das [!DNL Facebook Audience] zu befüllen. Dies führt zu einer schrittweisen Erhöhung der [!DNL Facebook Audience], je mehr das Tag an die entsprechende Zielgruppe auf Ihrer Site gesendet wird.

>[!NOTE]
>
> Wenn ein(e) Benutzende(r) aus dem [!DNL Audience Manager] Segment fällt, gibt es derzeit keine Möglichkeit für [!DNL Audience Manager], [!DNL Facebook] zu informieren, den/die Benutzende aus dem [!DNL Custom Audience] zu entfernen.
>

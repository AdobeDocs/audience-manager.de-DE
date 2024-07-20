---
description: Auf dieser Seite wird der Vorgang zum Erstellen von Facebook Website Custom Audiences (WCA)-Pixeln erläutert, um webbasierte Zielgruppensegmente von Audience Managern an Facebook zu senden, damit sie für das Targeting von Online-Anzeigen mit verbesserter Transparenz verwendet werden können.
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

Auf dieser Seite wird der Prozess der Erstellung von [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) Pixeln zum Senden webbasierter [!DNL Audience Manager] Zielgruppensegmente an [!DNL Facebook] für das Targeting von Online-Anzeigen mit verbesserter Transparenz erläutert.

>[!IMPORTANT]
>
>Es handelt sich hierbei nicht um eine produktive Integration zwischen Audience Manager und Facebook.

## Überblick {#overview}

Mit [Facebook Website Custom Audiences (WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) können Sie eine Liste von Personen erstellen, die bestimmte Seiten besucht oder bestimmte Aktionen auf Ihrer Website durchgeführt haben. [!DNL Audience Manager] aktiviert die Aktivierung in [!DNL WCA] mithilfe von [!DNL URL] -Zielen, mit denen Sie eine benutzerdefinierte pixelbasierte Integration konfigurieren können, um webbasierte Zielgruppen zum Targeting an [!DNL Facebook] zu senden.

![Facebook-WCA-Integration](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Für diese Funktion müssen Sie die Option [!UICONTROL Website] Zielgruppe für soziale Plattformen in [URL-Zielen](/help/using/features/destinations/create-url-destination.md) auswählen. Social-Plattformen erfordern, dass Referrer-Informationen beim Senden an ihre Plattform nicht maskiert werden. Beachten Sie, dass dies bedeutet, dass die Zielplattform/-partner Informationen in Ihrer verweisenden Stelle [!DNL URL] sehen können.

## Voraussetzungen {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] Segmente, die bereit sind, Ihrem neuen [!DNL Facebook]-Ziel zuzuweisen. Im Folgenden finden Sie [ Informationen zum Erstellen eines Segments](/help/using/features/segments/segment-builder.md) in der Benutzeroberfläche von [!DNL Audience Manager].
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 oder neuer. Laden Sie die neueste Version **[hier](https://github.com/Adobe-Marketing-Cloud/id-service/releases)** herunter.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) Version 9.0 oder höher, herunterladbar von **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Wenn Sie alternativ [Server-seitige Weiterleitung (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) verwenden, um Daten in [!DNL Audience Manager] zu importieren, müssen Sie AppMeasurement-Version 2.12 oder höher verwenden. Laden Sie [!DNL AppMeasurement] mit dem [Analytics-Code-Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html) herunter.

Es wird empfohlen, die Bibliotheken in den Schritten 3 und 4 mit [Adobe Experience Platform-Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) zu installieren oder zu aktualisieren.

## Schritt 1: Erstellen eines [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Erstellen Sie eine neue [!UICONTROL URL Destination] in [!DNL Audience Manager] und nennen Sie sie [!DNL Facebook Website Custom Audiences]. Verwenden Sie beim Erstellen des Ziels die unten stehenden Einstellungen. Weitere Informationen finden Sie auf der Seite [URL-Ziel konfigurieren](/help/using/features/destinations/create-url-destination.md) .

### Basisinformationen

* **[!UICONTROL Category]**: Benutzerdefiniert
* **[!UICONTROL Type]**: [!DNL URL]
* Aktivieren Sie das Kontrollkästchen **[!UICONTROL Auto-fill Destination Mapping]** und wählen Sie dann **[!UICONTROL Segment ID]** aus.

### [!UICONTROL Data Export Labels]

Wählen Sie die Option **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]** aus.

>[!NOTE]
>
> Diese Exportbezeichnung verhindert, dass Daten von Drittanbietern und Daten aus Gerätediagrammen in die Segmente aufgenommen werden.

### Konfiguration

* **[!UICONTROL URL type]**: Wählen Sie **[!UICONTROL Website audience for social platforms]** aus. Durch Auswahl dieser [!UICONTROL URL Type] -Option verdeckt [!DNL Audience Manager] die verweisenden [!DNL URL]-Informationen nicht, wenn ein [!DNL Facebook WCA]-Pixel ausgelöst wird.
* **[!UICONTROL Serialize]**: Wählen Sie **[!UICONTROL Enable]** aus.
* Geben Sie in die Felder **[!UICONTROL Base URL]** und **[!UICONTROL Secure URL]** das Pixel [!DNL Facebook WCA] ein.
* **[!UICONTROL Delimiter]**: `,`

Base [!DNL URL]-Beispiel: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Beispielpixel werden von der Seite ausgelöst. Dieses Beispiel zeigt einen Benutzer, der für drei [!DNL Audience Manager]-Segmente qualifiziert ist, mit den IDs 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beschreibung |
|---------|----------|
| `id` | Ihre [!DNL Facebook] Pixel-ID, die Sie beim Erstellen von Zielgruppenpixel in der Benutzeroberfläche von [!DNL Facebook Ad Manager] finden können. |
| `ev` | Ereignis. Dies ist ein beliebiger Wert, der in der Benutzeroberfläche von [!DNL Facebook Ad Manager] angezeigt wird, sobald das Pixel auf der Site ausgelöst wird. Weitere Informationen finden Sie unter dem Element [!UICONTROL Include] in [Schritt 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Ein zusätzlicher Parameter, der innerhalb der [!DNL Facebook Ad Manager] -Benutzeroberfläche auffüllt, sobald das Pixel auf der Site ausgelöst wird. `segID` ist ebenfalls beliebig. |
| `%ALIAS%` | Ein [!DNL Audience Manager] -Makro, das dynamisch durch die [!DNL Audience Manager] [!UICONTROL segment]-IDs ersetzt wird, für die sich der Site-Besucher qualifiziert, getrennt durch Kommas , |

Ihre [!UICONTROL URL destination] -Konfiguration sollte wie in der Abbildung unten dargestellt aussehen:

![Zielkonfiguration](/help/using/integration/assets/facebook-wca.png)

Speichern Sie die [!UICONTROL destination]. Anschließend können Sie mit dem Schritt **Segmentzuordnungen** fortfahren.

## Schritt 2: Segmentzuordnungen - Segment dem Ziel zuordnen {#step-2-segment-mappings}

Ordnen Sie im Workflow [URL-Ziel konfigurieren](/help/using/features/destinations/create-url-destination.md) das entsprechende Segment Ihrem neu erstellten [!UICONTROL destination] zu. Beachten Sie, dass der Zuordnungswert automatisch mit dem Wert [!DNL Audience Manager] [!UICONTROL segment ID] gefüllt wird.

Geben Sie gegebenenfalls ein Enddatum ein, andernfalls leer lassen für kein Enddatum.

## Schritt 3: Erstellen einer [!UICONTROL Audience] innerhalb von [!DNL Facebook Ads Manager] {#step-3-create-audience}

Siehe [Erstellen einer benutzerdefinierten Website-Zielgruppe](https://www.facebook.com/business/help/666509013483225) in der Hilfedokumentation zu [!DNL Facebook]. Wählen Sie die Optionen [!UICONTROL Create Audience] in der folgenden Tabelle aus:

| Element | Beschreibung |
|---------|----------|
| Website-Traffic | Benutzerdefinierte Kombination |
| Einschließlich | <ul><li>Wählen Sie **[!UICONTROL Event]** > Wählen Sie **[!UICONTROL Adobe-Audience-Manager-Segment]** aus. Dies war der Wert des Parameters `ev` im Beispielpixel in Schritt 1. Beachten Sie, dass die Option **[!UICONTROL Event]** oder **[!UICONTROL Adobe-Audience-Manager-Segment]** in der Benutzeroberfläche von [!DNL Facebook] möglicherweise nicht angezeigt wird, wenn das Pixel noch nicht ausgelöst wird.</li><li>Parameter hinzufügen: Wählen Sie `segID` aus.</li><li><p>Wählen Sie den Operator **contains** aus.</p><p>Angesichts der Tatsache, dass sich Besucher für mehrere Segmente qualifizieren können, ist dies wichtig. Daher kann der Pixelparameter mehrere [!UICONTROL segment IDs] enthalten. Die Verwendung des Operators gleich (`=`) qualifiziert Ihre Besucher möglicherweise nicht für die Zielgruppe, und Sie werden ein geringeres Volumen feststellen.</p></li><li>Wert hinzufügen: Geben Sie die Segment-ID [!DNL Audience Manager] ein.</li></ul> |
| Neue Bedingung hinzufügen | Optionale Einstellung |
| Im letzten | Optionale Einstellung |
| Zielgruppenname | Es wird empfohlen, denselben [!DNL Audience Manager] Segmentnamen für Konsistenz zu verwenden, es sei denn, Sie fügen dieser Zielgruppe zusätzliche Bedingungen hinzu. |

## Schritt 4: Zuweisen der [!UICONTROL Audience] zu einer [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Nachdem Sie den [!DNL Custom Audience] erstellt haben, weisen Sie ihn einer Anzeigenkampagne zu. Erstellen Sie eine neue Kampagne oder bearbeiten Sie eine bestehende. Ihre neu erstellte Zielgruppe wird dann in der Benutzeroberfläche von [!DNL Facebook] aufgelistet. Ihre Werbekampagne wendet sich an Benutzer, die beim Besuch Ihrer Site das Pixelfeuer in ihrem Browser gesehen haben, sofern [!DNL Audience Manager] sie in das Segment einbezieht.

## Zusammenfassung  {#summary}

Nachdem Sie Ihr [!DNL Audience Manager]-Segment nun dem [!DNL Facebook WCA]-Ziel zugewiesen haben, löst [!DNL Audience Manager] selektiv das [!DNL Facebook WCA]-Pixel für Benutzer eines bestimmten Segments aus, wobei die entsprechende Segment-ID in dem Pixel enthalten ist, um die [!DNL Facebook Audience] zu füllen. Dies führt zu einem allmählichen Anstieg des Werts [!DNL Facebook Audience], je mehr das Tag an die entsprechende Zielgruppe auf Ihrer Site gesendet wird.

>[!NOTE]
>
> Wenn ein Benutzer aus dem [!DNL Audience Manager] -Segment herausfällt, ist es derzeit nicht möglich, [!DNL Audience Manager] zu informieren, dass [!DNL Facebook] den Benutzer aus dem [!DNL Custom Audience] entfernt.
>

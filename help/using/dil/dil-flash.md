---
description: Erfassen Sie Daten, die von FLA-Dateien an Analytics gesendet werden, und verwenden Sie diese Informationen in Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 3%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>Ab Juli 2023 hat die Adobe die Entwicklung der [!DNL Data Integration Library (DIL)] und [!DNL DIL] -Erweiterung.
>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] Implementierung. Die Adobe wird sich jedoch nicht entwickeln [!DNL DIL] über diesen Punkt hinaus. Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie.
>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) anstatt.

Erfassen Sie Daten, die von FLA-Dateien an Analytics gesendet werden, und verwenden Sie diese Informationen in Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] ist [!DNL ActionScript] -Codebibliothek, mit der Sie mit Videowiedergabedaten in Audience Manager arbeiten können. [!DNL Flash DIL] erfasst SWF-Inhalte in der Adobe [!UICONTROL AppMeasurement] -Bibliothek wird an Analytics übergeben. [!DNL Flash DIL] sendet diese Daten an die separate [!UICONTROL DIL] JavaScript-Datenerfassungsmodul, das diese Informationen an Audience Manager übergibt. Analytics-Daten ( [!UICONTROL Props], [!UICONTROL eVars], Ereignisse usw.) erfasst von der [!DNL FLA] -Datei ist in Audience Manager als Eigenschaften oder nicht verwendete Signale verfügbar.

## Anforderungen an die Datenerfassung durch Flash DIL {#requirements}

Allgemeine Implementierungs- und Code-bezogene Anforderungen.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementierungsanforderungen**

[!UICONTROL Flash] Die Datenerfassung erfordert:

* Die [!UICONTROL DIL] Klassenbibliothek ( `dil.swc`). Erhalten Sie die [!UICONTROL DIL] -Klassenbibliothek von Ihrem Partner Solutions-Ansprechpartner aus.

* JavaScript [!UICONTROL DIL] Datenerfassungscode auf der Seite.
* [DIL ActionScript-Bibliothek](../dil/dil-flash.md#flash-dil-actionscript) in das Flash-Objekt geladen wurde, aus dem Sie Daten erfassen möchten.
* Adobe [!DNL AppMeasurement] [!DNL AS] -Bibliothek (Version 3.5.2 oder höher) lädt die [!DNL Flash] -Objekt, aus dem Sie Daten erfassen möchten.

**AllowScriptAccess auf `Always` oder`sameDomain`**

Die `AllowScriptAccess` in HTML-Code, der eine SWF-Datei lädt, steuert die Möglichkeit, aus der SWF-Datei ausgehenden URL-Zugriff durchzuführen. Wenn Sie eine [!UICONTROL Flash DIL] Datenintegration, stellen Sie sicher, dass der Flash `AllowScriptAccess` -Parameter auf `always` oder `sameDomain`. [!UICONTROL Flash DIL] Die Datenerfassung funktioniert nicht, wenn `AllowScriptAccess` auf `never`. Siehe [Zugriff auf Skripte oder Host-Web-Seite steuern](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Codeplatzierung**

Versuchen Sie, JS zu platzieren. [!UICONTROL DIL] Datenerfassungsmodul auf der Seite, damit es vor dem [!DNL FLA] -Datei. Wenn die Variable [!DNL FLA] Datei wird zuerst geladen, bevor [!UICONTROL DIL] die Datenerfassung abgeschlossen ist, können Sie die ersten Datensignale verpassen, die [!UICONTROL Flash DIL] sendet an dieses Modul. Sobald jedoch die Variable [!UICONTROL DIL] Datenerfassungsmodul erfasst alle nachfolgenden SWF-Dateidaten, die von [!UICONTROL Flash DIL].

## Vom Flash-DIL erfasste Daten {#data-collected}

[!UICONTROL Flash DIL] erfasst Seitenansichts-, Link-Tracking-, Medien-Tracking- und andere Medienansichtsereignisse aus der Adobe [!UICONTROL AppMeasurement] -Bibliothek.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Seitenansichtsereignisse**

Sofern nicht anders angegeben durch `s.trackVars`, [!UICONTROL Flash DIL] erfasst die folgenden Daten aus Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Linktracking-Ereignisse**

Sofern nicht anders angegeben durch `s.linkTrackVars`, [!UICONTROL Flash DIL] erfasst die folgenden Daten aus Adobe [!UICONTROL AppMeasurement]:

* `pe` (Nachverfolgungslink namens)
* `pev1` (Link-URL)
* `pev2`(Link-Text)

**Medien-Tracking-Ereignisse**

Sofern nicht anders angegeben durch `s.Media.trackVars`, [!UICONTROL Flash DIL] erfasst alle im Abschnitt Seitenansichtsereignisse aufgezählten Daten.

**Andere Datenpunkte**

Daten aus diesen Parametern werden standardmäßig erfasst:

* `mediaName` (Medien-/Videoelementname)
* `mediaAdName` (Anzeigenname)
* `mediaAdParentName` (Name des Primärmedieninhalts, unter dem die Anzeige verschachtelt ist)
* `mediaAdParentPod` (Die Werbeunterbrechung innerhalb des Hauptinhalts, in dem die Anzeige wiedergegeben wird)
* `mediaAdParentPodPos` (Die numerische Position in der Werbeunterbrechung, an der die Anzeige wiedergegeben wird. Innerhalb eines Pods können mehrere Anzeigen wiedergegeben werden.

## Flash DIL Data in Audience Manager {#flash-dil-data}

Die [!UICONTROL Flash DIL] -Modul wandelt Adobe AppMeasurement-Daten in Audience Manager-Eigenschaften und nicht verwendete Signale um.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars]und -Ereignisse funktionieren wie Eigenschaften in Audience Manager. Eigenschaften sind Schlüssel-Wert-Paare und werden zum Erstellen von Segmenten verwendet. Beispiel: bei einer Analytics-Prop wie `c30=foo`, `c30` ist der Schlüssel (eine Konstante) und `foo` ist der Wert (eine Variable).

**Audience Manager-Eigenschaften mit Analytics-Variablen abgleichen**

So verwenden Sie die Analytics-Daten, die von [!UICONTROL Flash DIL], sollten Sie Audience Manager-Eigenschaften erstellen, denen der Schlüsselwert vorangestellt ist. `c_`.

Beispiele finden Sie in der Tabelle:

| Analytics-Datenelement | Analytics-Beispiel | Als Audience Manager-Eigenschaft |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics-Daten als nicht verwendete Signale**

Audience Manager akzeptiert Analytics [!UICONTROL Props], [!UICONTROL eVars]und -Ereignissen auch ohne entsprechende Eigenschaft. In diesem Fall sind die Daten nicht für die Erstellung von Eigenschaften verfügbar und werden im [Bericht zu nicht verwendeten Signalen](../reporting/dynamic-reports/unused-signals.md) anstatt. Um diese Informationen optimal zu nutzen, erstellen Sie Audience Manager-Eigenschaften, die mit den Analytics-Daten übereinstimmen, die von der [!UICONTROL Flash DIL] -Bibliothek.

## Flash DIL ActionScript Library {#flash-dil-actionscript}

Code für Ihre [!DNL Flash] -Objekt, um Analytics-Daten an Audience Manager zu senden.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Für jeden [!DNL Flash] -Objekt, unterstützt der Code eine Partnerinstanz ( `d.partner`).
>
>* Erfordert die Adobe [!UICONTROL AppMeasurement] [!DNL AS] Bibliotheksversion 3.5.2 oder höher.

```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

>[!MORELIKETHIS]
>
>* [Eigenschaften ](../features/traits/trait-details-page.md)
>* [Signale, Eigenschaften und Segmente](../reference/signal-trait-segment.md)
>* [Schlüssel-Wert-Paare – Erklärung](../reference/key-value-pairs-explained.md)
>* [Anforderungen an Präfixe für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)

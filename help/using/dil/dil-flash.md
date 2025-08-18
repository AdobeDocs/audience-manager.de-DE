---
description: Erfassen Sie die von FLA-Dateien an Analytics gesendeten Daten und verwenden Sie diese Informationen in Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash-DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 2%

---

# Flash-DIL{#flash-dil}

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung des [!DNL Data Integration Library (DIL)] und der [!DNL DIL] eingestellt.
>
>Bestehende Kundinnen und Kunden können ihre [!DNL DIL] Implementierung weiterhin nutzen. Adobe wird jedoch keine [!DNL DIL] über diesen Punkt hinaus entwickeln. Kundinnen und Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) auf ihre langfristige Datenerfassungsstrategie hin zu überprüfen.
>
>Kunden, die nach Juli 2023 neue Datenerfassungsintegrationen implementieren möchten, sollten stattdessen [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) verwenden.

Erfassen Sie die von FLA-Dateien an Analytics gesendeten Daten und verwenden Sie diese Informationen in Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] ist eine [!DNL ActionScript] Code-Bibliothek, mit der Sie Videowiedergabedaten in Audience Manager verwenden können. [!DNL Flash DIL] erfasst SWF-Inhalte, die die Adobe [!UICONTROL AppMeasurement]-Bibliothek an Analytics übergibt. [!DNL Flash DIL] sendet diese Daten an das separate [!UICONTROL DIL] JavaScript-Datenerfassungsmodul, das diese Informationen an Audience Manager weitergibt. Aus der [!UICONTROL Props] erfasste Analytics-Daten ( [!UICONTROL eVars], [!DNL FLA], Ereignisse usw.) sind in Audience Manager als Eigenschaften oder nicht verwendete Signale verfügbar.

## Voraussetzungen für die Flash DIL-Datenerfassung {#requirements}

Allgemeine Implementierungs- und Code-bezogene Anforderungen.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementierungsanforderungen**

[!UICONTROL Flash] Datenerfassung erfordert Folgendes:

* Die [!UICONTROL DIL]-Klassenbibliothek ( `dil.swc`). Beziehen Sie die [!UICONTROL DIL]-Klassenbibliothek von Ihrem Partner Solutions-Kontakt.

* JavaScript [!UICONTROL DIL] Datenerfassungs-Code auf der Seite.
* [DIL ActionScript-Bibliothek](../dil/dil-flash.md#flash-dil-actionscript) geladen in das Flash-Objekt, aus dem Sie Daten erfassen möchten.
* Die Adobe [!DNL AppMeasurement] [!DNL AS]-Bibliothek (Version 3.5.2 oder höher) hat das [!DNL Flash]-Objekt geladen, aus dem Sie Daten erfassen möchten.

**Setzen Sie AllowScriptAccess auf `Always` oder`sameDomain`**

Die `AllowScriptAccess` im HTML-Code, die eine SWF-Datei lädt, steuert die Möglichkeit, den ausgehenden URL-Zugriff über die SWF-Datei durchzuführen. Wenn Sie eine [!UICONTROL Flash DIL] Datenintegration konfigurieren, stellen Sie sicher, dass der Flash-`AllowScriptAccess`-Parameter auf `always` oder `sameDomain` gesetzt ist. [!UICONTROL Flash DIL] Datenerfassung funktioniert nicht, wenn `AllowScriptAccess` auf `never` gesetzt ist. Siehe [Zugriff auf Skripte steuern oder Web-Seite hosten](https://helpx.adobe.com/de/flash/kb/control-access-scripts-host-web.html).

**JS[!UICONTROL DIL]Code-Platzierung**

Versuchen Sie, das JS [!UICONTROL DIL]-Datenerfassungsmodul auf der Seite zu platzieren, damit es vor der [!DNL FLA] geladen wird. Wenn die [!DNL FLA] Datei zuerst geladen wird, bevor [!UICONTROL DIL] Datenerfassung fertig ist, können die ersten Datensignale, die [!UICONTROL Flash DIL] an dieses Modul sendet, übersehen werden. Nach der Instanziierung erfasst das Datenerfassungsmodul [!UICONTROL DIL] alle nachfolgenden SWF-Dateidaten, die von [!UICONTROL Flash DIL] übergeben werden.

## Von Flash DIL erfasste Daten {#data-collected}

[!UICONTROL Flash DIL] erfasst Seitenansichten, Linktracking, Medientracking und andere Medienansichtsereignisse aus der Adobe-[!UICONTROL AppMeasurement].

<!-- 

r_flash_dil_data_collected.xml

 -->

**Seitenansichtsereignisse**

Sofern von `s.trackVars` nicht anders angegeben, erfasst [!UICONTROL Flash DIL] die folgenden Daten aus Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Linktracking-Ereignisse**

Sofern von `s.linkTrackVars` nicht anders angegeben, erfasst [!UICONTROL Flash DIL] die folgenden Daten aus Adobe [!UICONTROL AppMeasurement]:

* `pe` (Art des aufgerufenen Tracklinks)
* `pev1` (Link-URL)
* `pev2`(Link-Text)

**Medien-Tracking-Ereignisse**

Sofern nicht durch `s.Media.trackVars` anders angegeben, erfasst [!UICONTROL Flash DIL] alle im Abschnitt „Seitenansichtsereignisse“ aufgelisteten Daten.

**Andere Datenpunkte**

Daten aus diesen Parametern werden standardmäßig erfasst:

* `mediaName` (Name des Medien-/Videoelements)
* `mediaAdName` (Anzeigename)
* `mediaAdParentName` (Name des primären Medieninhalts, unter dem die Anzeige verschachtelt ist)
* `mediaAdParentPod` (Der Pod oder die Anzeigenunterbrechung innerhalb des primären Inhalts, in dem die Anzeige abgespielt wird)
* `mediaAdParentPodPos` (Die numerische Position innerhalb des Pods, an der die Anzeige abgespielt wird. Innerhalb eines Pods können mehrere Anzeigen gespielt werden.

## Flash-DIL-Daten in Audience Manager {#flash-dil-data}

Das [!UICONTROL Flash DIL] Modul wandelt Adobe AppMeasurement-Daten in Audience Manager-Eigenschaften und nicht verwendete Signale um.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics-[!UICONTROL Props], -[!UICONTROL eVars] und -Ereignisse funktionieren wie Eigenschaften in Audience Manager. Eigenschaften sind Schlüssel-Wert-Paare und werden zum Erstellen von Segmenten verwendet. Beispielsweise ist in einer Analytics-Prop wie `c30=foo` `c30` der Schlüssel (eine Konstante) und `foo` der Wert (eine Variable).

**Abgleichen von Audience Manager-Eigenschaften mit Analytics-Variablen**

Um die von [!UICONTROL Flash DIL] weitergegebenen Analytics-Daten zu verwenden, sollten Sie Audience Manager-Eigenschaften erstellen, bei denen der Schlüsselwert mit dem Präfix `c_` versehen ist.

Beispiele finden Sie in der Tabelle:

| Analytics-Datenelement | Analytics-Beispiel | Als Audience Manager-Eigenschaft |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **eVar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics-Daten als nicht verwendete Signale**

Audience Manager akzeptiert Analytics-[!UICONTROL Props], -[!UICONTROL eVars] und -Ereignisse auch ohne entsprechende Eigenschaft. In diesem Fall sind die Daten für die Erstellung von Eigenschaften nicht verfügbar und werden stattdessen im Bericht [Nicht verwendete Signale](../reporting/dynamic-reports/unused-signals.md) angezeigt. Um diese Informationen optimal zu nutzen, erstellen Sie Audience Manager-Eigenschaften, die mit den von der [!UICONTROL Flash DIL] übergebenen Analytics-Daten übereinstimmen.

## Flash DIL ActionScript-Bibliothek {#flash-dil-actionscript}

Code für Ihr [!DNL Flash]-Objekt zum Senden von Analytics-Daten an Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Für jedes [!DNL Flash]-Objekt unterstützt der Code nur eine Partnerinstanz ( `d.partner`).
>
>* Erfordert die Adobe [!UICONTROL AppMeasurement] [!DNL AS]-Bibliothek Version 3.5.2 oder höher.

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
>* [Eigenschaften](../features/traits/trait-details-page.md)
>* [Signale, Eigenschaften und Segmente](../reference/signal-trait-segment.md)
>* [Schlüssel-Wert-Paare – Erklärung](../reference/key-value-pairs-explained.md)
>* [Anforderungen an Präfixe für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)

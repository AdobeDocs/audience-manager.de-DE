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
source-wordcount: '686'
ht-degree: 2%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung der Erweiterung [!DNL Data Integration Library (DIL)] und der Erweiterung [!DNL DIL] eingestellt.
>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] -Implementierung verwenden. Adobe wird jedoch nicht mehr [!DNL DIL] als bisher entwickeln. Kunden wird empfohlen, das [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie zu bewerten.
>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten stattdessen das [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) verwenden.

Erfassen Sie Daten, die von FLA-Dateien an Analytics gesendet werden, und verwenden Sie diese Informationen in Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] ist eine [!DNL ActionScript] -Codebibliothek, mit der Sie mit Videowiedergabedaten in Audience Manager arbeiten können. [!DNL Flash DIL] erfasst SWF-Inhalte, die die Adobe [!UICONTROL AppMeasurement]-Bibliothek an Analytics übergibt. [!DNL Flash DIL] sendet diese Daten an das separate [!UICONTROL DIL] JavaScript-Datenerfassungsmodul, das diese Informationen an den Audience Manager übergibt. Analysedaten ( [!UICONTROL Props], [!UICONTROL eVars], Ereignisse usw.) aus der [!DNL FLA] -Datei erfasst werden, ist in Audience Manager als Eigenschaften oder nicht verwendete Signale verfügbar.

## Anforderungen an die Datenerfassung durch Flash-DIL {#requirements}

Allgemeine Implementierungs- und Code-bezogene Anforderungen.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementierungsanforderungen**

[!UICONTROL Flash] Datenerfassung erfordert:

* Die [!UICONTROL DIL]-Klassenbibliothek ( `dil.swc`). Rufen Sie die [!UICONTROL DIL]-Klassenbibliothek von Ihrem Partner Solutions-Kontakt ab.

* JavaScript [!UICONTROL DIL] Datenerfassungscode auf der Seite.
* [DIL ActionScript-Bibliothek](../dil/dil-flash.md#flash-dil-actionscript), die in das Flash-Objekt geladen wurde, aus dem Sie Daten erfassen möchten.
* Adobe [!DNL AppMeasurement] [!DNL AS] -Bibliothek (Version 3.5.2 oder höher) hat das [!DNL Flash] -Objekt geladen, aus dem Sie Daten erfassen möchten.

**Setzen Sie AllowScriptAccess auf `Always` oder`sameDomain`**

Der HTML-Code `AllowScriptAccess`, der eine SWF-Datei lädt, steuert die Möglichkeit, aus der SWF-Datei ausgehenden URL-Zugriff durchzuführen. Wenn Sie eine [!UICONTROL Flash DIL] -Datenintegration konfigurieren, stellen Sie sicher, dass der Flash `AllowScriptAccess` -Parameter auf `always` oder `sameDomain` eingestellt ist. Die [!UICONTROL Flash DIL] -Datenerfassung funktioniert nicht, wenn `AllowScriptAccess` auf `never` gesetzt ist. Siehe [Steuern des Zugriffs auf Skripte oder Hostwebseite](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Codeplatzierung**

Versuchen Sie, das JS [!UICONTROL DIL]-Datenerfassungsmodul auf der Seite zu platzieren, damit es vor der [!DNL FLA]-Datei geladen wird. Wenn die [!DNL FLA] -Datei zuerst geladen wird, bevor die [!UICONTROL DIL] -Datenerfassung abgeschlossen ist, können Sie die anfänglichen Datensignale verpassen, die [!UICONTROL Flash DIL] an dieses Modul sendet. Nach der Instanziierung erfasst das Datenerfassungsmodul [!UICONTROL DIL] jedoch alle nachfolgenden SWF-Dateidaten, die von [!UICONTROL Flash DIL] übergeben werden.

## Von Flash DIL erfasste Daten {#data-collected}

[!UICONTROL Flash DIL] erfasst Seitenansichts-, Link-Tracking-, Medien-Tracking- und andere Medienansichtsereignisse aus der Adobe [!UICONTROL AppMeasurement] -Bibliothek.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Seitenansichtsereignisse**

Sofern nicht durch `s.trackVars` anders angegeben, erfasst [!UICONTROL Flash DIL] die folgenden Daten aus Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Linktracking-Ereignisse**

Sofern nicht durch `s.linkTrackVars` anders angegeben, erfasst [!UICONTROL Flash DIL] die folgenden Daten von Adobe [!UICONTROL AppMeasurement]:

* `pe` (Typ des Nachverfolgungslinks mit Namen)
* `pev1` (Link-URL)
* `pev2`(Link-Text)

**Medien-Tracking-Ereignisse**

Sofern nicht durch `s.Media.trackVars` anders angegeben, erfasst [!UICONTROL Flash DIL] alle im Abschnitt Seitenansichtsereignisse aufgezählten Daten.

**Andere Datenpunkte**

Daten aus diesen Parametern werden standardmäßig erfasst:

* `mediaName` (Medien-/Videoelementname)
* `mediaAdName` (Anzeigenname)
* `mediaAdParentName` (Name des Primärmedieninhalts, unter dem die Anzeige verschachtelt ist)
* `mediaAdParentPod` (Die Werbeunterbrechung innerhalb des Hauptinhalts, in der die Anzeige wiedergegeben wird)
* `mediaAdParentPodPos` (Die numerische Position in der Werbeunterbrechung, an der die Anzeige wiedergegeben wird. Innerhalb eines Pods können mehrere Anzeigen wiedergegeben werden.

## Flash DIL Data in Audience Manager {#flash-dil-data}

Das Modul [!UICONTROL Flash DIL] wandelt Adobe AppMeasurement-Daten in Audience Manager-Eigenschaften und nicht verwendete Signale um.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars] und Ereignisse funktionieren wie Eigenschaften in Audience Manager. Eigenschaften sind Schlüssel-Wert-Paare und werden zum Erstellen von Segmenten verwendet. In einer Analytics-Prop wie `c30=foo` ist beispielsweise `c30` der Schlüssel (eine Konstante) und `foo` der Wert (eine Variable).

**Audience Manager-Eigenschaften mit Analytics-Variablen abgleichen**

Um die von [!UICONTROL Flash DIL] übergebenen Analytics-Daten zu verwenden, sollten Sie Audience Manager-Eigenschaften erstellen, denen der Schlüsselwert mit dem Präfix `c_` vorangestellt ist.

Beispiele finden Sie in der Tabelle:

| Analytics-Datenelement | Analytics-Beispiel | Als Audience Manager-Eigenschaft |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics-Daten als nicht verwendete Signale**

Audience Manager akzeptiert Analytics-Ereignisse [!UICONTROL Props], [!UICONTROL eVars] und auch ohne entsprechende Eigenschaft. In diesem Fall sind die Daten nicht für die Erstellung von Eigenschaften verfügbar und werden stattdessen im Bericht [Nicht verwendete Signale](../reporting/dynamic-reports/unused-signals.md) angezeigt. Um diese Informationen optimal zu nutzen, erstellen Sie Audience Manager-Eigenschaften, die mit den von der [!UICONTROL Flash DIL] -Bibliothek übergebenen Analytics-Daten übereinstimmen.

## Flash DIL ActionScript Library {#flash-dil-actionscript}

Code für Ihr [!DNL Flash] -Objekt, um Analytics-Daten an Audience Manager zu senden.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Für jedes [!DNL Flash] -Objekt unterstützt der Code nur eine Partnerinstanz ( `d.partner`).
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
>* [Eigenschaften](../features/traits/trait-details-page.md)
>* [Signale, Eigenschaften und Segmente](../reference/signal-trait-segment.md)
>* [Schlüssel-Wert-Paare – Erklärung](../reference/key-value-pairs-explained.md)
>* [Anforderungen an Präfixe für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)

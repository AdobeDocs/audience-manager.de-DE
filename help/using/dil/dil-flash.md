---
description: Erfassen von Daten, die von FLA-Dateien an Analytics gesendet werden, und Arbeiten mit diesen Informationen in Audience Manager.
seo-description: Erfassen von Daten, die von FLA-Dateien an Analytics gesendet werden, und Arbeiten mit diesen Informationen in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 4%

---


# Flash DIL{#flash-dil}

Erfassen von Daten, die von FLA-Dateien an Analytics gesendet werden, und Arbeiten mit diesen Informationen in Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] ist eine  [!DNL ActionScript] Codebibliothek, mit der Sie mit Videodaten in Audience Manager arbeiten können. [!DNL Flash DIL] erfasst SWF-Inhalte, die die  [!UICONTROL AppMeasurement] Bibliotheksbibliothek an Analytics übergibt. [!DNL Flash DIL] sendet diese Daten an das separate  [!UICONTROL DIL] JavaScript-Datenerfassungsmodul, das diese Informationen an Audience Manager weiterleitet. Analytics-Daten ( [!UICONTROL Props], [!UICONTROL eVars], Ereignis usw.) erfasst aus der [!DNL FLA]-Datei ist in Audience Manager als Eigenschaften oder nicht verwendete Signale verfügbar.

## Voraussetzungen für die Datenerfassung mit Flash DIL {#requirements}

Allgemeine Implementierungs- und codebezogene Anforderungen.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementierungsanforderungen**

[!UICONTROL Flash] Datenerfassung erfordert:

* Die [!UICONTROL DIL]-Klassenbibliothek ( `dil.swc`). Rufen Sie die [!UICONTROL DIL]-Klassenbibliothek von Ihrem Partner Solutions-Kontakt ab.

* JavaScript [!UICONTROL DIL]-Datenerfassungscode auf der Seite.
* [DIL ActionScript, das in das Flash-Objekt, von dem Sie Daten erfassen möchten, ](../dil/dil-flash.md#flash-dil-actionscript) bibliothekaryloaded ist.
* Adobe [!DNL AppMeasurement] [!DNL AS] Bibliothek (Version 3.5.2 oder höher) hat das [!DNL Flash]-Objekt geladen, von dem Sie Daten erfassen möchten.

**AllowScriptAccess auf  `Always` oder`sameDomain`**

Der `AllowScriptAccess`-Code im HTML-Code, der eine SWF-Datei lädt, steuert die Fähigkeit, einen ausgehenden URL-Zugriff von der SWF-Datei aus durchzuführen. Wenn Sie eine [!UICONTROL Flash DIL]-Datenintegration konfigurieren, stellen Sie sicher, dass der Flash `AllowScriptAccess` auf `always` oder `sameDomain` eingestellt ist. [!UICONTROL Flash DIL] Die Datenerfassung funktioniert nicht, wenn  `AllowScriptAccess` sie auf  `never`. Siehe [Zugriff auf Skripte oder Host-Webseite](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html) steuern.

**JS- [!UICONTROL DIL] Codeplatzierung**

Versuchen Sie, das Datenerfassungsmodul JS [!UICONTROL DIL] auf der Seite zu platzieren, damit es vor der Datei [!DNL FLA] geladen wird. Wenn die [!DNL FLA]-Datei zuerst geladen wird, bevor [!UICONTROL DIL] die Datenerfassung abgeschlossen ist, können Sie die anfänglichen Datensignale verpassen, die [!UICONTROL Flash DIL] an dieses Modul sendet. Nach der Instanziierung erfasst das Datenerfassungsmodul jedoch alle nachfolgenden SWF-Dateidaten, die von [!UICONTROL Flash DIL] weitergegeben werden.[!UICONTROL DIL]

## Von Flash DIL erfasste Daten {#data-collected}

[!UICONTROL Flash DIL] erfasst die Ansicht von Seiten, die Linktracking, die Medienverfolgung und andere Ereignis zur Ansicht von Medien aus der  [!UICONTROL AppMeasurement] Medienbibliothek.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Ereignisse zur Ansicht der Seite**

Sofern von `s.trackVars` nichts anderes angegeben, erfasst [!UICONTROL Flash DIL] die folgenden Daten aus Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Linktracking-Ereignis**

Sofern von `s.linkTrackVars` nichts anderes angegeben, erfasst [!UICONTROL Flash DIL] die folgenden Daten aus der Adobe [!UICONTROL AppMeasurement]:

* `pe` (Nachverfolgungslink-Typ genannt)
* `pev1` (Link-URL)
* `pev2`(Linktext)

**Medienverfolgung - Ereignisse**

Sofern nicht anders durch `s.Media.trackVars` angegeben, erfasst [!UICONTROL Flash DIL] alle im Abschnitt &quot;Ereignis der Ansicht&quot;aufgelisteten Daten.

**Andere Datenpunkte**

Daten aus diesen Parametern werden standardmäßig erfasst:

* `mediaName` (Name des Medien-/Videoelements)
* `mediaAdName` (Anzeigenname)
* `mediaAdParentName` (Name des primären Medieninhalts, unter dem die Anzeige verschachtelt ist)
* `mediaAdParentPod` (Die Werbeunterbrechung innerhalb des Hauptinhalts, in dem die Anzeige wiedergegeben wird)
* `mediaAdParentPodPos` (Die numerische Position innerhalb der Werbeunterbrechung, an der die Anzeige wiedergegeben wird.) Innerhalb eines Pods können mehrere Anzeigen abgespielt werden.

## Flash DIL-Daten in Audience Manager {#flash-dil-data}

Das Modul [!UICONTROL Flash DIL] wandelt Adobe AppMeasurement-Daten in Audience Manager- und nicht verwendete Signale um.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars] und Ereignis funktionieren wie Eigenschaften in Audience Manager. Eigenschaften sind Schlüssel-Wert-Paare und werden zum Aufbau von Segmenten verwendet. Beispiel: In einer Analytics-Eigenschaft wie `c30=foo` ist `c30` der Schlüssel (eine Konstante) und `foo` der Wert (eine Variable).

**Audience Manager-Eigenschaften mit Analytics-Variablen abgleichen**

Um die von [!UICONTROL Flash DIL] übergebenen Analytics-Daten zu verwenden, sollten Sie Audience Manager-Eigenschaften mit dem Schlüsselwert mit dem Präfix `c_` erstellen.

Beispiele finden Sie in der Tabelle:

| Analytics-Datenelement | Analytics-Beispiel | Als Audience Manager-Eigenschaft |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics-Daten als nicht verwendete Signale**

Audience Manager akzeptiert Analytics [!UICONTROL Props]-, [!UICONTROL eVars]- und Ereignis auch ohne entsprechende Eigenschaft. In diesem Fall sind die Daten nicht für die Erstellung von Eigenschaften verfügbar und werden stattdessen im Bericht [Nicht verwendete Signale](../reporting/dynamic-reports/unused-signals.md) angezeigt. Um diese Informationen optimal zu nutzen, erstellen Sie Audience Manager-Eigenschaften, die mit den Analytics-Daten übereinstimmen, die von der [!UICONTROL Flash DIL]-Bibliothek übergeben werden.

## Flash DIL ActionScript Library {#flash-dil-actionscript}

Code für das [!DNL Flash]-Objekt, um Analytics-Daten an Audience Manager zu senden.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Für jedes [!DNL Flash]-Objekt unterstützt der Code nur eine Partnerinstanz ( `d.partner`).
   >
   >
* Erfordert die Adobe [!UICONTROL AppMeasurement] [!DNL AS] Bibliotheksversion 3.5.2 oder höher.


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


---
description: Erfassen Sie Daten, die von FLA-Dateien an Analytics gesendet werden, und verwenden Sie diese Informationen in Audience Manager.
seo-description: Erfassen Sie Daten, die von FLA-Dateien an Analytics gesendet werden, und verwenden Sie diese Informationen in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL-Implementierung
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 4%

---

# Flash DIL{#flash-dil}

Erfassen Sie Daten, die von FLA-Dateien an Analytics gesendet werden, und verwenden Sie diese Informationen in Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] ist eine  [!DNL ActionScript] Codebibliothek, mit der Sie mit Videowiedergabedaten in Audience Manager arbeiten können. [!DNL Flash DIL] erfasst SWF-Inhalte, die die Adobe- [!UICONTROL AppMeasurement] Bibliothek an Analytics übergibt. [!DNL Flash DIL] sendet diese Daten an das separate  [!UICONTROL DIL] JavaScript-Datenerfassungsmodul, das diese Informationen an Audience Manager übergibt. Analytics-Daten ( [!UICONTROL Props], [!UICONTROL eVars], Ereignisse usw.) aus der Datei [!DNL FLA] erfasst wird, ist in Audience Manager als Eigenschaften oder nicht verwendete Signale verfügbar.

## Anforderungen an die Datenerfassung durch Flash DIL {#requirements}

Allgemeine Implementierungs- und Code-bezogene Anforderungen.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementierungsanforderungen**

[!UICONTROL Flash] Die Datenerfassung erfordert:

* Die [!UICONTROL DIL]-Klassenbibliothek ( `dil.swc`). Rufen Sie die Klassenbibliothek [!UICONTROL DIL] von Ihrem Partner Solutions-Ansprechpartner ab.

* JavaScript [!UICONTROL DIL]-Datenerfassungscode auf der Seite.
* [DIL ActionScript-](../dil/dil-flash.md#flash-dil-actionscript) Bibliothek in das Flash-Objekt geladen, aus dem Sie Daten erfassen möchten.
* Adobe [!DNL AppMeasurement] [!DNL AS] -Bibliothek (Version 3.5.2 oder höher) hat das [!DNL Flash] -Objekt geladen, aus dem Sie Daten erfassen möchten.

**Setzen Sie AllowScriptAccess auf  `Always` oder`sameDomain`**

Der `AllowScriptAccess` im HTML-Code, der eine SWF-Datei lädt, steuert die Möglichkeit, aus der SWF-Datei ausgehenden URL-Zugriff durchzuführen. Stellen Sie beim Konfigurieren einer [!UICONTROL Flash DIL]-Datenintegration sicher, dass der Flash `AllowScriptAccess` auf `always` oder `sameDomain` gesetzt ist. [!UICONTROL Flash DIL] Die Datenerfassung funktioniert nicht, wenn  `AllowScriptAccess` auf  `never`gesetzt ist. Siehe [Zugriff auf Skripte steuern oder Hostwebseite](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS- [!UICONTROL DIL] Codeplatzierung**

Versuchen Sie, das JS-Datenerfassungsmodul [!UICONTROL DIL] auf der Seite zu platzieren, damit es vor der Datei [!DNL FLA] geladen wird. Wenn die [!DNL FLA]-Datei zuerst geladen wird, bevor die [!UICONTROL DIL]-Datenerfassung abgeschlossen ist, können Sie die ersten Datensignale verpassen, die [!UICONTROL Flash DIL] an dieses Modul sendet. Nach der Instanziierung erfasst das Datenerfassungsmodul [!UICONTROL DIL] jedoch alle nachfolgenden SWF-Dateidaten, die von [!UICONTROL Flash DIL] übergeben werden.

## Von Flash-DIL erfasste Daten {#data-collected}

[!UICONTROL Flash DIL] erfasst Seitenansichts-, Linktracking-, Medien-Tracking- und andere Medienansichtsereignisse aus der Adobe- [!UICONTROL AppMeasurement] Bibliothek.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Seitenansichtsereignisse**

Sofern nicht anders von `s.trackVars` angegeben, erfasst [!UICONTROL Flash DIL] die folgenden Daten aus Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Linktracking-Ereignisse**

Sofern nicht anders durch `s.linkTrackVars` angegeben, erfasst [!UICONTROL Flash DIL] die folgenden Daten aus der Adobe [!UICONTROL AppMeasurement]:

* `pe` (Nachverfolgungslink-Typ genannt)
* `pev1` (Link-URL)
* `pev2`(Link-Text)

**Medien-Tracking-Ereignisse**

Sofern durch `s.Media.trackVars` nichts anderes angegeben ist, erfasst [!UICONTROL Flash DIL] alle im Abschnitt &quot;Seitenansichtsereignisse&quot;aufgelisteten Daten.

**Andere Datenpunkte**

Daten aus diesen Parametern werden standardmäßig erfasst:

* `mediaName` (Medien-/Videoelementname)
* `mediaAdName` (Anzeigenname)
* `mediaAdParentName` (Name des Primärmedieninhalts, unter dem die Anzeige verschachtelt ist)
* `mediaAdParentPod` (Die Werbeunterbrechung innerhalb des Hauptinhalts, in dem die Anzeige wiedergegeben wird)
* `mediaAdParentPodPos` (Die numerische Position in der Werbeunterbrechung, an der die Anzeige wiedergegeben wird. Innerhalb eines Pods können mehrere Anzeigen wiedergegeben werden.

## Flash DIL Daten in Audience Manager {#flash-dil-data}

Das Modul [!UICONTROL Flash DIL] wandelt Adobe AppMeasurement-Daten in Audience Manager-Eigenschaften und nicht verwendete Signale um.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars] und -Ereignisse funktionieren wie Eigenschaften in Audience Manager. Eigenschaften sind Schlüssel-Wert-Paare und werden zum Erstellen von Segmenten verwendet. In einer Analytics-Eigenschaft wie `c30=foo` ist `c30` beispielsweise der Schlüssel (eine Konstante) und `foo` der Wert (eine Variable).

**Audience Manager-Eigenschaften mit Analytics-Variablen abgleichen**

Um die von [!UICONTROL Flash DIL] übergebenen Analytics-Daten zu verwenden, sollten Sie Audience Manager-Eigenschaften erstellen, denen der Schlüsselwert `c_` vorangestellt ist.

Beispiele finden Sie in der Tabelle:

| Analytics-Datenelement | Analytics-Beispiel | Als Audience Manager-Eigenschaft |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics-Daten als nicht verwendete Signale**

Audience Manager akzeptiert Analytics [!UICONTROL Props], [!UICONTROL eVars] und -Ereignisse auch ohne entsprechende Eigenschaft. In diesem Fall sind die Daten nicht für die Erstellung von Eigenschaften verfügbar und werden stattdessen im Bericht [Nicht verwendete Signale](../reporting/dynamic-reports/unused-signals.md) angezeigt. Um diese Informationen optimal zu nutzen, erstellen Sie Audience Manager-Eigenschaften, die mit den Analytics-Daten übereinstimmen, die von der [!UICONTROL Flash DIL]-Bibliothek übergeben werden.

## Flash DIL ActionScript Library {#flash-dil-actionscript}

Code für Ihr [!DNL Flash]-Objekt, um Analytics-Daten an Audience Manager zu senden.

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
* [Signale, Eigenschaften und Segmente](../reference/signal-trait-segment.md)
* [Schlüssel-Wert-Paare – Erklärung](../reference/key-value-pairs-explained.md)
* [Anforderungen an Präfixe für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)


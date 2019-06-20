---
description: Erfassen von Daten, die von FLA-Dateien an Analytics gesendet werden und mit diesen Informationen in Audience Manager arbeiten.
seo-description: Erfassen von Daten, die von FLA-Dateien an Analytics gesendet werden und mit diesen Informationen in Audience Manager arbeiten.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833 cfd -768 e -4 b 16-95 c 5-debd 8411 df 38
translation-type: tm+mt
source-git-commit: 49fff90fa1330c59360e16f2a56e8fba7d4c43dc

---


# Flash DIL{#flash-dil}

Erfassen von Daten, die von FLA-Dateien an Analytics gesendet werden und mit diesen Informationen in Audience Manager arbeiten.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] ist eine [!DNL ActionScript] Codebibliothek, mit der Sie mit Videowiedergabedaten in Audience Manager arbeiten können. [!DNL Flash DIL] funktioniert durch Erfassung von SWF-Inhalten, die die Adobe [!UICONTROL AppMeasurement] -Bibliothek in Analytics übergibt. [!DNL Flash DIL] sendet diese Daten an das separate [!UICONTROL DIL] javascript-Datenerfassungsmodul, das diese Informationen an Audience Manager weiterleitet. Analytics-Daten ( [!UICONTROL Props][!UICONTROL eVars], Ereignisse usw.) aus der [!DNL FLA] Datei erfasst ist, ist in Audience Manager als Eigenschaften oder nicht verwendete Signale verfügbar.

## Anforderungen für die Flash DIL-Datenerfassung {#requirements}

Allgemeine Implementierung und Code-bezogene Anforderungen.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementierungsanforderungen**

[!UICONTROL Flash] Die Datenerfassung erfordert Folgendes:

* [!UICONTROL DIL] Die Klassenbibliothek ( `dil.swc`). Besorgen Sie sich die [!UICONTROL DIL] Klassenbibliothek aus Ihrem Partner-Lösungskontakt.

* Javascript [!UICONTROL DIL] -Datenerfassungscode auf der Seite.
* [DIL actionscript-Bibliothek](../dil/dil-flash.md#flash-dil-actionscript) in das Flash-Objekt geladen, aus dem Sie Daten erfassen möchten.
* Die Adobe [!DNL AppMeasurement][!DNL AS] -Bibliothek (Version 3.5.2 oder höher) hat das [!DNL Flash] Objekt geladen, aus dem Daten erfasst werden sollen.

**Legen Sie allowscriptaccess auf`Always`oder`sameDomain`**

Der `AllowScriptAccess` in HTML-Code, der eine SWF-Datei lädt, steuert die Fähigkeit, aus der SWF-Datei ausgehende URL-Zugriff durchzuführen. Stellen Sie beim Konfigurieren einer [!UICONTROL Flash DIL] Datenintegration sicher, dass der Flash `AllowScriptAccess` -Parameter auf `always` oder `sameDomain`. [!UICONTROL Flash DIL] die Datenerfassung funktioniert nicht, wenn `AllowScriptAccess` sie festgelegt `never`ist. Siehe [Steuern des Zugriffs auf Skripte oder Host-Webseite](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS[!UICONTROL DIL]-Codeplatzierung**

Versuchen Sie, das JS [!UICONTROL DIL] -Datenerfassungsmodul auf der Seite zu platzieren, damit es vor der [!DNL FLA] Datei geladen wird. Wenn die [!DNL FLA] Datei zuerst geladen wird, können Sie die [!UICONTROL DIL] anfänglichen Datensignale, die an das Modul [!UICONTROL Flash DIL] gesendet werden, verwerfen. Nach der Instanziierung erfasst das [!UICONTROL DIL] Datenerfassungsmodul jedoch alle nachfolgenden SWF-Dateidaten, die von [!UICONTROL Flash DIL]Ihnen übergeben werden.

## Von Flash DIL erfasste Daten {#data-collected}

[!UICONTROL Flash DIL] erfasst Seitenansichten, Linktracking, Medienverfolgung und andere Medienansichtsereignisse aus der Adobe [!UICONTROL AppMeasurement] -Bibliothek.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Seitenansichtsereignisse**

Sofern nichts anderes angegeben ist, `s.trackVars`[!UICONTROL Flash DIL] werden die folgenden Daten aus Adobe appmeasurement erfasst:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Linktracking-Ereignisse**

Sofern nichts anderes angegeben ist, `s.linkTrackVars`[!UICONTROL Flash DIL] werden die folgenden Daten von Adobe [!UICONTROL AppMeasurement]erfasst:

* `pe` (Typ des Nachverfolgungslink-Links)
* `pev1` (Link-URL)
* `pev2`(Linktext)

**Medienverfolgungsereignisse**

Sofern nichts anderes angegeben ist, `s.Media.trackVars`[!UICONTROL Flash DIL] werden alle im Abschnitt &quot;Seitenansichtsereignisse&quot; erfassten Daten erfasst.

**Andere Datenpunkte**

Daten aus diesen Parametern werden standardmäßig erfasst:

* `mediaName` (Medien-/Videoelementname)
* `mediaAdName` (Anzeigenname)
* `mediaAdParentName` (Name des primären Medieninhalts, unter dem die Anzeige verschachtelt ist)
* `mediaAdParentPod` (Pod oder Werbeunterbrechung innerhalb des Hauptinhalts, in dem die Anzeige abgespielt wird)
* `mediaAdParentPodPos` (Die numerische Position innerhalb des Pods, in der die Anzeige wiedergegeben wird. In einem Pod können mehrere Anzeigen wiedergegeben werden.

>[!MORE_ LIKE_ THIS]
>
>* [Appmeasurement Flash, Flex und OSMF Implementierungshandbuch](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)


## Flash DIL-Daten in Audience Manager {#flash-dil-data}

Das [!UICONTROL Flash DIL] Modul verwandelt Adobe appmeasurement-Daten in Audience Manager-Eigenschaften und nicht verwendete Signale.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props]und [!UICONTROL eVars]Ereignisse funktionieren wie Eigenschaften in Audience Manager. Eigenschaften sind Schlüssel-Wert-Paare und werden zum Erstellen von Segmenten verwendet. Beispielsweise ist in einer Analytics-Prop der `c30=foo``c30` Schlüssel (eine Konstante) und `foo` der Wert (eine Variable).

**Zuordnung von Audience Manager-Eigenschaften zu Analytics-Variablen**

Um die von Ihnen [!UICONTROL Flash DIL]übergebenen Analytics-Daten zu verwenden, sollten Sie Audience Manager-Eigenschaften erstellen, bei denen der Schlüsselwert vorangestellt `c_`ist.

Beispiele finden Sie in der Tabelle:

| Analytics-Datenelement | Analytics-Beispiel | Als Audience Manager-Eigenschaften |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics-Daten als nicht verwendete Signale**

Audience Manager akzeptiert Analytics [!UICONTROL Props]und [!UICONTROL eVars]Ereignisse selbst ohne zugehörige Eigenschaft. In diesem Fall sind die Daten nicht für die Erstellung von Eigenschaften verfügbar und werden stattdessen im [Bericht &quot;Nicht verwendete Signale](../reporting/dynamic-reports/unused-signals.md) &quot; angezeigt. Um diese Informationen optimal nutzen zu können, erstellen Sie Audience Manager-Eigenschaften, die den von der [!UICONTROL Flash DIL] Bibliothek übermittelten Analytics-Daten entsprechen.

>[!MORE_ LIKE_ THIS]
>
>* [Eigenschaften](../features/traits/trait-details-page.md)
>* [Signale, Eigenschaften und Segmente](../reference/signal-trait-segment.md)
>* [Wichtige Wertpaare](../reference/key-value-pairs-explained.md)
>* [Präfix für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)


## Flash DIL actionscript-Bibliothek {#flash-dil-actionscript}

Code für das [!DNL Flash] Objekt, das Analytics-Daten an Audience Manager sendet.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Für jedes [!DNL Flash] Objekt unterstützt der Code nur eine Partnerinstanz ( `d.partner`).
   >
   >
* Erfordert die Adobe [!UICONTROL AppMeasurement][!DNL AS] Library Version 3.5.2 oder höher.
>



```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```


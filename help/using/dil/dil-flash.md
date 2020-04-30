---
description: Erfassen von Daten, die von FLA-Dateien an Analytics gesendet werden, und Arbeiten mit diesen Informationen in Audience Manager.
seo-description: Erfassen von Daten, die von FLA-Dateien an Analytics gesendet werden, und Arbeiten mit diesen Informationen in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Flash DIL{#flash-dil}

Erfassen von Daten, die von FLA-Dateien an Analytics gesendet werden, und Arbeiten mit diesen Informationen in Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] ist eine [!DNL ActionScript] Codebibliothek, mit der Sie mit Videodaten in Audience Manager arbeiten können. [!DNL Flash DIL] erfasst SWF-Inhalte, die die Adobe- [!UICONTROL AppMeasurement] Bibliothek an Analytics übergibt. [!DNL Flash DIL] sendet diese Daten an das separate [!UICONTROL DIL] JavaScript-Datenerfassungsmodul, das diese Informationen an Audience Manager weiterleitet. Analytics-Daten ( [!UICONTROL Props], [!UICONTROL eVars]Ereignis usw.) Aus der [!DNL FLA] Datei erfasste Daten stehen im Audience Manager als Eigenschaften oder nicht verwendete Signale zur Verfügung.

## Anforderungen für die Flash DIL-Datenerfassung {#requirements}

Allgemeine Implementierungs- und codebezogene Anforderungen.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementierungsanforderungen**

[!UICONTROL Flash] Datenerfassung erfordert:

* Die [!UICONTROL DIL] Klassenbibliothek ( `dil.swc`). Rufen Sie die [!UICONTROL DIL] Klassenbibliothek von Ihrem Partner Solutions-Kontakt ab.

* JavaScript- [!UICONTROL DIL] Datenerfassungscode auf der Seite.
* [DIL-ActionScript-Bibliothek](../dil/dil-flash.md#flash-dil-actionscript) , die im Flash-Objekt geladen wird, von dem Sie Daten erfassen möchten.
* Adobe [!DNL AppMeasurement] Library (Version 3.5.2 oder höher) hat das Objekt geladen, von dem Sie Daten erfassen [!DNL AS] [!DNL Flash] möchten.

**AllowScriptAccess auf`Always`oder`sameDomain`**

Der `AllowScriptAccess` in-HTML-Code, der eine SWF-Datei lädt, steuert die Fähigkeit, aus der SWF-Datei ausgehenden URL-Zugriff durchzuführen. Stellen Sie beim Konfigurieren einer [!UICONTROL Flash DIL] Datenintegration sicher, dass der Flash- `AllowScriptAccess` Parameter auf `always` oder `sameDomain`eingestellt ist. [!UICONTROL Flash DIL] Die Datenerfassung funktioniert nicht, wenn `AllowScriptAccess` auf `never`. Siehe Zugriff auf Skripten [steuern oder Webseite](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)hosten.

**JS[!UICONTROL DIL]-Codeplatzierung**

Versuchen Sie, das JS- [!UICONTROL DIL] Datenerfassungsmodul auf der Seite zu platzieren, damit es vor der [!DNL FLA] Datei geladen wird. Wenn die [!DNL FLA] Datei zuerst geladen wird, bevor die [!UICONTROL DIL] Datenerfassung abgeschlossen ist, können Sie die anfänglichen Datensignale verpassen, die an dieses Modul [!UICONTROL Flash DIL] gesendet werden. Nach der Instanziierung erfasst das [!UICONTROL DIL] Datenerfassungsmodul jedoch alle nachfolgenden SWF-Dateidaten, die von [!UICONTROL Flash DIL]Ihnen weitergegeben werden.

## Von Flash DIL erfasste Daten {#data-collected}

[!UICONTROL Flash DIL] erfasst die Ansicht von Seiten, die Linktracking, die Medienverfolgung und andere Ereignis zur Ansicht von Medien aus der Adobe- [!UICONTROL AppMeasurement] Bibliothek.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Ereignisse zur Ansicht der Seite**

Erfasst die folgenden Daten aus Adobe AppMeasurement, sofern nicht anders angegeben `s.trackVars`[!UICONTROL Flash DIL] :

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Linktracking-Ereignis**

Erfasst die folgenden Daten von Adobe, sofern nicht anders angegeben `s.linkTrackVars`[!UICONTROL Flash DIL] : [!UICONTROL AppMeasurement]:

* `pe` (Nachverfolgungslink-Typ genannt)
* `pev1` (Link-URL)
* `pev2`(Linktext)

**Medienverfolgung - Ereignisse**

Wenn nicht anders angegeben von `s.Media.trackVars`erfasst [!UICONTROL Flash DIL] , werden alle im Abschnitt &quot;Ereignis der Ansicht&quot;aufgelisteten Daten erfasst.

**Andere Datenpunkte**

Daten aus diesen Parametern werden standardmäßig erfasst:

* `mediaName` (Name des Medien-/Videoelements)
* `mediaAdName` (Anzeigenname)
* `mediaAdParentName` (Name des primären Medieninhalts, unter dem die Anzeige verschachtelt ist)
* `mediaAdParentPod` (Die Werbeunterbrechung innerhalb des Hauptinhalts, in dem die Anzeige wiedergegeben wird)
* `mediaAdParentPodPos` (Die numerische Position innerhalb der Werbeunterbrechung, an der die Anzeige wiedergegeben wird.) Innerhalb eines Pods können mehrere Anzeigen abgespielt werden.

## Flash-DIL-Daten in Audience Manager {#flash-dil-data}

Das [!UICONTROL Flash DIL] Modul wandelt Adobe AppMeasurement-Daten in Audience Manager-Eigenschaften und nicht verwendete Signale um.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars]und Ereignis funktionieren wie Eigenschaften in Audience Manager. Eigenschaften sind Schlüssel-Wert-Paare und werden zum Aufbau von Segmenten verwendet. Beispiel: In einer Analytics-Prop wie `c30=foo`ist `c30` der Schlüssel (eine Konstante) und `foo` der Wert (eine Variable).

**Audience Manager-Eigenschaften mit Analytics-Variablen abgleichen**

Um die Analytics-Daten zu verwenden, die übergeben werden, [!UICONTROL Flash DIL]sollten Sie Audience Manager-Eigenschaften erstellen, denen der Schlüsselwert vorangestellt wird `c_`.

Beispiele finden Sie in der Tabelle:

| Analytics-Datenelement | Analytics-Beispiel | Audience Manager-Eigenschaft |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics-Daten als nicht verwendete Signale**

Audience Manager akzeptiert Analytics [!UICONTROL Props], [!UICONTROL eVars]und Ereignis auch ohne entsprechende Eigenschaften. In diesem Fall sind die Daten nicht für die Erstellung von Eigenschaften verfügbar und werden stattdessen im Bericht [&quot;](../reporting/dynamic-reports/unused-signals.md) Nicht verwendete Signale&quot;angezeigt. Um diese Informationen optimal nutzen zu können, erstellen Sie Audience Manager-Eigenschaften, die mit den von der [!UICONTROL Flash DIL] Bibliothek übergebenen Analytics-Daten übereinstimmen.

## Flash DIL ActionScript Library {#flash-dil-actionscript}

Code für Ihr [!DNL Flash] Objekt, um Analytics-Daten an Audience Manager zu senden.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Für jedes [!DNL Flash] Objekt unterstützt der Code nur eine Partnerinstanz ( `d.partner`).
   >
   >
* Erfordert die Adobe [!UICONTROL AppMeasurement] [!DNL AS] Library Version 3.5.2 oder höher.


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
>* [Erläuterung von Seiten mit Schlüsselwert](../reference/key-value-pairs-explained.md)
>* [Voraussetzungen für das Präfix für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)


<!-- Victor/Vlad: Do we still need this link? It doesn't look like this content has been migrated.
>* [AppMeasurement Flash, Flex, and OSMF Implementation Guide](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)
-->

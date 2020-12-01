---
description: In diesem Artikel werden die Präfixe beschrieben, die Sie beim Erstellen von Eigenschaftsregeln an Schlüsselvariablen anhängen müssen.
seo-description: In diesem Artikel werden die Präfixe beschrieben, die Sie beim Erstellen von Eigenschaftsregeln an Schlüsselvariablen anhängen müssen.
seo-title: Anforderungen an Präfixe für Schlüsselvariablen
solution: Audience Manager
title: Anforderungen an Präfixe für Schlüsselvariablen
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
translation-type: tm+mt
source-git-commit: 1c0d40082cd0753a9b4326aae764eb74aefb8be4
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 5%

---


# Anforderungen an Präfixe für Schlüsselvariablen {#prefix-requirements-for-key-variables}

In diesem Artikel werden die Präfixe beschrieben, die Sie beim Erstellen von Eigenschaftsregeln an Schlüsselvariablen anhängen müssen.

<!-- r_tb_variable_prefixes.xml -->

## Zweck der Präfixe für Schlüsselvariablen

Wenn Sie [!UICONTROL Trait Builder]-Regeln erstellen, ist es wichtig, der Schlüsselvariablen ein empfehlenswertes Präfix vorangestellt zu haben. Diese Präfixe identifizieren den Datentyp, der übergeben wird, und tragen dazu bei, Namensraum-Konflikte innerhalb von [!DNL Audience Manager] zu vermeiden. Im Allgemeinen können Sie einer Variablen einen beliebigen Namen geben, aber die Daten für eine Regel werden nicht verarbeitet, wenn der Name der Schlüsselvariablen nicht mit dem Variablennamen in einem Ereignis-Aufruf übereinstimmt.

## Präfixe für Schlüsselvariablen

Die folgende Tabelle definiert die allgemeinen Präfixe, die von [!UICONTROL Trait Builder] verwendet werden.

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Präfix der Schlüsselvariablen </th> 
   <th colname="col2" class="entry"> Identifiziert die Variable </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>Als kundenspezifisch. Dies sind wichtige Daten, die von Ihren eigenen Eigenschaften gesendet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>Auf der Ebene <span class="keyword"> Audience Manager</span>. Diese Daten sind im gesamten <span class="keyword">-Audience Manager</span>-Ökosystem einheitlich. Eine umfassendere Liste finden Sie unter <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Unterstützte Attribute für DCS API-Aufrufe</a>.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Das enthält <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP-Header</a>-Informationen. Umfasst Header-Parameter wie <code> referer</code>,<code> IP</code>, <code> accept-language</code> usw. </p> <p> <p>Hinweis: Bei Kunden, die DIL-Versionen verwenden, die älter als 9.0 sind, funktioniert die Datenerfassung mit dem <code> h_referer</code>-Signal nicht auf Safari-Browsern. Mit der Einführung von <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a> können Safari-Browser die Domäne demdex.net als Tracker klassifizieren und den Werber bei der Datenerfassungsanforderung abschneiden, sodass nur die Herkunft und nicht die vollständige URL enthalten ist. Die neueste DIL-Version finden Sie unter <a href="../../dil/dil-overview.md#get-implement-dil-code">DIL-Code abrufen und implementieren</a>.<p>Signale, die dieses Präfix verwenden, werden in <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Signalsuche</a> nicht angezeigt.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Unsere <span class="wintitle"> Datenerfassungsserver</span> ermöglichen die Übergabe privater Parameter. Grundsätzlich werden alle Parameter, die Beginn mit <code> p_</code> verwenden, zur Eigenschaftsbewertung verwendet, aber nicht nachgelagert oder gespeichert. </p> <p>Beispiel: bei <code> /event?p_age=23</code> und einer Eigenschaft wie <code> YoungPeople = p_age &lt; 25</code> wird die Eigenschaft realisiert, aber das <code> p_age=23</code> Schlüssel-Wert-Paar wird nach der Anforderung entfernt und nicht protokolliert. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Übersicht über grundlegende Informationen](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Verwalten von Eigenschaftsregeln](../../features/traits/manage-trait-rules.md#managing-trait-rules)


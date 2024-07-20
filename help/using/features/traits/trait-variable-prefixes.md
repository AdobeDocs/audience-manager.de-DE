---
description: In diesem Artikel werden die Präfixe beschrieben, die Sie beim Erstellen von Eigenschaftsregeln an Schlüsselvariablen anhängen müssen.
seo-description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-title: Prefix Requirements for Key Variables
solution: Audience Manager
title: Voraussetzungen für das Präfix für Schlüsselvariablen
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Voraussetzungen für das Präfix für Schlüsselvariablen {#prefix-requirements-for-key-variables}

In diesem Artikel werden die Präfixe beschrieben, die Sie beim Erstellen von Eigenschaftsregeln an Schlüsselvariablen anhängen müssen.

<!-- r_tb_variable_prefixes.xml -->

## Zweck der Schlüsselvariablenpräfixe

Wenn Sie [!UICONTROL Trait Builder] -Regeln erstellen, ist es wichtig, der Schlüsselvariablen ein empfohlenes Präfix voranzustellen. Diese Präfixe identifizieren den Datentyp, der übergeben wird, und helfen, Namespace-Konflikte innerhalb von [!DNL Audience Manager] zu vermeiden. Im Allgemeinen können Sie einer Variablen einen beliebigen Namen geben, aber die Daten für eine Regel werden nicht verarbeitet, wenn der Name der Schlüsselvariablen nicht mit dem Variablennamen in einem Ereignisaufruf übereinstimmt.

## Präfixe für Schlüsselvariablen

Die folgende Tabelle definiert die allgemeinen Präfixe, die von [!UICONTROL Trait Builder] verwendet werden.

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schlüsselvariablenpräfix </th> 
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
   <td colname="col2"> <p>Auf der Ebene <span class="keyword"> Audience Manager</span> . Diese Daten sind im gesamten Ökosystem <span class="keyword"> Audience Manager</span> einheitlich. Eine vollständigere Liste finden Sie unter <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Unterstützte Attribute für DCS-API-Aufrufe</a> .</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Enthält <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP-Header</a> -Informationen. Enthält Kopfzeilenparameter wie <code> referer</code>, <code> IP</code>, <code> accept-language</code> usw. </p> <p> <p>Hinweis: Bei Kunden, die DIL-Versionen verwenden, die älter als 9.0 sind, funktioniert die Datenerfassung mit dem <code> h_referer</code> -Signal nicht in Safari-Browsern. Mit der Einführung von <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a> können Safari-Browser die Domäne demdex.net als Tracker klassifizieren und den Referrer bei der Datenerfassungsanforderung so abschneiden, dass er nur den Ursprung anstelle der vollständigen URL enthält. Die neueste DIL-Version finden Sie unter <a href="../../dil/dil-overview.md#get-implement-dil-code">Abrufen und Implementieren von DIL-Code</a> .<p>Signale, die dieses Präfix verwenden, werden in der <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Signalsuche</a> nicht angezeigt.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Unsere <span class="wintitle"> Datenerfassungsserver</span> ermöglichen die Übergabe privater Parameter. Grundsätzlich werden Parameter, die mit <code> p_</code> beginnen, für die Eigenschaftsbewertung verwendet, aber nicht nachgelagert protokolliert und auch nicht gespeichert. </p> <p>Beispiel: Bei <code> /event?p_age=23</code> und einer Eigenschaft wie <code> YoungPeople = p_age &lt; 25</code> wird die Eigenschaft implementiert, aber das Schlüssel-Wert-Paar <code> p_age=23</code> wird nach der Anfrage abgelegt und nicht protokolliert. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Überblick über grundlegende Informationen](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Verwalten von Eigenschaftsregeln](../../features/traits/manage-trait-rules.md#managing-trait-rules)

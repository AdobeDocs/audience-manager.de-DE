---
description: In diesem Artikel werden die Präfixe beschrieben, die Sie bei der Erstellung von Eigenschaftsregeln an Schlüsselvariablen anhängen müssen.
seo-description: In diesem Artikel werden die Präfixe beschrieben, die Sie bei der Erstellung von Eigenschaftsregeln an Schlüsselvariablen anhängen müssen.
seo-title: Präfix für Schlüsselvariablen
solution: Audience Manager
title: Präfix für Schlüsselvariablen
uuid: df 2 ef 9 c 8-606 a -45 f 9-a 836-859 f 856 a 7 d 4 b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Präfix für Schlüsselvariablen {#prefix-requirements-for-key-variables}

In diesem Artikel werden die Präfixe beschrieben, die Sie bei der Erstellung von Eigenschaftsregeln an Schlüsselvariablen anhängen müssen.

<!-- r_tb_variable_prefixes.xml -->

## Zweck der Präfixe von Schlüsselvariablen

Beim Erstellen [!UICONTROL Trait Builder] von Regeln ist es wichtig, die Schlüsselvariable mit einem empfohlenen Präfix vorzustellen. Diese Präfixe identifizieren die Art der übergebenen Daten und helfen [!DNL Audience Manager]bei der Vermeidung von Namespace-Konflikten. Im Allgemeinen können Sie einer Variablen einen beliebigen Namen geben, aber die Daten für eine Regel werden nicht verarbeitet, wenn der Name der Schlüsselvariablen nicht dem Variablennamen in einem Ereignisaufruf entspricht.

## Präfixe für Schlüsselvariablen

In der folgenden Tabelle sind die häufig verwendeten Präfixe definiert [!UICONTROL Trait Builder].

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
   <td colname="col2"> <p>Als kundenspezifisch. Dies sind wichtige Daten, die aus Ihren eigenen Eigenschaften gesendet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>Auf Audience <span class="keyword"> Manager</span> -Ebene. Diese Daten sind im <span class="keyword"> gesamten Audience Manager</span> -System einheitlich. Eine vollständige Liste finden Sie unter <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Unterstützte Attribute für DCS-API-Aufrufe</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Dies enthält <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP-Header</a> -Informationen. Enthält Kopfzeilenparameter wie <code> Referrer</code>,<code> IP</code>, <code> accept-language</code>usw. </p> <p> <p>Hinweis: Für Kunden, die ältere DIL-Versionen als 9.0 verwenden, funktioniert die Datenerfassung mit <code> dem h_ referenzer</code> -Signal in Safari-Browsern nicht. Mit der Einführung von <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>können Safari-Browser die Domäne demdex. net als Tracker klassifizieren und den Referrer auf der Datenerfassungsanforderung kürzen, sodass er nur den Ursprung anstelle der vollständigen URL enthält. Siehe <a href="../../dil/dil-overview.md#get-implement-dil-code">Abrufen und Implementieren von DIL-Code</a> für die aktuelle DIL-Version. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Unsere <span class="wintitle"> Datenerfassungsserver</span> ermöglichen die Übergabe privater Parameter. Grundsätzlich wird jeder Parameter, der mit <code> p_</code> beginnt, für die Eigenschaftenauswertung verwendet, wird jedoch nicht nach unten protokolliert oder gespeichert. </p> <p>Beispiel: angegeben <code> ? p_ age = 23</code> und eine Eigenschaft wie <code> "youngpeople = p_ age &lt; 25</code>" wird realisiert, aber das <code> Schlüssel-Wert-Paar p_ age = 23</code> wird nach der Anforderung abgelegt und wird nicht protokolliert. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Grundlegende Informationsübersicht](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Verwalten von Trait-Regeln](../../features/traits/manage-trait-rules.md#managing-trait-rules)


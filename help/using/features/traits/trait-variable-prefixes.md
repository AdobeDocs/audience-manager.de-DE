---
description: In diesem Artikel werden die Präfixe beschrieben, die Sie beim Erstellen von Eigenschaftsregeln an Schlüsselvariablen anhängen müssen.
seo-description: In diesem Artikel werden die Präfixe beschrieben, die Sie beim Erstellen von Eigenschaftsregeln an Schlüsselvariablen anhängen müssen.
seo-title: Voraussetzungen für das Präfix für Schlüsselvariablen
solution: Audience Manager
title: Voraussetzungen für das Präfix für Schlüsselvariablen
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Voraussetzungen für das Präfix für Schlüsselvariablen {#prefix-requirements-for-key-variables}

In diesem Artikel werden die Präfixe beschrieben, die Sie beim Erstellen von Eigenschaftsregeln an Schlüsselvariablen anhängen müssen.

<!-- r_tb_variable_prefixes.xml -->

## Zweck der Präfixe für Schlüsselvariablen

Beim Erstellen von [!UICONTROL Trait Builder] Regeln ist es wichtig, der Schlüsselvariablen ein empfehlenswertes Präfix vorzustellen. Diese Präfixe identifizieren den Typ der weitergeleiteten Daten und helfen, Namespace-Konflikte innerhalb von [!DNL Audience Manager]zu vermeiden. Im Allgemeinen können Sie einer Variablen einen beliebigen Namen geben, aber die Daten für eine Regel werden nicht verarbeitet, wenn der Name der Schlüsselvariablen nicht mit dem Variablennamen in einem Ereignisaufruf übereinstimmt.

## Präfixe für Schlüsselvariablen

In der folgenden Tabelle sind die allgemeinen Präfixe definiert, die von [!UICONTROL Trait Builder]den

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
   <td colname="col2"> <p>Auf <span class="keyword"> Audience Manager</span> -Ebene. Diese Daten sind im gesamten <span class="keyword"> Audience Manager</span> -Ökosystem einheitlich. Eine vollständige Liste finden Sie unter <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Unterstützte Attribute für DCS API-Aufrufe</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Das enthält <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP-Header</a> -Informationen. Umfasst Header-Parameter wie <code> referer</code>,<code> IP</code><code> accept-language</code>usw. </p> <p> <p>Hinweis: Bei Kunden, die DIL-Versionen über 9.0 verwenden, funktioniert die Datenerfassung mit dem <code> h_referer</code> Signal nicht in Safari-Browsern. Mit der Einführung von <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>können Safari-Browser die Domäne demdex.net als Tracker klassifizieren und die verweisende Stelle in der Datenerfassungsanforderung abschneiden, sodass sie nur den Ursprung statt der vollständigen URL enthält. Die neueste DIL-Version finden Sie unter <a href="../../dil/dil-overview.md#get-implement-dil-code">Getting and Implementing DIL Code</a> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Unsere <span class="wintitle"> Datenerfassungsserver</span> ermöglichen die Übergabe privater Parameter. Grundsätzlich werden alle Parameter, die mit beginnen, zur Eigenschaftsbewertung verwendet, aber nicht nachgelagert oder gespeichert. <code> p_</code> </p> <p>Beispiel: angegeben <code> /event?p_age=23</code> und eine Eigenschaft wie <code> YoungPeople = p_age &lt; 25</code>, wird die Eigenschaft realisiert, aber das <code> p_age=23</code> Schlüssel-Wert-Paar wird nach der Anforderung entfernt und nicht protokolliert. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Übersicht über grundlegende Informationen](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Verwalten von Eigenschaftsregeln](../../features/traits/manage-trait-rules.md#managing-trait-rules)


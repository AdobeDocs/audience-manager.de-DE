---
description: Empfehlungen und Anwendungsfälle für Segment-Remotings und personalisierte Segmentqualifizierung mit dem Profillink-Gerätediagramm.
seo-description: Empfehlungen und Anwendungsfälle für Segment-Remotings und personalisierte Segmentqualifizierung mit dem Profillink-Gerätediagramm.
seo-title: Anwendungsfälle des Profillink-Gerätediagramms
solution: Audience Manager
title: Anwendungsfälle des Profillink-Gerätediagramms
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Anwendungsfälle des Profillink-Gerätediagramms {#profile-link-device-graph-use-cases}

Empfehlungen und Anwendungsfälle für Segment-Retargeting und personalisierte Segmentqualifizierung mit dem [!UICONTROL Profile Link] Gerätediagramm.

## Recommendations {#recommendations}

Betrachten Sie das [!UICONTROL Profile Link] Gerätediagramm für Kampagnen, die:

* Sie haben eine hochwertige Authentifizierung über ihre digitalen Eigenschaften hinweg. Verwenden Sie eine [externe Gerätediagrammoption](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) , wenn Sie nur über eine geringe Anzahl authentifizierter Benutzer verfügen.
* Genaues Targeting bekannter Zielgruppen erforderlich. Die [!UICONTROL Profile Link device graph] Daten werden mit authentifizierten Erstanbieterdaten erstellt.
* Targeting bekannter Zielgruppen über ihren authentifizierten und nicht authentifizierten Status in Echtzeit.

![](assets/merge-rule-triangle2.png)

## Konfiguration der Anwendungsfall- und Profilzusammenführungsregel wiederholen {#retargeting-use-cases}

Retargeting von Zielgruppen, die sich zuvor auf mehreren Geräten authentifiziert haben, und/oder in der App. Segmente können aus folgenden Profilen bestehen:

* Zuletzt bekanntes authentifiziertes Geräteprofil.
* Anonyme Aktivität für jedes Geräteprofil.

>[!NOTE]
>
>Eigenschafteninformationen aus beiden Profiltypen können zum Erstellen des Segments verwendet werden.

### Beispiel für Retargeting

Schauen wir uns einmal an, wie das bei einem Beispiel-Kreditkartenunternehmen funktioniert. In diesem Beispiel werden Eigenschaftsinformationen verwendet, die aus anonymer Aktivität gesammelt wurden und nur bei 3 Geräteprofilen angezeigt werden.

<table id="table_8C5ABA47A0634EBA9B1AA1B5C2AABF07"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nutzungsszenario </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Bedingungen</b> </p> </td> 
   <td colname="col2"> <p>Dieser Anwendungsfall geht von folgenden Bedingungen aus: </p> <p> 
     <ul id="ul_72373D0F304044AE84E4CC055E3E8154"> 
      <li id="li_375DA786ED4D4F18A74C8FE42ABF8448">Ein Benutzer verfügt über 3 Geräte und war die letzte Person, die sich auf allen 3 Geräten auf der Kreditkartenfirma-Site/der Kreditkartenanwendung authentifiziert hat. </li> 
      <li id="li_77FDBFAED21B4DE19AB2B6C112E0C64B">Auf dem ersten Gerät zeigt ein Benutzer in einem nicht authentifizierten Status ein Angebot für eine Premium-Kreditkarte an. </li> 
      <li id="li_D3BE1B30BCCA49EA931AA9D97DD5F86D">Auf dem zweiten Gerät zeigt ein Benutzer in einem nicht authentifizierten Status die Vorteilsseite der Premium-Kreditkarte an. </li> 
      <li id="li_39D894624FC44806B6DB2C77F459B39E">Auf dem dritten Gerät zeigt ein Benutzer in einem nicht authentifizierten Status die Seite mit den Gebühren und Gebühren für die Kreditkarte an. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p>Unter diesen Bedingungen <span class="keyword"> kann Audience Manager</span>: </p> <p> 
     <ul id="ul_1B6174F5C3AF4C32831D4217C5113789"> 
      <li id="li_98FE54696B604C3C8D93CC1C1FBB48D9">Führt die anonyme, nicht authentifizierte Aktivität zusammen, die von allen 3 Geräten mithilfe des letzten authentifizierten Profils auf dem aktuellen Gerät erfasst wurde. </li> 
      <li id="li_A73C7DCE36BA42B6BAD26D8A075416C1">Wertet den anonymen Benutzer für die Segmentqualifizierung auf Grundlage von: 
       <ul id="ul_EF66EAFD12CA44F5ACCB66319606D937"> 
        <li id="li_541762056ECF4BC1ABF1F5116B5FED6C">Eine Kombination aus anonymer Aktivität auf allen 3 Geräten. </li> 
        <li id="li_C386CB62E5234E10AFEDE900ADC0E261">Das letzte authentifizierte Profil auf dem aktuellen Gerät. </li> 
       </ul> </li> 
      <li id="li_5C9BDC8FF886494589F005C9658A923C">Sendet das Segment an ein beliebiges Echtzeit-Ziel zum Retargeting auf allen 3 Geräten. </li>
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiel für eine Retargeting Profile Merge Rule

Um ein Retargeting mit einzurichten, [!UICONTROL Profile Link]sollten Ihre [!UICONTROL Authenticated Options] und [!UICONTROL Device Options] die Regel wie folgt konfiguriert sein. Die [!UICONTROL Authenticated Profile] Optionen unterscheiden sich von diesem Beispiel, da diese Einstellungen die Namen Ihrer geräteübergreifenden Datenquellen verwenden.

![Einrichten der Regel zum Profilzusammenführen](assets/merge-rules-internal3.png)

## Konfiguration der Anwendungsfall- und Profilzusammenführungsregel für Personalisierung {#personalization-use-case}

Personalisieren Sie das Erlebnis für authentifizierte Zielgruppen auf der Site und/oder in der App basierend auf der Aktivität auf mehreren Geräten. Segmente können aus folgenden Profilen bestehen:

* Aktuell authentifiziertes Geräteprofil.
* Anonyme Geräteprofile.

>[!NOTE]
>
>Ein Benutzer muss sich in einem authentifizierten Zustand befinden, um sich für ein Segment qualifizieren zu können.

### Personalisierungsbeispiel

Schauen wir uns einmal an, wie das bei einem Beispiel-Kreditkartenunternehmen funktioniert.

<table id="table_D2F4D5D27EB54224BB2CC1D843DDEDA3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nutzungsszenario </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Bedingungen</b> </p> </td> 
   <td colname="col2"> <p>Unser Anwendungsfall geht von folgenden Bedingungen aus: </p> <p> 
     <ul id="ul_C4D2108E7B1C4D3C89411A9CCCDA6DAC"> 
      <li id="li_2F10EB17466B4B91A94DF707C3CB6BE5">Ein Benutzer verfügt über 3 Geräte und war die letzte Person, die sich auf allen 3 Geräten auf der Kreditkartenfirma-Site/der Kreditkartenanwendung authentifiziert hat. </li> 
      <li id="li_1559C4DA51254BCF95291133F32A4057">Auf dem ersten Gerät zeigt ein Benutzer in einem nicht authentifizierten Status ein Angebot für eine Premium-Kreditkarte an. </li> 
      <li id="li_734465E5619C474291C42921160CEC6B">Auf dem zweiten Gerät zeigt ein Benutzer in einem nicht authentifizierten Status die Vorteilsseite der Premium-Kreditkarte an. </li> 
      <li id="li_B96ABC0205384B59A1901708505B8BF8">Auf dem dritten Gerät zeigt ein Benutzer in einem nicht authentifizierten Status die Seite mit den Gebühren und Gebühren für die Kreditkarte an. </li> 
      <li id="li_1A7BDBD546BD4B8EACF4292D885127F2">Auf einem dieser Geräte authentifiziert sich der Kunde (durch Anmeldung), um seinen Kontostand zu überprüfen. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p>Unter diesen Bedingungen <span class="keyword"> kann Audience Manager</span>: </p> <p> 
     <ul id="ul_37DBF5FEABC5463D85C74AD9150EA177"> 
      <li id="li_B60FFA5CF3F64FB69997AA05595900D7">Führt die anonyme, nicht authentifizierte Aktivität zusammen, die von allen 3 Geräten mithilfe des aktuellen authentifizierten Profils erfasst wurde. Das authentifizierte Profil bietet auf jedem Gerät eine gemeinsame ID. </li> 
      <li id="li_AB9FD87DD804474BA33805C364B7B92D">Wertet den authentifizierten Benutzer für die Segmentqualifizierung auf Grundlage folgender Elemente aus: 
       <ul id="ul_EAF99E72159D4E329052B71344D9C69B"> 
        <li id="li_0B5E52BA6D8B493980291EA7B0AE235A">Eine Kombination aus anonymer Aktivität auf allen 3 Geräten. </li> 
        <li id="li_07588DEFBEF64F97850CB12CD62D0213">Ihr aktuelles authentifiziertes Profil. </li> 
       </ul> </li> 
      <li id="li_E7CFCEAD7610496189F4486000D7860A">Sendet das Segment an ein beliebiges Echtzeit-Ziel, um eine personalisierte Browsererfahrung für den Benutzer zu erstellen, während die Authentifizierung auf dem aktuellen Gerät erfolgt. <p>Hinweis:  Dadurch sind alle 3 Geräte für das Segment qualifiziert, unabhängig vom Authentifizierungsstatus. Dies kann zu Datenschutzproblemen führen, wenn es sich um freigegebene Geräte handelt. </p> </li>
     </ul> </p> </td>
  </tr>
 </tbody> 
</table>

### Beispiel für eine Regel zum Zusammenführen des Personalisierungsprofils

Um die Personalisierung mit [!UICONTROL Profile Link]zu konfigurieren, sollten Sie [!UICONTROL Authenticated Options] und [!UICONTROL Device Options] wie folgt aussehen: Die [!UICONTROL Authenticated Profile] Optionen unterscheiden sich von diesem Beispiel, da diese Einstellungen die Namen Ihrer geräteübergreifenden Datenquellen verwenden.

![](assets/merge-rules-internal4.png)

Weitere Informationen zur Funktionsweise dieser Gerätediagrammprozesse finden Sie im PDF-, [Audience Manager- und Externe Gerätediagramme](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_LIKE_THIS]
>
>* [Anwendungsbeispiele für Diagramme externer Geräte](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Häufig gestellte Fragen zu Regeln zur Profilzusammenführung](../../faq/faq-profile-merge.md)


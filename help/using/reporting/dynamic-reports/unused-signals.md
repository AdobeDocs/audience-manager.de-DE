---
description: Dieser Bericht gibt die Häufigkeit aller nicht verwendeten Informationen zurück, die im Bestand erfasst und an Audience Manager gesendet wurden.
seo-description: Dieser Bericht gibt die Häufigkeit aller nicht verwendeten Informationen zurück, die im Bestand erfasst und an Audience Manager gesendet wurden.
seo-title: Bericht zu nicht verwendeten Signalen
solution: Audience Manager
title: Bericht zu nicht verwendeten Signalen
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bericht zu nicht verwendeten Signalen{#unused-signals-report}

Dieser Bericht gibt die Häufigkeit aller nicht verwendeten Informationen zurück, die im Bestand erfasst und an Audience Manager gesendet wurden.

<!-- 

c_unused_signals.xml

 -->

## Bericht zu nicht verwendeten Signalen

Ein Signal ist eine Information von Ihrer Website, an die [!DNL Audience Manager] in Form von [Schlüssel-Wert-Paaren](../../reference/key-value-pairs-explained.md) (z.B. `color=blue, price>100, gender=female`usw.) weitergegeben wird.

Nicht verwendete Signale bestehen aus Daten, die Sie erfassen, aber keiner Eigenschaft zugeordnet wurden. Der [!UICONTROL Unused Signals] Bericht zeigt Daten in einer Tabelle nach Datum, Schlüssel, Wert und Häufigkeit an. Jedes nicht zugeordnete Signal, das [!DNL Audience Manager] mindestens 100 Mal an einem Tag weitergegeben wird, qualifiziert sich für den [!UICONTROL Unused Signals] Bericht.

Überprüfen Sie diesen Bericht, um verwaiste Signale zu identifizieren, die neuen oder vorhandenen Eigenschaften zugeordnet werden können.

>[!NOTE]
>
>Geben Sie einen Schlüssel- oder Wertnamen in die Suchfelder ein, um die Ergebnisse auf bestimmte Datensätze zu beschränken.

## Nutzungsszenarios

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispiele </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Sicherstellen der Einheitlichkeit von Eigenschaften oder Hinzufügen verwandter Werte zu einem Schlüssel</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht, um verschiedene Variationen von Werten für ein bestimmtes Signal zu berücksichtigen. </p> <p>Angenommen, Sie haben eine Eigenschaft für den Bundesstaat "North Carolina"in einem Schlüssel-Wert-Paar definiert als <code> c_state = North Carolina</code>. Der Bericht kann Ihnen helfen, Namensvarianten zu finden und diese zu den Eigenschaften hinzuzufügen (z.B. <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Alternativ dazu können Sie Namensvarianten mit dem Bericht ausfindig machen und diese durch einen einheitlichen Wert für alle Sites ersetzen. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Neue Eigenschaften erstellen</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht, um zu sehen, welche neuen Werte an einen bestimmten Schlüssel weitergegeben werden. Möglicherweise möchten Sie anhand dieser neuen Werte neue Schlüssel-Wert-Paare erstellen. </p> <p> <p>Hinweis:  Überprüfen Sie den Bericht zweimal wöchentlich auf Werte, die sich häufig ändern (z. B. Shows, Kampagnen, Prominente usw.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nicht zugeordnete Werte suchen</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht auf die Nummer 1. Die Zahl 1 in einem <span class="wintitle"> Bericht "Nicht verwendete Signale</span> "stellt einen Nullwert dar. Das ist nicht unbedingt schlecht. Das bedeutet einfach, dass ein bestimmter Schlüssel keine Wertzuordnung besitzt. Wenn Sie viele von 1 Werten für eine wichtige Variable sehen, wenden Sie sich an Ihr Site-Team, um sicherzustellen, dass alle Seiten korrekt getaggt sind. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best Practices

Führen Sie den [!UICONTROL Unused Signals] Bericht aus und überprüfen Sie ihn:

* Nachdem Sie eine Eigenschaftsregel erstellt oder aktualisiert haben. Auf diese Weise können Sie sicherstellen, dass Ihre Eigenschaften und Regeln ordnungsgemäß eingerichtet sind. Die Zahl 1 in den Ergebnissen zeigt an, dass eine neue Eigenschaft möglicherweise nicht richtig konfiguriert ist.
* Zweiwöchentlich oder monatlich. Geplante Überprüfungen stellen sicher, dass die Zuordnungen von Eigenschaften auf dem neuesten Stand sind.

>[!NOTE]
>
>Beachten Sie bei der Suche nach nicht verwendeten Werten im Bericht die folgende Besonderheit. Es gibt einen Unterschied zwischen den beiden folgenden Beispielen:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Beide Beispiele zeigen eine Eigenschaft, die zwei Schlüssel/Wert-Paare v und a enthält. Der erste Ausdruck setzt sich wie folgt zusammen: die Eigenschaft enthält Schlüssel v mit dem Wert 1 [!UICONTROL AND NOT] der Schlüssel a mit dem Wert 23. Der zweite Ausdruck enthält Schlüssel v mit dem Wert 1 [!UICONTROL AND] der Schlüssel a mit dem Wert [!UICONTROL NOT EQUAL] 23.
* In Anbetracht der beiden oben genannten Ausdrücke, nehmen wir an, dass Sie in der Suche nach den Werten, die an Schlüssel A weitergegeben werden, mit einem beliebigen Wert von nicht 23, Sie erhalten nur Ergebnisse im ersten Fall, weil die Werte für Schlüssel nicht gesendet AT ALL. [!UICONTROL Unused Signals Report] Im zweiten Fall wurden Werte gesendet, die sich von 23 unterscheiden, sodass Schlüssel a nicht verwendet wird.

## Erstellung von Massenmerkmalen

Wenden Sie sich an Ihren Partner Solutions-Kundenbetreuer, wenn Sie aufgrund der aus dem [!UICONTROL Unused Signals] Bericht gewonnenen Daten eine Vielzahl von Eigenschaften erstellen müssen.

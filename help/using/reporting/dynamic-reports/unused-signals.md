---
description: Dieser Bericht gibt eine Häufigkeitsanzahl aller nicht verwendeten Informationen zurück, die in Ihrem Bestand erfasst und an Audience Manager gesendet werden.
seo-description: Dieser Bericht gibt eine Häufigkeitsanzahl aller nicht verwendeten Informationen zurück, die in Ihrem Bestand erfasst und an Audience Manager gesendet werden.
seo-title: Bericht zu nicht verwendeten Signalen
solution: Audience Manager
title: Bericht zu nicht verwendeten Signalen
uuid: 04334 a 5 c -3 e 21-44 db-b 971-0 b 4457685 e 9 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bericht zu nicht verwendeten Signalen{#unused-signals-report}

Dieser Bericht gibt eine Häufigkeitsanzahl aller nicht verwendeten Informationen zurück, die in Ihrem Bestand erfasst und an Audience Manager gesendet werden.

<!-- 

c_unused_signals.xml

 -->

## Bericht zu nicht verwendeten Signalen

Ein Signal sind Informationen von Ihrer Website, die in [!DNL Audience Manager] Form [von Schlüsselwertpaaren (z.](../../reference/key-value-pairs-explained.md) B. `color=blue, price>100, gender=female`usw.) weitergegeben werden.

Nicht verwendete Signale bestehen aus Daten, die Sie erfassen, aber keiner Eigenschaft zugeordnet wurden. Der [!UICONTROL Unused Signals] Bericht zeigt Daten in einer Tabelle nach Datum, Schlüssel, Wert und Häufigkeit an. Alle nicht zugeordneten Signale, die an einem Tag [!DNL Audience Manager] an mindestens 100 Tagen übergeben wurden, qualifizieren sich für den [!UICONTROL Unused Signals] Bericht.

Lesen Sie diesen Bericht, um verwaiste Signale zu identifizieren, die neuen oder vorhandenen Eigenschaften zugeordnet werden können.

>[!NOTE]
>
>Geben Sie einen Schlüssel oder einen Wert in den Suchfeldern an, um die Ergebnisse auf bestimmte Datensätze zu beschränken.

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
   <td colname="col1"> <p><b>Sicherstellen der Eigenschaftsübereinstimmung oder Hinzufügen verwandter Werte zu einem einzelnen Schlüssel</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht, um verschiedene Wertvariationen für ein bestimmtes Signal zu berücksichtigen. </p> <p>Angenommen, Sie haben eine Eigenschaft für den Status "North Carolina" , der in einem Schlüssel-Wert-Paar als <code> c_ state = North Carolina definiert ist</code>. Der Bericht kann Ihnen helfen, Namenvarianten zu finden und diese zur Eigenschaft hinzuzufügen (z. B. <code> c_ state = North Carolina, NC, N.C., ncarolina</code>). Alternativ dazu könnten Sie Namenvarianten mit dem Bericht erstellen und diejenigen durch einen einheitlichen Wert auf allen Sites ersetzen. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Neue Eigenschaften erstellen</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht, um zu sehen, welche neuen Werte an einen bestimmten Schlüssel weitergegeben werden. Sie können basierend auf diesen neuen Werten neue Schlüssel-Wert-Paare erstellen. </p> <p> <p>Hinweis: Überprüfen Sie den Bericht wöchentlich für Werte, die sich häufig ändern (z. B. Sendungen, Kampagnen, Celebrities usw.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nicht zugeordnete Werte suchen</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht für die Nummer 1. Die Zahl 1 in einem <span class="wintitle"> nicht verwendeten</span> Signaturbericht stellt einen Nullwert dar. Dies ist nicht unbedingt negativ. Dies bedeutet lediglich, dass ein bestimmter Schlüssel keine zugeordnete Wertzuordnung hat. Wenn Sie eine Vielzahl von Werten für eine wichtige Variable sehen, wenden Sie sich an Ihr Siteteam, um sicherzustellen, dass alle Ihre Seiten richtig getaggt sind. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best Practices

Führen Sie den [!UICONTROL Unused Signals] Bericht aus und prüfen Sie ihn:

* Nachdem Sie eine Eigenschaft erstellt oder Trait-Regeln aktualisiert haben. Dadurch wird sichergestellt, dass Ihre Eigenschaften und Regeln korrekt eingerichtet werden. Die Zahl 1 in den Ergebnissen bedeutet, dass eine neue Eigenschaft möglicherweise nicht richtig konfiguriert wird.
* Viertelwöchentlich oder monatlich. Geplante Überprüfungen helfen sicherzustellen, dass Eigenschaftszuordnungen aktuell sind.

>[!NOTE]
>
>Beachten Sie bei der Suche nach nicht verwendeten Werten im Bericht die folgende Besonderheit. Es gibt einen Unterschied zwischen den beiden folgenden Beispielen:

* T (v = 1 [!UICONTROL AND NOT] (a = 23))
* T (v = 1 [!UICONTROL AND] (a!=23))
* Beide Beispiele zeigen eine Eigenschaft, die zwei Schlüssel-Wert-Paare v und a enthält. Der erste Ausdruck wird in: die Eigenschaft enthält den Schlüssel v mit dem Wert 1 [!UICONTROL AND NOT] der Schlüssel a mit dem Wert 23. Der zweite Ausdruck enthält Schlüssel v mit dem Wert 1 [!UICONTROL AND] der Schlüssel a mit dem Wert [!UICONTROL NOT EQUAL] 23.
* Nehmen wir an, Sie suchen in den beiden obigen Ausdrücken nach den Werten, die [!UICONTROL Unused Signals Report] mit einem anderen Wert als 23 weitergereicht werden. Sie erhalten nur Ergebnisse im ersten Fall, da Werte für den Schlüssel NICHT ALLE gesendet wurden. Im zweiten Fall wurden Werte, die von 23 abweichen, gesendet, sodass Schlüssel A nicht nicht verwendet wird.

## Massenseiteerstellung

Wenden Sie sich an Ihren Partner-Kundenbetreuer, wenn Sie viele Eigenschaften basierend auf Daten erstellen müssen, die aus dem [!UICONTROL Unused Signals] Bericht bezogen wurden.

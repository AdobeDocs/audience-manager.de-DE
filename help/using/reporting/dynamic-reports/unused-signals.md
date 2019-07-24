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


# Unused Signals Report{#unused-signals-report}

Dieser Bericht gibt eine Häufigkeitsanzahl aller nicht verwendeten Informationen zurück, die in Ihrem Bestand erfasst und an Audience Manager gesendet werden.

<!-- 

c_unused_signals.xml

 -->

## Bericht zu nicht verwendeten Signalen

A signal is information from your website passed in to [!DNL Audience Manager] in the form of [key-value pairs](../../reference/key-value-pairs-explained.md) (e.g., `color=blue, price>100, gender=female`, etc.).

Nicht verwendete Signale bestehen aus Daten, die Sie erfassen, aber keiner Eigenschaft zugeordnet wurden. The [!UICONTROL Unused Signals] report shows data in a table by date, key, value, and frequency count. Any unmapped signal passed in to [!DNL Audience Manager] at least 100 times in a day qualifies for the [!UICONTROL Unused Signals] report.

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
   <td colname="col2"> <p>Überprüfen Sie den Bericht, um verschiedene Wertvariationen für ein bestimmtes Signal zu berücksichtigen. </p> <p>For example, say you have a trait for the state "North Carolina" defined in a key-value pair as <code> c_state = North Carolina</code>. The report can help you find name variants and add those to the trait (e.g., <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Alternativ dazu könnten Sie Namenvarianten mit dem Bericht erstellen und diejenigen durch einen einheitlichen Wert auf allen Sites ersetzen. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Neue Eigenschaften erstellen</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht, um zu sehen, welche neuen Werte an einen bestimmten Schlüssel weitergegeben werden. Sie können basierend auf diesen neuen Werten neue Schlüssel-Wert-Paare erstellen. </p> <p> <p>Hinweis: Überprüfen Sie den Bericht wöchentlich für Werte, die sich häufig ändern (z. B. Sendungen, Kampagnen, Celebrities usw.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nicht zugeordnete Werte suchen</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht für die Nummer 1. The number 1 in an <span class="wintitle"> Unused Signals</span> report represents a null value. Dies ist nicht unbedingt negativ. Dies bedeutet lediglich, dass ein bestimmter Schlüssel keine zugeordnete Wertzuordnung hat. Wenn Sie eine Vielzahl von Werten für eine wichtige Variable sehen, wenden Sie sich an Ihr Siteteam, um sicherzustellen, dass alle Ihre Seiten richtig getaggt sind. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best Practices

Run and check the [!UICONTROL Unused Signals] report:

* Nachdem Sie eine Eigenschaft erstellt oder Trait-Regeln aktualisiert haben. Dadurch wird sichergestellt, dass Ihre Eigenschaften und Regeln korrekt eingerichtet werden. Die Zahl 1 in den Ergebnissen bedeutet, dass eine neue Eigenschaft möglicherweise nicht richtig konfiguriert wird.
* Viertelwöchentlich oder monatlich. Geplante Überprüfungen helfen sicherzustellen, dass Eigenschaftszuordnungen aktuell sind.

>[!NOTE]
>
>Beachten Sie bei der Suche nach nicht verwendeten Werten im Bericht die folgende Besonderheit. Es gibt einen Unterschied zwischen den beiden folgenden Beispielen:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Both examples show a trait which contains two key-value pairs v and a. The first expression translates into: the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23. The second expression contains key v with the value 1 [!UICONTROL AND] the key a with the value [!UICONTROL NOT EQUAL] 23.
* Considering the two different expressions above, let's say you search in the [!UICONTROL Unused Signals Report] for the values that get passed on key a with any value different than 23, you'll only obtain results in the first case because values for key were not sent AT ALL. Im zweiten Fall wurden Werte, die von 23 abweichen, gesendet, sodass Schlüssel A nicht nicht verwendet wird.

## Massenseiteerstellung

Contact your Partner Solutions representative if you need to bulk create a lot of traits based on data obtained from the [!UICONTROL Unused Signals] report.

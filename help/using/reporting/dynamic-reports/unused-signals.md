---
description: Dieser Bericht gibt eine Häufigkeitszählung aller nicht verwendeten Informationen zurück, die in Ihrem Inventar erfasst und an den Audience Manager gesendet wurden.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: Bericht zu nicht verwendeten Signalen
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 8fd148df6c19a5d8331faf66c671f91686954a77
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 2%

---

# Bericht zu nicht verwendeten Signalen{#unused-signals-report}

Dieser Bericht gibt eine Häufigkeitszählung aller nicht verwendeten Informationen zurück, die in Ihrem Inventar erfasst und an den Audience Manager gesendet wurden. Um auf diesen Bericht zuzugreifen, navigieren Sie zu **Analytics > Zielgruppenberichte > Andere Berichte > Nicht verwendete Signale**.

>[!NOTE]
>
>Wenn die Meldung &quot;Sie haben keinen Zugriff auf Zielgruppenberichte&quot;angezeigt wird, wenden Sie sich an Ihren Audience Manager-Berater oder die Kundenunterstützung, um den Bericht für Sie bereitzustellen.

![Screenshot des Berichts über nicht verwendete Signale](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Überblick

Ein Signal ist eine Information von Ihrer Website, die an [!DNL Audience Manager] in Form von [Schlüssel-Wert-Paaren](../../reference/key-value-pairs-explained.md) übergeben wird (z. B. `color=blue, price>100, gender=female` usw.).

Nicht verwendete Signale bestehen aus Daten, die Sie erfassen, aber keiner Eigenschaft zugeordnet sind. Der Bericht [!UICONTROL Unused Signals] zeigt Daten in einer Tabelle nach Datum, Schlüssel, Wert und Häufigkeitsanzahl an. Jedes nicht zugeordnete Signal, das mindestens 100 Mal an einem Tag an [!DNL Audience Manager] weitergegeben wird, gilt für den Bericht [!UICONTROL Unused Signals]. Nicht verwendete Signale werden 45 Tage lang gespeichert und dann verworfen.

Lesen Sie diesen Bericht, um verwaiste Signale zu identifizieren, die neuen oder vorhandenen Eigenschaften zugeordnet werden können.

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
   <td colname="col1"> <p><b>Sicherstellen der Einheitlichkeit von Eigenschaften oder Hinzufügen verwandter Werte zu einem einzelnen Schlüssel</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht, um verschiedene Wertvarianten für ein bestimmtes Signal zu berücksichtigen. </p> <p>Angenommen, Sie haben eine Eigenschaft für den Status "North Carolina", der in einem Schlüssel-Wert-Paar als <code> c_state = North Carolina</code> definiert ist. Der Bericht kann Ihnen dabei helfen, Namensvarianten zu finden und diese zur Eigenschaft hinzuzufügen (z. B. <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Alternativ können Sie Namensvarianten mit dem Bericht erkennen und durch einen einheitlichen Wert für alle Sites ersetzen. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Neue Eigenschaften erstellen</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht, um zu sehen, welche neuen Werte an einen bestimmten Schlüssel übergeben werden. Möglicherweise möchten Sie neue Schlüssel-Wert-Paare erstellen, die auf diesen neuen Werten basieren. </p> <p> <p>Hinweis:  Überprüfen Sie den Bericht alle zwei Wochen auf häufig wechselnde Werte (z. B. Shows, Kampagnen, Prominente usw.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nicht zugeordnete Werte suchen</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht auf die Nummer 1. Die Zahl 1 in einem Bericht <span class="wintitle"> Nicht verwendete Signale</span> stellt einen Nullwert dar. Das ist nicht unbedingt schlecht. Dies bedeutet einfach, dass einem bestimmten Schlüssel keine Wertzuordnung zugeordnet ist. Wenn Sie viele 1 Werte für eine wichtige Variable sehen, wenden Sie sich an Ihr Site-Team, um sicherzustellen, dass alle Ihre Seiten korrekt getaggt sind. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best Practices

Führen Sie den Bericht [!UICONTROL Unused Signals] aus und überprüfen Sie ihn:

* Nachdem Sie eine Eigenschaft erstellt oder Eigenschaftsregeln aktualisiert haben. Dadurch können Sie sicherstellen, dass Ihre Eigenschaften und Regeln ordnungsgemäß eingerichtet sind. Die Zahl 1 in den Ergebnissen zeigt an, dass eine neue Eigenschaft möglicherweise nicht richtig konfiguriert ist.
* Zwei Wochen oder monatlich. Geplante Überprüfungen helfen dabei, sicherzustellen, dass Eigenschaftszuordnungen auf dem neuesten Stand sind.

>[!NOTE]
>
>Beachten Sie bei der Suche nach nicht verwendeten Werten im Bericht die folgende Besonderheit. Es gibt einen Unterschied in der Ausdrücke zwischen den beiden folgenden Beispielen:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Beide Beispiele zeigen eine Eigenschaft, die zwei Schlüssel-Wert-Paare v und a enthält. Der erste Ausdruck übersetzt sich in: die Eigenschaft enthält Schlüssel v mit dem Wert 1 [!UICONTROL AND NOT] den Schlüssel a mit dem Wert 23. Der zweite Ausdruck enthält Schlüssel v mit dem Wert 1 [!UICONTROL AND] den Schlüssel a mit dem Wert [!UICONTROL NOT EQUAL] 23.
* Angenommen, Sie suchen im [!UICONTROL Unused Signals Report] nach den Werten, die an den Schlüssel A mit einem anderen Wert als 23 übergeben werden, in Bezug auf die beiden oben genannten Ausdrücke nur im ersten Fall Ergebnisse, da die Werte für den Schlüssel NICHT AN ALL gesendet wurden. Im zweiten Fall wurden Werte gesendet, die sich von 23 unterscheiden, sodass der Schlüssel a nicht verwendet wird.

## Erstellung von Masseneigenschaften

Wenden Sie sich an Ihren Partner Solutions-Support-Mitarbeiter, wenn Sie eine große Anzahl von Eigenschaften basierend auf Daten aus dem [!UICONTROL Unused Signals] -Bericht erstellen müssen.

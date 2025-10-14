---
description: Dieser Bericht gibt eine Häufigkeitsanzahl aller nicht verwendeten Informationen zurück, die in Ihrem Inventar erfasst und an Audience Manager gesendet wurden.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: Bericht zu nicht verwendeten Signalen
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 9c980b8fd5c3cb6ba7b3031726da726ee5caeec6
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---

# Bericht zu nicht verwendeten Signalen{#unused-signals-report}

Dieser Bericht gibt eine Häufigkeitsanzahl aller nicht verwendeten Informationen zurück, die in Ihrem Inventar erfasst und an Audience Manager gesendet wurden. Um auf diesen Bericht zuzugreifen, navigieren Sie zu **Analytics > Zielgruppenberichte > Andere Berichte > Nicht verwendete Signale**.

>[!NOTE]
>
>Wenn die Meldung „Sie haben keinen Zugriff auf Zielgruppenberichte“ angezeigt wird, wenden Sie sich an Ihren Audience Manager-Berater oder die Kundenunterstützung, um den Bericht für Sie bereitzustellen.

![Screenshot des Berichts über nicht verwendete Signale](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Überblick

Ein Signal ist eine Information von Ihrer Website, die in Form von [!DNL Audience Manager]Schlüssel-Wert-Paaren[&#x200B; (z. B. &#x200B;](../../reference/key-value-pairs-explained.md) usw.) an `color=blue, price>100, gender=female` weitergegeben wird.

Nicht verwendete Signale bestehen aus Daten, die Sie sammeln, aber keiner Eigenschaft zugeordnet wurden. Der [!UICONTROL Unused Signals] Bericht zeigt Daten in einer Tabelle nach Datum, Schlüssel, Wert und Häufigkeitsanzahl an. Jedes nicht zugeordnete Signal, das an [!DNL Audience Manager] mindestens 100-mal pro Tag übergeben wird, ist für den [!UICONTROL Unused Signals]-Bericht qualifiziert.

Ungenutzte Signale werden 45 Tage lang aufbewahrt und dann verworfen. Der Bericht für nicht verwendete Signale zeigt Daten aus den letzten 10 Tagen an.

Dieser Bericht hilft bei der Identifizierung verwaister Signale, die neuen oder vorhandenen Eigenschaften zugeordnet werden können.

>[!NOTE]
>
>Geben Sie in den Suchfeldern einen Schlüssel- oder Wertnamen an, um die Ergebnisse auf bestimmte Datensätze zu beschränken.

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
   <td colname="col1"> <p><b>Einheitlichkeit der Eigenschaft sicherstellen oder einem Schlüssel verwandte Werte hinzufügen</b> </p> </td> 
   <td colname="col2"> <p>Prüfen Sie den Bericht, um verschiedene Wertevariationen für ein bestimmtes Signal zu berücksichtigen. </p> <p>Angenommen, Sie haben eine Eigenschaft für den Bundesstaat „North Carolina“, definiert in einem Schlüssel-Wert-Paar als <code> c_state = North Carolina</code>. Der Bericht kann Ihnen dabei helfen, Namensvarianten zu finden und diese zum Merkmal hinzuzufügen (z. B. <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Alternativ können Sie Namensvarianten mit dem Bericht erkennen und diese durch einen einheitlichen Wert für alle Sites ersetzen. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Erstellen neuer Eigenschaften</b> </p> </td> 
   <td colname="col2"> <p>Überprüfen Sie den Bericht, um zu sehen, welche neuen Werte für einen bestimmten Schlüssel übergeben werden. Sie können neue Schlüssel-Wert-Paare erstellen, die auf diesen neuen Werten basieren. </p> <p> <p>Hinweis: Überprüfen Sie den Bericht alle zwei Wochen auf Werte, die sich häufig ändern (z. B. Shows, Kampagnen, Prominente usw.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nicht zugeordnete Werte suchen</b> </p> </td> 
   <td colname="col2"> <p>Prüfen Sie den Bericht auf Nummer 1. Die Zahl 1 in einem Bericht zu <span class="wintitle"> nicht verwendeten </span> stellt einen Nullwert dar. Das ist nicht unbedingt schlecht. Das bedeutet einfach, dass einem bestimmten Schlüssel keine Wertzuordnung zugeordnet ist. Wenn viele 1-Werte für eine wichtige Variable angezeigt werden, wenden Sie sich an Ihr Site-Team, um sicherzustellen, dass alle Ihre Seiten korrekt mit Tags versehen sind. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best Practices

Führen Sie den [!UICONTROL Unused Signals] aus und überprüfen Sie ihn:

* Nachdem Sie eine Eigenschaft erstellt oder Eigenschaftsregeln aktualisiert haben. Dadurch wird sichergestellt, dass Ihre Eigenschaften und Regeln ordnungsgemäß eingerichtet sind. Die Zahl 1 in den Ergebnissen zeigt an, dass eine neue Eigenschaft möglicherweise nicht korrekt konfiguriert ist.
* Zweimal wöchentlich oder monatlich. Geplante Überprüfungen stellen sicher, dass die Eigenschaftszuordnungen auf dem neuesten Stand sind.

>[!NOTE]
>
>Beachten Sie bei der Suche nach nicht verwendeten Werten im Bericht die folgende Besonderheit. Zwischen den beiden folgenden Beispielen besteht ein Unterschied im Ausdruck:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23)
* Beide Beispiele zeigen ein Merkmal, das zwei Schlüssel-Wert-Paare v und a enthält. Der erste Ausdruck ergibt: Das Merkmal enthält Schlüssel v mit dem Wert 1 [!UICONTROL AND NOT] Schlüssel a mit dem Wert 23. Der zweite Ausdruck enthält Schlüssel v mit dem Wert 1 [!UICONTROL AND] Schlüssel a mit dem Wert [!UICONTROL NOT EQUAL] 23.
* In Anbetracht der beiden oben genannten verschiedenen Ausdrücke sagen wir, Sie suchen im [!UICONTROL Unused Signals Report] nach den Werten, die an Schlüssel a mit einem anderen Wert als 23 übergeben werden, Sie erhalten Ergebnisse nur im ersten Fall, da Werte für Schlüssel ÜBERHAUPT nicht gesendet wurden. Im zweiten Fall wurden andere Werte als 23 gesendet, sodass der Schlüssel a nicht ungenutzt bleibt.

## Erstellung einer Masseneigenschaft

Wenden Sie sich an Ihren Partner Solutions-Support-Mitarbeiter, wenn Sie aufgrund der aus dem [!UICONTROL Unused Signals]-Bericht gewonnenen Daten eine Vielzahl von Eigenschaften erstellen müssen.

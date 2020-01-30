---
description: Diese Seite enthält die wichtigsten Probleme, die der Kundenunterstützung von Audience Manager gemeldet wurden.
seo-description: Diese Seite enthält die wichtigsten Probleme, die der Kundenunterstützung von Audience Manager gemeldet wurden.
seo-title: Kundenunterstützung - Am häufigsten gemeldete Probleme
solution: Audience Manager
title: Kundenunterstützung - Am häufigsten gemeldete Probleme
translation-type: tm+mt
source-git-commit: f9d57da86b7e8962353b01b693a2359cade7b024

---


# Kundenunterstützung - Am häufigsten gemeldete Probleme{#most-frequent-issues}

Diese Seite enthält die wichtigsten Probleme, die der Kundenunterstützung von Audience Manager im Jahr 2019 gemeldet wurden.

## Warum können unsere schreibgeschützten Benutzer Eigenschaften und Segmente erstellen, bearbeiten oder löschen?

**Frage**

Warum können unsere schreibgeschützten Benutzer Eigenschaften und Segmente erstellen, bearbeiten oder löschen?

**Antwort**

Zusätzlich zum Erstellen von Gruppen und Berechtigungen im Abschnitt &quot;Administration&quot;müssen Sie sich an den Kundendienst (amsupport@adobe.com) wenden, damit ein Vertreter die RBAC-Steuerung (Role Based Access Controls) für Ihr Konto aktivieren kann.

<br> 

## Warum sind meine Trait-Populationen mit Onboarded um den 15. Oktober auf 0 gesunken? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

Etwa am 14. Oktober 2019 bemerkte ich, dass die Populationen für die integrierten Eigenschaften des Geräte-ID-Diagramms auf 0 gesunken sind, wo sie früher viel höher waren.

![Ablegen der Geräte-ID](/help/using/support-issues/assets/device_id_populationdrop.png)

**Antwort**

Am 15. Oktober wurde eine Aktualisierung der Profilzusammenführungsregel-Funktion von Audience Manager dahingehend geändert, dass Onboarded-Daten, die von einer CRM-ID, die auf eine geräteübergreifende Datenquelle hochgeladen wurde, herausgegeben wurden, nicht mehr für Geräte-IDs implementiert werden.  Zuvor wurde Audience Manager sowohl für die geräteübergreifende ID (oder CRM-ID) als auch für das Kopieren dieser Realisierungen in die entsprechenden UUIDs (Geräte-IDs) von Audience Manager erkannt.  Die Änderung wurde vorgenommen, um die Art der Eigenschaftsdaten und die zu realisierenden Profile genauer widerzuspiegeln.

Um die Eigenschaften anzuzeigen, wählen Sie bitte die Option &quot;Geräteübergreifende ID&quot;aus der Dropdown-Liste oben rechts in der Ansicht &quot;Eigenschaften&quot;.

![Realisierungen nach geräteübergreifender ID anzeigen](/help/using/support-issues/assets/deviceid-crossdevice.png)

<br> 

## Warum werden meine Eigenschaften oder Segmente nicht auf der Seite Überschneidungsberichte angezeigt?

Erläuterung, warum Eigenschaften und Segmente möglicherweise nicht auf der Seite Überschneidungsberichte angezeigt werden.

**Frage**

Warum sehen Benutzer beim Versuch, einen Überschneidungsbericht auszuführen, nicht bestimmte Eigenschaften und Segmente, die auf der Seite &quot;Überschneidungsberichte&quot;aufgeführt sind?

**Antwort**

Damit eine Eigenschaft oder ein Segment in den Überschneidungsberichten aufgeführt wird, muss eine Mindestanforderung an individuelle Besucher erfüllt werden.


* Eigenschaften: 28000 über einen Zeitraum von 14 Tagen
* Für Segmente: 70000 Echtzeit-Benutzer über einen Zeitraum von 14 Tagen

Weitere Informationen dazu finden Sie in den Berichten[zu ausgewählten Audience Manager- ](/help/using/reporting/report-sampling.md)Daten unter Datenbearbeitung und Fehlerquoten.
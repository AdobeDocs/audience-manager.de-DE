---
description: Häufige Fragen und Probleme im Zusammenhang mit der Zielgruppenbestimmung.
seo-description: Common targeting-related questions and issues.
seo-title: Targeting FAQ
solution: Audience Manager
title: Häufig gestellte Fragen zur Zielgruppenbestimmung
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
feature: Match Rates
exl-id: e5f761fd-dfc8-4859-a81e-89abbd7f2914
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 100%

---

# Häufig gestellte Fragen zur Zielgruppenbestimmung{#targeting-faq}

Häufige Fragen und Probleme im Zusammenhang mit der Zielgruppenbestimmung.

<br>

<!-- 

faq_targeting.xml

 -->

**Wo finde ich eine vollständige Liste von Datendrittanbietern, die von Audience Manager unterstützt werden?**

Im [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html) finden Sie eine vollständige Liste der Datendrittanbieter, die von [!DNL Audience Manager] unterstützt werden.

<br>

**Sollte ich Daten von Drittanbietern in Audience Manager oder in einer DSP verwenden, um Benutzer mit Daten von Drittanbietern anzusprechen, die ich noch nie auf meiner Website gesehen habe?**

Die Antwort hängt von Ihren Zielen ab. Wenn Ihre Kampagne z. B. darauf ausgelegt ist, neue Kunden mit Daten von Drittanbietern zu finden, arbeiten Sie direkt mit einer DSP zusammen. Denken Sie daran, dass Audience Manager Daten nur dann mit einem Drittanbieter synchronisiert, wenn wir diesen Benutzer sehen. Wenn wir einen Benutzer noch nie gesehen haben, wird unser System keine Informationen für diesen Site-Besucher haben. Erstellen Sie für Kampagnen, die nur Daten von Drittanbietern verwenden möchten, um Benutzer anzusprechen, die noch nie eine Ihrer Eigenschaften besucht haben, diese Segmente über die DSP.

<br>

**Kann ich an Einzelanwender vermarkten?**

Mit Audience Manager können Sie Benutzer anhand von gemeinsamen Attributen oder Eigenschaften aggregieren und an sie vermarkten. Zur Einhaltung der Branchenvorschriften dürfen [!DNL Audience Manager]-Kunden jedoch keine personenbezogenen Daten (PII) an unsere Systeme senden. Daher können Sie keine E-Mail-Adressen, Namen, physischen Adressen usw. für die Zielgruppenbestimmung verwenden.

<br>

**Wie bewahre ich Daten zur erneuten Zielgruppenbestimmung sicher auf?**

Es wird empfohlen, eine Server-zu-Server-Verbindung zu verwenden, um Daten mit Ihrer bevorzugten Retargeting-Plattform auszutauschen. Audience Manager tauscht Daten mit den meisten wichtigen DSPs über Server-zu-Server-Verbindungen aus. Durch Server-zu-Server-Datenübertragungen wird verhindert, dass andere Akteure Ihre Daten abfangen und diese Zielgruppendaten weiterverkaufen.

<br>

**Ist die eindeutige Benutzer-ID (Unique User ID, UUID) von Audience Manager an die eindeutige Benutzer-ID eines Adservers gebunden, indem die ID direkt auf der Seite synchronisiert wird?**

Nein. Auf der Seite werden keine ID-Synchronisierungen für On-site-Publisher oder Server vorgenommen. Die Audience Manager-UUID wird in das `u=`-Feld der Adserver-Protokolldateien eingefügt. Dies geschieht, wenn das Segment für die Zielgruppenbestimmung übergeben wird. Diese Funktion wird vom DIL-Code-Modul ausgeführt. Dies ist derselbe Mechanismus, mit dem wir die Benutzer-ID des Servers für die Berichte zur Segmentleistung einem Audience Manager-Benutzer zuordnen können. Wenn jedoch ein Adserver auf der Site vorhanden ist, werden IDs direkt auf der Seite synchronisiert.

<br>

**Zählt Audience Manager Benutzer, die sich von verschiedenen Geräten aus anmelden, als einen Unique User oder als verschiedene Unique Users?**

[Deklariertes ID-Targeting](../features/declared-ids.md#declared-id-targeting) hilft Audience Manager bei der Identifizierung eines Besuchers auf mehreren Geräten mit einer einzigen eindeutigen ID. Aus Sicht der Zielgruppenbestimmung oder des Ziels sind dies jedoch immer noch 2 (oder mehr) Benutzer, da DSPs diese mehreren IDs nicht miteinander in Einklang bringen können.

<br>

**Kann Audience Manager Benutzer anhand von Display- und Mobilgeräten identifizieren?**

Ja. Siehe [Deklariertes ID-Targeting](../features/declared-ids.md#declared-id-targeting).

<br>

**Kann ich Benutzer mit online erfassten Daten bewerten und sie anhand dieses Modellwerts erneut ansprechen?**

Ja. Audience Manager kann Datendateien bereitstellen, mit denen Sie Benutzer bewerten können. Sie müssen jedoch mit anderen Anbietern oder Software zusammenarbeiten, um diese Informationen zu analysieren und zu bewerten. Senden Sie diese Daten in Form von Schlüssel-Wert-Paaren an Audience Manager. Wir können diese Informationen an bestehende Profile anhängen. Wenden Sie sich an Ihren Partner Solutions-Support-Mitarbeiter, um diesen Prozess zu überprüfen.

<br>

**Wie hoch sind die Löschraten von Cookies in einem bestimmten Zeitraum von 1 bis 2 Monaten?**

Das Löschen von Cookies ist schwer zu messen. Die meisten Cookies werden von einigen Besuchern gelöscht, die häufig Cookies löschen. Die meisten Browser-Cookies sind jedoch für mindestens 30 Tage stabil, auch wenn einige von ihnen möglicherweise eine begrenzte Lebensdauer haben. Einige Studien legen nahe, dass ein Targeting des oberen Trichters, das länger als 30 Tage dauert, 7 % der Browser-Zielgruppe über einen Zeitraum von 30 Tagen effektiv eliminieren würde. Wie Sie wissen, sind 30-tägige Kampagnen für eine bestimmte Werbemittelbotschaft in der Branche Standard. Nach dem, was wir gesehen haben, ist diese Abnahme um 7 % korrekt.

Das Löschen von Cookies hat negative Auswirkungen auf die Berechnung von Reichweite und Häufigkeit. Daher betonen wir den Wert von Verhaltensdaten, wenn wir versuchen, die wahre Natur von Verbraucher-Trends bei der Planung von Display-Kampagnen zu verstehen. Unsere Kunden können in Audience Manager Berichte über Segmentüberlagerungen, über die optimale Impressionshäufigkeit und Trends bei Unique Users über bestimmte Datumsbereiche nutzen, um die Kampagnenplanung und die optimalen Datumsbereiche für laufende Kampagnen wissenschaftlicher zu gestalten.

<br>

**Welches Gültigkeitsfenster haben Audience Manager-Cookies?**

In der Benutzeroberfläche können Sie das Gültigkeitsintervall für Cookies festlegen. Sie können Cookies so einstellen, dass sie nach *n* Tagen oder nie ablaufen.

<br>

**Kostet uns die Implementierung eines Kampagnenwerbemittels in einem Ereignisaufruf mehr?**

Das kommt darauf an. Die Kosten basieren auf Unique Users. Wenn eine Kampagne zu neuen Nutzern führt, kostet dies mehr. Wenn Ihre Kampagne Orte erreicht, an denen wir bereits Daten sammeln, dann gibt es keine zusätzlichen Kosten. Wenn Ihre Kampagne auf verwandten Sites mit erheblichen Überlagerungen ausgeführt wird, entstehen zusätzliche Kosten für die neuen Unique Users, die wir sehen.

<br>

**Audience Manager zeigt nur [!UICONTROL Addressable Audiences]-Metriken und Übereinstimmungsraten für [!UICONTROL Server-to-Server]-Ziele an. Können Sie erklären, warum wir diese Zahlen nicht für Cookie- und URL-Ziele sehen?**

Es finden ID-Synchronisierungen statt. Bei [!UICONTROL Server-to-Server]-Zielen übertragen wir die Daten offline (entweder in Echtzeit oder im Batch-Modus), und wir müssen die ID senden, die der Zielpartner versteht, damit er sie dem Browser wieder zuordnen kann. Die adressierbare Segmentzahl ist eine Teilmenge der gesamten Segmentpopulation.

Bei Cookie- und URL-Zielen befindet sich der Benutzer bereits im Browser, und [!DNL Audience Manager] sendet nur die Segmente, für die der Benutzer sich qualifiziert hat. Der Zielpartner kann die Segmentzuordnungen einfach abrufen und mit diesen Informationen arbeiten. Beachten Sie daher, dass die Übereinstimmungsraten für Cookie- und URL-Ziele immer 100 % betragen.

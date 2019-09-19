---
description: Häufige Fragen und Probleme im Zusammenhang mit Targeting.
seo-description: Häufige Fragen und Probleme im Zusammenhang mit Targeting.
seo-title: Häufig gestellte Fragen zum Targeting
solution: Audience Manager
title: Häufig gestellte Fragen zum Targeting
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Häufig gestellte Fragen zum Targeting{#targeting-faq}

Häufige Fragen und Probleme im Zusammenhang mit Targeting.

<br> 

<!-- 

faq_targeting.xml

 -->

**Wo finde ich eine vollständige Liste der Drittanbieter für Daten, die von Audience Manager unterstützt werden?**

Eine vollständige Liste der von Drittanbietern unterstützten Datenanbieter finden Sie im [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) [!DNL Audience Manager] .

<br> 

**Sollte ich Daten von Drittanbietern in Audience Manager oder einem DSP verwenden, um Benutzer, die ich noch nie mit Daten von Drittanbietern auf meiner Site gesehen habe, als Ziel anzusehen?**

Die Antwort hängt von deinen Zielen ab. Wenn Ihre Kampagne zum Beispiel darauf ausgelegt ist, neue Kunden mit Daten von Drittanbietern zu finden, arbeiten Sie direkt mit einem DSP zusammen. Denken Sie daran, dass Audience Manager Daten nur dann mit einem Drittanbieter synchronisiert, wenn dieser Benutzer angezeigt wird. Wenn wir noch nie einen Benutzer gesehen haben, verfügt unser System nicht über Informationen für diesen Besucher. Für Kampagnen, die nur Daten von Drittanbietern für das Targeting von Benutzern verwenden möchten, die noch keine Ihrer Eigenschaften besucht haben, erstellen Sie diese Segmente über das DSP.

<br> 

**Kann ich für Einzelpersonen vermarkten?**

Mit Audience Manager können Sie Benutzer zusammenfassen und basierend auf gemeinsamen Attributen oder Eigenschaften auf sie vermarkten. Zur Einhaltung der Branchenvorschriften dürfen [!DNL Audience Manager] Kunden jedoch keine personenbezogenen Daten (PII) an unsere Systeme senden. Daher können Sie keine E-Mail-Adressen, Namen, physischen Adressen usw. verwenden. für Targeting.

<br> 

**Wie kann ich das Targeting von Daten sicher gestalten?**

Es wird empfohlen, eine Server-zu-Server-Verbindung zum Datenaustausch mit Ihrer bevorzugten Targeting-Plattform zu verwenden. Audience Manager tauscht Daten mit den meisten der wichtigsten DSPs über Server-zu-Server-Verbindungen aus. Die Übertragung von Server-zu-Server-Daten verhindert, dass andere Akteure Ihre Daten abfangen und diese Zielgruppendaten erneut verkaufen.

<br> 

**Ist die eindeutige Benutzer-ID (UUID) von Audience Manager durch ID-Synchronisierung direkt auf der Seite an die eindeutige Benutzer-ID eines Anzeigenservers gebunden?**

Nein. ID-Synchronisierungen werden für lokale Herausgeber oder Server nicht auf der Seite vorgenommen. Die Audience Manager-UUID wird in das `u=` Feld der Protokolldateien des Anzeigenservers eingefügt. Dies geschieht, wenn das Segment für das Targeting weitergegeben wird. Diese Funktion wird vom DIL-Codemodul ausgeführt. Dies ist der gleiche Mechanismus, mit dem wir die Benutzer-ID des Servers einem Audience Manager-Benutzer für die Segmentleistungsberichterstellung zuordnen können. Wenn jedoch ein Anzeigenserver auf der Site vorhanden ist, werden IDs direkt auf der Seite synchronisiert.

<br> 

**Zählt Audience Manager Benutzer, die sich von verschiedenen Geräten aus anmelden, als ein Unique User oder als verschiedene Unique Users?**

[Deklariertes ID-Targeting](../features/declared-ids.md#declared-id-targeting) hilft Audience Manager bei der Identifizierung eines Besuchers auf mehreren Geräten mit einer einzigen eindeutigen Kennung. Aus der Targeting- oder Zielperspektive betrachtet sind dies jedoch immer noch 2 (oder mehr) Benutzer, da DSPs diese mehreren IDs nicht miteinander in Einklang bringen können.

<br> 

**Kann Audience Manager einen Benutzer anhand von Anzeige- und Mobilgeräten identifizieren.**

Ja. Siehe [Deklariertes ID-Targeting](../features/declared-ids.md#declared-id-targeting).

<br> 

**Kann ich Benutzer mit online erfassten Daten bewerten und sie anhand dieses Modellwerts neu ausrichten?**

Ja. Audience Manager kann Datendateien bereitstellen, mit denen Sie Benutzer bewerten können. Sie müssen jedoch mit anderen Anbietern oder Software zusammenarbeiten, um diese Informationen zu analysieren und zu bewerten. Senden Sie diese Daten in Form von Schlüssel/Wert-Paaren an Audience Manager. Wir können diese Informationen nehmen und an bestehende Benutzerprofile anhängen. Wenden Sie sich an Ihren Partner Solutions-Kundenbetreuer, um diesen Prozess zu überprüfen.

<br> 

**Wie hoch sind die Löschraten von Cookies in einem bestimmten Zeitraum von 1 bis 2 Monaten?**

Das Löschen von Cookies ist schwer zu messen. Die meisten Cookies werden von einigen wenigen Besuchern gelöscht, die häufig Cookies löschen. Die meisten Browser-Cookies sind jedoch für mindestens 30 Tage stabil, auch wenn einige von ihnen eine begrenzte Lebensdauer haben. Einige Studien deuten darauf hin, dass das Targeting von oberen Trichter, das länger als 30 Tage ist, effektiv 7 % der Zielgruppe im Browser über einen Zeitraum von 30 Tagen eliminiert. Wie Sie wissen, sind 30-Tage-Kampagnen für eine bestimmte kreative Botschaft in der Branche Standard. Nach dem, was wir gesehen haben, ist diese 7%-ige Abnahme korrekt.

Das Löschen von Cookies hat negative Auswirkungen auf die Reichweiten- und Frequenzberechnungen. Daher betonen wir den Wert von Verhaltensdaten, wenn wir versuchen, die wahre Natur von Verbrauchertrends für die Anzeigenkampagnenplanung zu verstehen. Unsere Kunden können Audience Manager-Berichte zur Segmentüberschneidung, optimale Impressionshäufigkeitsberichte und eindeutige Benutzertrends über bestimmte Datumsbereiche hinweg nutzen, um die Kampagnenplanung und optimale Datumsbereiche für die Ausführung von Kampagnen wissenschaftlicher zu gestalten.

<br> 

**Welches Ablauffenster haben Audience Manager-Cookies?**

In der Benutzeroberfläche können Sie das Ablaufintervall für Cookies festlegen. Sie können Cookies so einstellen, dass sie nach *n* Tagen ablaufen oder nie.

<br> 

**Kostet uns die Implementierung eines kreativen Kampagnenkreises in einem Ereignisaufruf mehr?**

Es kommt darauf an. Die Kosten basieren auf Unique Users. Wenn eine Kampagne netto neue Benutzer ergibt, dann ja, das kostet mehr. Wenn Ihre Kampagne Orte erreicht, an denen wir bereits Daten erfassen, dann entstehen keine zusätzlichen Kosten. Wenn Ihre Kampagne auf verwandten Sites läuft, auf denen erhebliche Überschneidungen bestehen, entstehen zusätzliche Kosten für die neuen Unique Users, die wir sehen.

<br> 

**Audience Manager zeigt nur[!UICONTROL Addressable Audiences]Metriken und Übereinstimmungsraten für[!UICONTROL Server-to-Server]Ziele an. Können Sie erklären, warum wir diese Zahlen für Cookie- und URL-Ziele nicht sehen?**

Es führt zu ID-Synchronisierungen. Bei [!UICONTROL Server-to-Server] Zielen werden Daten offline übertragen (entweder in Echtzeit oder im Stapel), und wir müssen die ID senden, die der Zielpartner versteht, damit er sie wieder dem Browser zuordnen kann. Die adressierbare Segmentanzahl ist eine Untergruppe der Segmentpopulation insgesamt.

Bei Cookie- und URL-Zielen befindet sich der Benutzer bereits im Browser, und es werden nur die Segmente gesendet, für die der Benutzer sich qualifiziert hat. [!DNL Audience Manager] Der Zielpartner kann die Segmentzuordnungen einfach abrufen und mit diesen Informationen arbeiten. Beachten Sie daher, dass die Übereinstimmungsraten für Cookie- und URL-Ziele immer 100% betragen.

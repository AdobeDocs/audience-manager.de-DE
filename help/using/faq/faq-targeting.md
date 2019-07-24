---
description: Häufig verwendete Fragen und Probleme.
seo-description: Häufig verwendete Fragen und Probleme.
seo-title: Häufig gestellte Fragen zum Targeting
solution: Audience Manager
title: Häufig gestellte Fragen zum Targeting
uuid: ee 96 ef 71-b 903-4953-afc 4-8 ec 8 e 48 bd 49 e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Targeting FAQ{#targeting-faq}

Häufig verwendete Fragen und Probleme.

<br> 

<!-- 

faq_targeting.xml

 -->

**Wo finde ich eine vollständige Liste von Drittanbietern von Drittanbietern, die von Audience Manager unterstützt werden?**

See the [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) for a complete list of third-party data providers that [!DNL Audience Manager] supports.

<br> 

**Um Benutzer als Ziel auszuwählen, die ich auf meiner Site nicht mit Daten von Drittanbietern gesehen habe, sollte ich Daten von Drittanbietern in Audience Manager oder in einem DSP verwenden?**

Die Antwort hängt von Ihren Zielen ab. Wenn Ihre Kampagne beispielsweise so konzipiert ist, dass neue Kunden mit Daten von Drittanbietern gefunden werden, arbeiten Sie direkt mit einer DSP. Denken Sie daran, dass der Audience Manager Daten nur mit einem Drittanbieter-Datenprovider synchronisiert, wenn wir diesen Benutzer sehen. Wenn wir noch nie einen Benutzer gesehen haben, verfügt unser System über keine Informationen für diesen Site-Besucher. Für Kampagnen, die nur Daten von Drittanbietern verwenden möchten, um Benutzer als Ziel auszuwählen, die nie Ihre Eigenschaften besucht haben, erstellen Sie diese Segmente über die DSP.

<br> 

**Kann ich für Einzelpersonen ein Marketing durchführen?**

Mit Audience Manager können Sie Benutzer aggregieren und auf Grundlage freigegebener Attribute oder Eigenschaften für sie freigeben. However, to comply with industry regulations, [!DNL Audience Manager] customers may not send personally identifiable information (PII) to our systems. Daher können Sie keine E-Mail-Adressen, einzelne Namen, physische Adressen usw. verwenden. für Targeting.

<br> 

**Wie kann ich die Retargeting-Daten sicher sicherstellen?**

Es wird empfohlen, eine Server-zu-Server-Verbindung zu verwenden, um Daten mit Ihrer bevorzugten Retargeting-Plattform auszutauschen. Audience Manager tauscht Daten mit den meisten der Haupt-dsps über Server-zu-Server-Verbindungen aus. Server-zu-Server-Datenübertragungen helfen anderen Anbietern, Ihre Daten zu unterfangen und diese Zielgruppeninformationen erneut zu verkaufen.

<br> 

**Ist die eindeutige Benutzer-ID (UUID) des Audience Manager mit der eindeutigen Benutzer-ID eines Werbeservers verknüpft, indem die ID direkt auf der Seite synchronisiert wird?**

Nein. ID-Synchronisierungen werden auf der Seite nicht für Herausgeber oder Server auf der Seite vorgenommen. The Audience Manager UUID is inserted into the `u=` field of the ad server log files. Dies geschieht, wenn das Segment für das Targeting weitergegeben wird. Diese Funktion wird vom DIL-Code-Modul ausgeführt. Dies ist derselbe Mechanismus, mit dem wir die Benutzer-ID des Servers einem Audience Manager-Benutzer für die Berichterstellung zur Segmentleistung zuordnen können. Wenn jedoch auf der Site ein Anzeigen-Server vorhanden ist, synchronisieren wir IDs direkt auf der Seite.

<br> 

**Zählt Audience Manager einen Benutzer, der sich von verschiedenen Geräten als Unique User oder Unique Users anmeldet?**

[Deklariertes ID-Targeting](../features/declared-ids.md#declared-id-targeting) hilft Audience Manager, einen Besucher über mehrere Geräte mit einer einzigen eindeutigen Kennung zu identifizieren. Aus Targeting- oder Zielperspektive sind dies jedoch noch 2 (oder mehr) Benutzer, da dsps diese mehreren IDs nicht anpassen können.

<br> 

**Kann einen Benutzer von der Anzeige und Mobilgeräten aus identifizieren.**

Ja. See [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting).

<br> 

**Kann ich Benutzer mit online erfassten Daten bewerten und sie basierend auf diesem Modellergebnis retargeting?**

Ja. Audience Manager kann Datendateien bereitstellen, die Ihnen bei der Bewertung von Benutzern helfen. Sie müssen jedoch mit anderen Anbietern oder Software zusammenarbeiten, um diese Informationen zu analysieren und zu ordnen. Senden Sie diese Daten in Form von Schlüssel/Wert-Paaren an Audience Manager. Wir können diese Informationen nehmen und an vorhandene Benutzerprofile anhängen. Wenden Sie sich an Ihren Partner-Lösungsvertreter, um diesen Vorgang zu lesen.

<br> 

**Welches sind die Cookie-Löschen-Raten über einen gegebenen Zeitraum von 1 bis 2 Monaten?**

Das Löschen von Cookies ist schwer zu messen. Die meisten Löschen von Cookies stammen aus wenigen Besuchern, die Cookies häufig löschen. Die meisten Browser-Cookies sind jedoch für mindestens 30 Tage stabil, auch wenn einige der Browser nur ein begrenztes Leben aufweisen. Einige Studien empfehlen das obere Trichtertargeting, das größer als 30 Tage ist und 7% der Browser-Zielzielgruppe über einen Zeitraum von 30 Tagen effektiv eliminiert würde. Wie Sie wissen, sind 30 Tage für eine bestimmte Kreative Botschaft in der Branche Standard. Aus dem, was wir gesehen haben, ist diese 7%-Dropdownliste genau.

Das Löschen von Cookies wirkt sich negativ auf Reichweiten- und Frequenzberechnungen aus. Daher unterstreichen wir den Wert von Verhaltensdaten, wenn wir versuchen, die wahre Art der Kundentrends für die Anzeige der Kampagnenplanung zu verstehen. Unsere Kunden können Audience Manager-Segmentüberlappberichte, optimale Impressionsberichte und individuelle Benutzertrends über bestimmte Datumsbereiche hinweg nutzen, um mehr über die Kampagnenplanung und optimale Datumsbereiche für laufende Kampagnen zu erfahren.

<br> 

**Was ist das Ablauffenster für Audience Manager-Cookies?**

Über die Benutzeroberfläche können Sie das Ablaufintervall für die Cookies bestimmen. You can set cookies to expire after *n* number of days or never.

<br> 

**Führt die Implementierung eines kreativen Kampagnennamens in einem Ereignisaufruf mehr für uns?**

Dies hängt davon ab. Die Kosten basieren auf Unique Users. Wenn eine Kampagne Netto-neue Benutzer ergibt und dann ja, kostet dies mehr. Wenn Ihre Kampagne Positionen erreicht, an denen bereits Daten gesammelt werden, entstehen keine zusätzlichen Kosten. Wenn Ihre Kampagne auf verwandten Sites ausgeführt wird, auf denen sich erhebliche Überlappungen befinden, entstehen Mehrkosten für die neuen Unique Users, die wir sehen.

<br> 

**Audience Manager zeigt[!UICONTROL Addressable Audiences]Metriken und Übereinstimmungsraten nur für[!UICONTROL Server-to-Server]Ziele an. Can you explain why we don't see these figures for Cookie and URL destinations?**

Er wird auf ID-Synchronisierungen heruntergefahren. For [!UICONTROL Server-to-Server] destinations, we transfer data offline (either real-time or batch) and we need to send the ID that the destination partner understands, so they can map it back to the browser. Die segment addressable number ist eine Untergruppe der Gesamtanzahl der Segmente.

In the case of Cookie and URL destinations, the user is already on the browser, and what [!DNL Audience Manager] sends is just the segments that the user qualified for. Der Zielpartner kann die Segmentzuordnungen einfach abrufen und mit diesen Informationen arbeiten. Berücksichtigen Sie daher die Übereinstimmungsraten für Cookie- und URL-Ziele immer 100%.

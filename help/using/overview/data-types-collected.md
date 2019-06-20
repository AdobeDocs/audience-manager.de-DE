---
description: Mit Audience Manager können Sie Daten von Erstanbietern, Drittanbietern und Drittanbietern sammeln und verwalten.
seo-description: Mit Audience Manager können Sie Daten von Erstanbietern, Drittanbietern und Drittanbietern sammeln und verwalten.
seo-title: Datenerfassung
solution: Audience Manager
title: Datenerfassung
uuid: a 2 ddf 470-32 e 6-41 ec-a 1 d 7-a 6232 ef 084 b 9
translation-type: tm+mt
source-git-commit: f87a6f6c79a01c23608e4f5be24d017894e1c541

---


# Datenerfassung{#types-of-data-collected}

Mit Audience Manager können Sie Daten von Erstanbietern, Drittanbietern und Drittanbietern sammeln und verwalten.

Das Entsperren von Kundeninformationselementen, die in mehreren Silos gespeichert sind, stellt eine der größten Datenherausforderungen dar, die Unternehmen heute bewältigen. Von CRM-Datenbanken, von Registrierungssystemen, von Anzeigenservern usw. benötigen Unternehmen Tools, die wertvolle Daten zentralisieren und Kunden/Zielgruppen als ein strategisches Datenelement verwalten. Mit Audience Manager können Sie isolierte Kundeninformationen entsperren und die Datenerfassung aus mehreren Quellen verwalten. Erfasste Daten können basierend auf den Zeit-to-Live-Werten (TTL) des Datenelements verwaltet werden, wodurch der Herausgeber die Ablaufdaten aller Quellen kontrollieren kann. Audience Manager hilft Ihnen bei der Verwaltung der folgenden Datentypen:

| Datentyp | Wo Daten aus |
|---|---|
| **Erstanbieter** | Bekannte. Daten werden online gesammelt (von Kundeninteraktionen auf Ihren Websites) oder offline. |
| **Zweitanbieter** | Strategische Partner und Werbetreibende. |
| **Drittanbieter** | Datenanbieter und/oder Umtausch. Daten können Informationen wie Priorität, Demografie, Social/Lifestyle, psychografik und mehr enthalten. |

## Erstanbieter-Datenerfassung {#first-party-data}

Die Datenerfassung von Erstanbietern ist eine Hauptfunktion des Audience Manager. Diese Kernkompetenz berücksichtigt die Anforderungen unserer Kunden (Herausgeber oder Werbetreibende), die proprietäre Daten als Grundlage ihrer Marketingprogramme oder für das Targeting und die Modellierung mit anderen Datenquellen verwenden möchten.

<!-- 

c_1st_party_data.xml

 -->

Audience Manager arbeitet mit Kunden zusammen, um ihre Datenstrategie zu verstehen und diese Strategie dann einem benutzerdefinierten Datenerfassungsplan zuzuordnen. Unser Team für Partnerlösungen arbeitet mit Ihnen zusammen, um Sites, Rohdatensignale und andere Benutzerinteraktionen auf Ihren Websites zu bewerten. Mit diesen Informationen können Sie eine angepasste Datenerfassungsstrategie erstellen, die Datensignale auf Benutzerebene auf verschiedenen Seiten Ihres Bestands erfasst. Erfasste Daten werden gespeichert und einer vordefinierten Taxonomie zugeordnet, die jederzeit aktualisiert werden kann, da sich Ihr Unternehmen ändert.

Das folgende Beispiel zeigt, wie potenzielle Datenelemente von einer Musterseite erfasst werden können.

![](assets/1st_party_800px.png)

Nachdem die Rohdaten erfasst wurden, wird sie den kundendefinierten Eigenschaften innerhalb der Audience Manager-Plattform zugeordnet. Sowohl die Taxonomie als auch die Datenzuordnungen können jederzeit angepasst werden, ohne dass der Datenerfassungscode geändert wird.

## Datenerfassung von Drittanbietern {#second-party-data}

Daten von Drittanbietern stammen aus einem strategischen Geschäftspartner (der keine Daten verlag). Diese Informationen werden genau wie Erstanbieter-Daten erfasst und verwaltet.

<!-- 

c_2nd_party_data.xml

 -->

Bei einem zweiten Datenszenario senden Advertiser ihre eigenen Daten an Herausgeber, damit diese Informationen mit den Daten des Herausgebers kombinieren und dann ein gezielteres Werbeprogramm ausführen können. Darüber hinaus können Herausgeber ihren Zielgruppenpool erweitern, indem sie mit ihren Werbetreibenden zusammenarbeiten. In den meisten Fällen beinhalten diese Regeln vertragliche Beziehungen, die darauf beschränkt sind, das Audience Manager-Container-Tag auf der Partner-Site zu platzieren, um die Datenerfassung und Freigabe zu erleichtern.

Ein Beispiel für die Erfassung und das Remarketing von Drittanbietern könnte dazu führen, dass Automobilhersteller Daten auf ihren Autokonfigurationsseiten erfassen und diese Informationen dann mit wichtigen Partnern teilen. In diesem Fall könnte der Automobilhersteller verschiedene Anzeigen auf einer Audience Manager-Partnersite für Verbraucher bereitstellen, die verschiedene Arten von Fahrzeugoptionen konfiguriert haben (z. B. Farbe, Modell usw.).

![](assets/2nd_party_700px.png)

## Datenerfassung von Drittanbietern {#third-party-data}

Drittanbieterdaten sind Informationen, die von Anbietern außerhalb von Audience Manager erfasst und freigegeben werden.

<!-- 

c_3rd_party_data.xml

 -->

Drittanbieterdaten können verwendet werden, um vorhandene Datensegmente zu qualifizieren (z. B. Alter, Haushaltseinkommen usw.), Daten bereitzustellen, die zwar gefragt, aber nicht anderweitig verfügbar sind oder in Lookalike-Modellierung für eine bekannte Benutzerbasis von Erstanbieter- und Drittanbieterdaten verwendet werden. Audience Manager arbeitet mit Drittanbietern von Daten zusammen und hilft Ihnen dabei, den Datentyp zu verstehen, den diese Datenanbieter erfassen, damit Sie die richtigen strategischen Angebote für jeden Anbieter vornehmen können.

>[!NOTE]
>
>Eine vollständige Liste der von Drittanbietern unterstützten Drittanbieter-Datenanbieter [!DNL Audience Manager]finden Sie in [der Adobe Audience Finder](https://www.adobe-audience-finder.com/).

Audience Manager wird basierend auf den verfügbaren apis und Datensätzen mit anderen Datenanbietern integriert. Die Datenerfassung funktioniert in Echtzeit, wenn ein Benutzer Ihre Site durchsucht oder über Out-of-Band-Methoden, bei denen IDs zwischen Partnern synchronisiert werden und die Daten zwischen Servern übertragen werden, nachdem ein Benutzer Ihre Site verlassen hat. In beiden Fällen nutzen Audience Manager-Clients die Vorteile von Drittanbieterdaten, die auf unserer Plattform synchronisiert werden, was bedeutet, dass jeder Client oder jede Domäne keine eigene Synchronisierung durchführen muss. Auf diese Weise können Sie die Reichweite erhöhen und Serveraufrufe auf der Seite reduzieren.

## Übereinstimmungspartner {#match-partners}

Viele Kunden können mit Drittanbieter-Datenübereinstimmungspartnern arbeiten. Diese Entitäten verfügen über Beziehungen zu Sites, die über Registrierungsanforderungen verfügen und Kundendatendateien verarbeiten können, indem sie sie (in Echtzeit) basierend auf ihrem Registrierungsnetzwerk anpassen.

![](assets/data_provider_match_700px.png)


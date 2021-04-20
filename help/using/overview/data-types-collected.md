---
description: Mit Audience Manager können Sie Erstanbieter-, Zweitanbieter- und Drittanbieterdaten erfassen und verwalten.
seo-description: Mit Audience Manager können Sie Erstanbieter-, Zweitanbieter- und Drittanbieterdaten erfassen und verwalten.
seo-title: Erfasste Datentypen
solution: Audience Manager
title: Erfasste Datentypen
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: Overview
exl-id: cfb587da-ceac-425f-8334-e961eba6fad2
translation-type: tm+mt
source-git-commit: 15e36d2847627b5e5ccef11f8073ce5124f14815
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 72%

---

# Erfasste Datentypen {#types-of-data-collected}

[!DNL Audience Manager]Mit können Sie Erstanbieter-, Zweitanbieter- und Drittanbieterdaten erfassen und verwalten.

Die Nutzung von in mehreren Silos gespeicherten Kundendatenelementen ist eine der größten Datenherausforderungen, mit denen Unternehmen heute konfrontiert sind. Von Datenbanken über Registrierungssysteme bis zu Anzeigenservern usw. benötigen Firmen Tools, mit denen Sie wertvolle Daten zentralisieren und Daten zu Kunden und Audiencen als strategisches Datenelement verwalten können. [!DNL CRM] [!DNL Audience Manager]Mit können Sie isolierte Kundeninformationen nutzen und die Datenerfassung aus mehreren Quellen verwalten. Die erfassten Daten können auf der Grundlage der Werte für die Zeit bis zum Live-Betrieb des Datenelements ([!DNL TTL]) verwaltet werden, wodurch der Herausgeber den Ablauf von Daten über alle Quellen hinweg steuern kann. [!DNL Audience Manager] unterstützt Sie bei der Verwaltung der folgenden Datentypen:

| Datentyp | Datenquelle |
|---|---|
| **Erstanbieter** | Kunden. Daten werden online (aus Interaktionen der Verbraucher auf Ihren Websites) oder offline erfasst. |
| **Zweitanbieter** | Strategische Partner und Advertiser. |
| **Drittanbieter** | Datenanbieter und/oder Datenaustausch. Zu den Daten können Informationen wie Absichten, Demographie, Sozial-/Lebensstil, Psychographie und mehr gehören. |

## Erstanbieterdatenerfassung {#first-party-data}

Die Datenerfassung durch Erstanbieter ist eine Hauptfunktion von [!DNL Audience Manager]. Diese Kernkompetenz richtet sich an die Bedürfnisse unserer Kunden (Publisher und Advertiser), die proprietäre Daten als Eckpfeiler ihrer Marketing-Programme oder für Targeting und Modellierung mit anderen Datenquellen verwenden möchten.

[!DNL Audience Manager] arbeitet mit Kunden zusammen, um deren Datenstrategie zu verstehen und diese Strategie dann einem benutzerdefinierten Datenerfassungsplan zuzuordnen. Unser Partner Solutions-Team arbeitet mit Ihnen zusammen, um Sites, Rohdatensignale und andere Benutzerinteraktionen auf Ihren Websites auszuwerten. Mit diesen Informationen helfen wir Ihnen bei der Erstellung einer maßgeschneiderten Datenerfassungsstrategie, die Datensignale auf Benutzerebene von verschiedenen Seiten in Ihrem Bestand erfasst. Erfasste Daten werden gespeichert und einer vordefinierten Taxonomie zugeordnet, die jederzeit aktualisiert werden kann, wenn sich die Anforderungen Ihres Unternehmen ändern.

Das folgende Beispiel zeigt, wie potenzielle Datenelemente von einer Beispieleinkaufsseite erfasst werden können.

![Warenkorbdaten](assets/shopping-cart-data.png)

| Element | Beschreibung |
|---|---|
| 1 | **Geschlecht**. Der Vorname eines Käufers gibt normalerweise das Geschlecht an. In unserem Beispiel ist der Vorname des Käufers Mary, also wissen wir, dass der Käufer eine Frau ist. Namen werden nie von Audience Manager gespeichert. |
| 2 | **Interessen**. Die Artikel im Warenkorb können auf verschiedene Interessen hinweisen. In unserem Beispiel gibt Mary viel für Fitnessgeräte aus. |
| 3 | **Wohnungstyp**. Je nach Lieferadresse und/oder Rechnungsadresse können Sie entscheiden, ob Mary Fitnessgeräte für sich selbst oder für eine Firma kauft. |
| 4 | **Standort**. [!DNL ZIP] -Codes sind zuverlässiger als  [!DNL IP] Adressen, wenn es darum geht, einen Ort zu bestimmen. |
| 5 | **Promotionsaffinität**. Wenn ein Käufer Werbe-Codes oder Geschenkkarten verwendet, ist er wahrscheinlich ein Schnäppchenjäger, der nach den besten Angeboten sucht. |
| 6 | **Kaufkraft**. Preisdaten, die mit [!DNL ZIP+4]-Codes korrelieren, geben die Ausgabenstärke eines bestimmten Ortes an. |

Nachdem die Rohdaten erfasst wurden, werden sie den benutzerdefinierten Eigenschaften innerhalb der [!DNL Audience Manager]-Plattform zugeordnet. Sowohl die Taxonomie als auch die Datenzuordnung können jederzeit angepasst werden, ohne dass Änderungen am Datenerfassungs-Code vorgenommen werden.

## Zweitanbieterdatenerfassung {#second-party-data}

Zweitanbieterdaten stammen von einem strategischen Unternehmenspartner (es handelt sich nicht um Publisher-Daten). Diese Informationen werden wie Erstanbieterdaten erfasst und verwaltet.

In einem Zweitanbieterdatenszenario senden Advertiser ihre eigenen Daten-Assets an Publisher, damit diese die Informationen mit den Daten des Publishers kombinieren und dann ein gezielteres Werbeprogramm ausführen können. Darüber hinaus können Publisher ihre Zielgruppen-Pools durch eine Partnerschaft mit ihren Advertisern erweitern. In den meisten Fällen schließen diese Vereinbarungen vertragliche Beziehungen ein, die darauf beschränken, das [!DNL Audience Manager]-Container-Tag auf die Partnersite zu setzen, um die Datenerfassung und -freigabe zu erleichtern.

Ein Beispiel für die Erfassung und das Remarketing von Zweitanbieterdaten könnte darin bestehen, dass ein Bekleidungshändler Daten zu seinen Produkten erfasst und diese Informationen dann an wichtige Partner weitergibt. In diesem Fall könnte der Einzelhandel verschiedene Anzeigen auf einer [!DNL Audience Manager] Partner-Site für Kunden bereitstellen, die verschiedene Jackettfarben und -größen auswählen.

![](assets/shopping-cart-traits.png)

## Drittanbieterdatenerfassung {#third-party-data}

Daten von Drittanbietern sind Informationen, die von Anbietern außerhalb von [!DNL Audience Manager] erfasst und freigegeben werden.

Daten von Drittanbietern können verwendet werden, um vorhandene Daten [!UICONTROL segments] (z. B. Alter, Haushaltseinkommen usw.) zu qualifizieren, Daten bereitzustellen, die nachgefragt sind, aber nicht anderweitig verfügbar sind, oder um bei der Suche nach einer bekannten Benutzerbasis aus Erstanbieter- und Zweitanbieterdaten verwendet zu werden. [!DNL Audience Manager] arbeitet mit vielen Drittdatenanbietern zusammen und hilft Ihnen, die Art der von diesen Datenanbietern erfassten Daten zu verstehen, sodass Sie die richtigen strategischen Vereinbarungen mit jedem Anbieter abschließen können.

>[!NOTE]
>
>Eine vollständige Liste der von [!DNL Audience Manager] unterstützten Drittdatenanbietern finden Sie im [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] integriert mit anderen Datenanbietern auf Grundlage ihrer verfügbaren Daten  [!DNL APIs] und Datensätze. Die Datenerfassung erfolgt in Echtzeit, wenn ein Benutzer Ihre Site durchsucht, oder über Out-of-Band-Methoden, bei denen IDs zwischen Partnern synchronisiert werden und Daten zwischen Servern übertragen werden, nachdem ein Benutzer Ihre Site verlassen hat. In beiden Fällen profitieren Clients von der Synchronisierung von Drittanbieterdaten auf unserer Plattform, d. h. jeder Client oder jede Domäne muss keine eigene Synchronisierung durchführen. [!DNL Audience Manager] Damit wird die Reichweite erhöht und Server-Aufrufe von der Seite verringert.

## Abgleichspartner {#match-partners}

Viele Kunden entscheiden sich für die Zusammenarbeit mit externen Datenabgleichspartnern. Diese Entitäten haben Beziehungen zu Websites mit Registrierungsanforderungen und können Kundendatendateien verarbeiten, indem sie diese (in Echtzeit) basierend auf ihrem Registrierungsnetzwerk abgleichen.

![Datenanbieterabgleich](assets/data-provider-match.png)

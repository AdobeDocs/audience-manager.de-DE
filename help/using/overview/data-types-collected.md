---
description: Mit Audience Manager können Sie Erstanbieter-, Zweitanbieter- und Drittanbieterdaten erfassen und verwalten.
seo-description: Audience Manager helps you collect and manage first-party, second-party, and third-party data.
seo-title: Types of Data Collected
solution: Audience Manager
title: Erfasste Datentypen
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: Overview
exl-id: cfb587da-ceac-425f-8334-e961eba6fad2
source-git-commit: 15e36d2847627b5e5ccef11f8073ce5124f14815
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 60%

---

# Erfasste Datentypen {#types-of-data-collected}

Mit [!DNL Audience Manager] können Sie Erstanbieter-, Zweitanbieter- und Drittanbieter-Daten erfassen und verwalten.

Die Nutzung von in mehreren Silos gespeicherten Kundendatenelementen ist eine der größten Datenherausforderungen, mit denen Unternehmen heute konfrontiert sind. Von [!DNL CRM] -Datenbanken über Registrierungssysteme bis hin zu Werbeservern usw. benötigen Unternehmen Tools, mit denen wertvolle Daten zentralisiert und Kunden-/Zielgruppeninformationen als ein einziges strategisches Datenelement verwaltet werden können. Mit [!DNL Audience Manager] können Sie isolierte Kundeninformationen entsperren und die Datenerfassung aus mehreren Quellen verwalten. Die erfassten Daten können basierend auf den Werten für die Live-Zeit des Datenelements ([!DNL TTL]) verwaltet werden, wodurch der Herausgeber die Gültigkeit von Daten über alle Quellen hinweg steuern kann. [!DNL Audience Manager] soll Ihnen bei der Verwaltung der folgenden Datentypen helfen:

| Datentyp | Datenquelle |
|---|---|
| **Erstanbieter** | Kunden. Daten werden online (aus Interaktionen der Verbraucher auf Ihren Websites) oder offline erfasst. |
| **Zweitanbieter** | Strategische Partner und Advertiser. |
| **Drittanbieter** | Datenanbieter und/oder Datenaustausch. Zu den Daten können Informationen wie Absichten, Demographie, Sozial-/Lebensstil, Psychographie und mehr gehören. |

## Erstanbieter-Datenerfassung {#first-party-data}

Die Erstanbieter-Datenerfassung ist eine wichtige [!DNL Audience Manager]-Funktion. Diese Kernkompetenz richtet sich an die Bedürfnisse unserer Kunden (Publisher und Advertiser), die proprietäre Daten als Eckpfeiler ihrer Marketing-Programme oder für Targeting und Modellierung mit anderen Datenquellen verwenden möchten.

[!DNL Audience Manager] arbeitet mit Kunden zusammen, um ihre Datenstrategie zu verstehen, und ordnet diese Strategie dann einem benutzerdefinierten Datenerfassungsplan zu. Unser Partner Solutions-Team arbeitet mit Ihnen zusammen, um Sites, Rohdatensignale und andere Benutzerinteraktionen auf Ihren Websites auszuwerten. Mit diesen Informationen helfen wir Ihnen bei der Erstellung einer maßgeschneiderten Datenerfassungsstrategie, die Datensignale auf Benutzerebene von verschiedenen Seiten in Ihrem Bestand erfasst. Erfasste Daten werden gespeichert und einer vordefinierten Taxonomie zugeordnet, die jederzeit aktualisiert werden kann, wenn sich die Anforderungen Ihres Unternehmen ändern.

Das folgende Beispiel zeigt, wie potenzielle Datenelemente von einer Beispieleinkaufsseite erfasst werden können.

![Warenkorbdaten](assets/shopping-cart-data.png)

| Element | Beschreibung |
|---|---|
| 1 | **Geschlecht**. Der Vorname eines Käufers gibt normalerweise das Geschlecht an. In unserem Beispiel ist der Vorname des Käufers Mary, also wissen wir, dass der Käufer eine Frau ist. Namen werden nie von Audience Manager gespeichert. |
| 2 | **Interessen**. Die Artikel im Warenkorb können auf verschiedene Interessen hinweisen. In unserem Beispiel gibt Mary viel für Fitnessgeräte aus. |
| 3 | **Wohnungstyp**. Je nach Lieferadresse und/oder Rechnungsadresse können Sie entscheiden, ob Mary Fitnessgeräte für sich selbst oder für eine Firma kauft. |
| 4 | **Standort**. [!DNL ZIP] -Codes sind zuverlässiger als [!DNL IP] -Adressen, wenn es darum geht, einen Ort zu bestimmen. |
| 5 | **Promotionsaffinität**. Wenn ein Käufer Werbe-Codes oder Geschenkkarten verwendet, ist er wahrscheinlich ein Schnäppchenjäger, der nach den besten Angeboten sucht. |
| 6 | **Kaufkraft**. Preisdaten, die mit [!DNL ZIP+4] -Codes korreliert werden, geben die Kaufkraft eines bestimmten Standorts an. |

Nachdem die Rohdaten erfasst wurden, werden sie in der [!DNL Audience Manager] -Plattform benutzerdefinierten Eigenschaften zugeordnet. Sowohl die Taxonomie als auch die Datenzuordnung können jederzeit angepasst werden, ohne dass Änderungen am Datenerfassungs-Code vorgenommen werden.

## Zweitanbieterdatenerfassung {#second-party-data}

Zweitanbieterdaten stammen von einem strategischen Unternehmenspartner (es handelt sich nicht um Publisher-Daten). Diese Informationen werden wie Erstanbieterdaten erfasst und verwaltet.

In einem Zweitanbieterdatenszenario senden Advertiser ihre eigenen Daten-Assets an Publisher, damit diese die Informationen mit den Daten des Publishers kombinieren und dann ein gezielteres Werbeprogramm ausführen können. Darüber hinaus können Publisher ihre Zielgruppen-Pools durch eine Partnerschaft mit ihren Advertisern erweitern. In den meisten Fällen handelt es sich bei diesen Vereinbarungen um vertragliche Beziehungen, die darauf beschränkt sind, das [!DNL Audience Manager] -Container-Tag auf der Partner-Site zu platzieren, um die Datenerfassung und -freigabe zu erleichtern.

Ein Beispiel für die Erfassung und das Remarketing von Zweitanbieterdaten könnte darin bestehen, dass ein Bekleidungshändler Daten zu seinen Produkten erfasst und diese Informationen dann an wichtige Partner weitergibt. In diesem Fall könnte der Einzelhändler verschiedene Anzeigen auf einer [!DNL Audience Manager] -Partnerseite für Verbraucher bereitstellen, die verschiedene Jackenfarben und -größen auswählen.

![](assets/shopping-cart-traits.png)

## Datenerfassung von Drittanbietern {#third-party-data}

Drittanbieterdaten sind Informationen, die von Anbietern außerhalb von [!DNL Audience Manager] erfasst und freigegeben werden.

Daten von Drittanbietern können verwendet werden, um vorhandene Daten [!UICONTROL segments] zu qualifizieren (z. B. Alter, Haushaltseinkommen usw.), Daten bereitzustellen, die gefragt, aber nicht anderweitig verfügbar sind, oder um eine Look-alike-Modellierung anhand einer bekannten Benutzerbasis aus Erstanbieter- und Zweitanbieterdaten durchzuführen. [!DNL Audience Manager] arbeitet mit vielen Datenanbietern von Drittanbietern zusammen und hilft Ihnen, den Datentyp zu verstehen, den diese Datenanbieter erfassen. So können Sie für jeden Anbieter die richtigen strategischen Vereinbarungen treffen.

>[!NOTE]
>
>Eine vollständige Liste der von [!DNL Audience Manager] unterstützten Drittdatenanbietern finden Sie im [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] kann basierend auf den verfügbaren [!DNL APIs] und Datensätzen mit anderen Datenanbietern integriert werden. Die Datenerfassung erfolgt in Echtzeit, wenn ein Benutzer Ihre Site durchsucht, oder über Out-of-Band-Methoden, bei denen IDs zwischen Partnern synchronisiert werden und Daten zwischen Servern übertragen werden, nachdem ein Benutzer Ihre Site verlassen hat. In beiden Fällen profitieren [!DNL Audience Manager] -Clients davon, dass Daten von Drittanbietern auf unserer Plattform synchronisiert werden. Das bedeutet, dass jeder Client oder jede Domäne keine eigene Synchronisierung durchführen muss. Damit wird die Reichweite erhöht und Server-Aufrufe von der Seite verringert.

## Abgleichspartner {#match-partners}

Viele Kunden entscheiden sich für die Zusammenarbeit mit externen Datenabgleichspartnern. Diese Entitäten haben Beziehungen zu Websites mit Registrierungsanforderungen und können Kundendatendateien verarbeiten, indem sie diese (in Echtzeit) basierend auf ihrem Registrierungsnetzwerk abgleichen.

![Datenanbieterabgleich](assets/data-provider-match.png)

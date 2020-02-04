---
description: Mit Audience Manager können Sie Erstanbieter-, Zweitanbieter- und Drittanbieter-Daten erfassen und verwalten.
seo-description: Mit Audience Manager können Sie Erstanbieter-, Zweitanbieter- und Drittanbieter-Daten erfassen und verwalten.
seo-title: Datenerfassungstypen
solution: Audience Manager
title: Datenerfassungstypen
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
translation-type: tm+mt
source-git-commit: f37f5c3747357205fa35bff6bb2322b8b909cb3c

---


# Datenerfassungstypen{#types-of-data-collected}

Mit Audience Manager können Sie Erstanbieter-, Zweitanbieter- und Drittanbieter-Daten erfassen und verwalten.

Die Entsperrung von in mehreren Silos gespeicherten Kundendatenelementen ist eine der größten Herausforderungen für Unternehmen heute. Von CRM-Datenbanken über Registrierungssysteme bis hin zu Anzeigenservern usw. benötigen Unternehmen Tools, mit deren Hilfe wertvolle Daten zentralisiert und Kunden-/Zielgruppeninformationen als ein einziges strategisches Datenelement verwaltet werden können. Mit Audience Manager können Sie isolierte Kundeninformationen entsperren und die Datenerfassung aus mehreren Quellen verwalten. Die erfassten Daten können auf Basis von TTL-Werten (Time-to-Live) des Datenelements verwaltet werden, wodurch der Herausgeber den Ablauf von Daten über alle Quellen hinweg steuern kann. Audience Manager unterstützt Sie bei der Verwaltung der folgenden Datentypen:

| Datentyp | wobei Daten von |
|---|---|
| **Erstanbieter** | Bekannte. Daten werden online (aus Interaktionen der Verbraucher auf Ihren Websites) oder offline erfasst. |
| **Zweitanbieter** | Strategische Partner und Werbetreibende. |
| **Drittanbieter** | Datenanbieter und/oder Datenaustausch. Zu den Daten können Informationen wie Absichten, Demografie, Sozial-/Lebensstil, Psychografie und mehr gehören. |

## First-Party Data Collection {#first-party-data}

Die Datenerfassung durch Erstanbieter ist eine der wichtigsten Funktionen von Audience Manager. Diese Kernkompetenz richtet sich an die Bedürfnisse unserer Kunden (Herausgeber oder Werbetreibende), die proprietäre Daten als Eckpfeiler ihrer Marketingprogramme oder für Targeting und Modellierung mit anderen Datenquellen verwenden möchten.

<!-- 

c_1st_party_data.xml

 -->

Audience Manager arbeitet mit Kunden zusammen, um deren Datenstrategie zu verstehen und diese Strategie dann einem benutzerdefinierten Datenerfassungsplan zuzuordnen. Unser Partner Solutions-Team arbeitet mit Ihnen zusammen, um Sites, Rohdatensignale und andere Benutzerinteraktionen auf Ihren Websites zu bewerten. Mit diesen Informationen helfen wir Ihnen bei der Erstellung einer maßgeschneiderten Datenerfassungsstrategie, die Datensignale auf Benutzerebene von verschiedenen Seiten in Ihrem Bestand erfasst. Erfasste Daten werden gespeichert und einer vordefinierten Taxonomie zugeordnet, die jederzeit aktualisiert werden kann, wenn sich Ihr Unternehmen ändert.

Das folgende Beispiel zeigt, wie potenzielle Datenelemente von einer Einkaufsseite erfasst werden können.

![shopping-cart-data](assets/shopping-cart-data.png)

| Element | Beschreibung |
|---|---|
| 1 | **Geschlecht**. Der Vorname eines Bestellers gibt normalerweise das Geschlecht an. In unserem Beispiel ist der Vorname des Käufers Maria, also wissen wir, dass der Käufer eine Frau ist. Namen werden nie von Audience Manager gespeichert. |
| 2 | **Interessen**. Die Artikel im Warenkorb können auf verschiedene Interessen hinweisen. In unserem Beispiel gibt Maria viel für Fitnessgeräte aus. |
| 3 | **Wohnungstyp**. Je nach Lieferadresse und/oder Rechnungsadresse können Sie entscheiden, ob Mary Fitnessgeräte für sich selbst oder für eine Firma kauft. |
| 4 | **Ort**. ZIP-Codes sind zuverlässiger als IP-Adressen, wenn es um die Standortbestimmung geht. |
| 5 | **Förderaffinität**. Wenn ein Käufer Werbecodes oder Geschenkkarten verwendet, sind sie wahrscheinlich ein Schnäppchenjäger, der nach den besten Geschäften sucht. |
| 6 | **Ausgeben von Strom**. Preisdaten, die mit Postleitzahlen korrelieren, geben die Ausgabenstärke eines bestimmten Ortes an. |

Nachdem die Rohdaten erfasst wurden, werden sie in der Audience Manager-Plattform wieder benutzerdefinierten Eigenschaften zugeordnet. Sowohl die Taxonomie als auch die Datenzuordnung können jederzeit angepasst werden, ohne dass Änderungen am Datenerfassungscode vorgenommen werden.

## Datenerfassung durch Zweitanbieter {#second-party-data}

Daten von Zweitanbietern stammen von einem strategischen Geschäftspartner (es handelt sich nicht um Veröffentlichungsdaten). Diese Informationen werden wie Erstanbieter-Daten gesammelt und verwaltet.

<!-- 

c_2nd_party_data.xml

 -->

In einem Szenario mit Daten von Zweitanbietern senden Werbetreibende ihre eigenen Daten-Assets an Herausgeber, damit sie diese Informationen mit den Daten des Herausgebers kombinieren und dann ein gezielteres Werbetreff ausführen können. Darüber hinaus können Herausgeber ihren Zielgruppenpool durch Zusammenarbeit mit ihren Werbekunden erweitern. In den meisten Fällen beinhalten diese Vereinbarungen vertragliche Beziehungen, die sich darauf beschränken, den Audience Manager-Container-Tag auf die Partner-Site zu setzen, um die Datenerfassung und -freigabe zu erleichtern.

Ein Beispiel für die Erhebung und das Remarketing von Daten von Zweitanbietern könnte darin bestehen, dass ein Bekleidungshändler Daten über seine Produkte sammelt und diese Informationen dann an wichtige Partner weitergibt. In diesem Fall könnten die verkauften Anzeigen auf einer Audience Manager-Partnersite für Kunden, die verschiedene Jackettfarben und -größen auswählen, verschiedene Anzeigen bereitstellen.

![](assets/shopping-cart-traits.png)

## Third-Party Data Collection {#third-party-data}

Daten von Drittanbietern sind Informationen, die von Anbietern außerhalb von Audience Manager erfasst und freigegeben werden.

<!-- 

c_3rd_party_data.xml

 -->

Daten von Drittanbietern können verwendet werden, um vorhandene Datensegmente (z. B. Alter, Haushaltseinkommen usw.) zu qualifizieren, Daten bereitzustellen, die nachgefragt sind, aber nicht anderweitig verfügbar sind, oder um bei der Suche nach einem bekannten Benutzerstamm aus Erstanbieter- und Zweitanbieter-Daten verwendet zu werden. Audience Manager arbeitet mit vielen Drittanbietern von Daten zusammen und hilft Ihnen dabei, die Art der von diesen Datenanbietern erfassten Daten zu verstehen, sodass Sie mit jedem Anbieter die richtigen strategischen Geschäfte abschließen können.

>[!NOTE]
>
>Eine vollständige Liste der von Drittanbietern unterstützten Datenanbieter finden Sie [!DNL Audience Manager]im [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

Audience Manager kann auf Grundlage der verfügbaren APIs und Datensätze mit anderen Datenanbietern integriert werden. Die Datenerfassung funktioniert in Echtzeit, wenn ein Benutzer Ihre Site aufsucht, oder über Out-of-Band-Methoden, bei denen IDs zwischen Partnern synchronisiert werden und Daten zwischen Servern übertragen werden, nachdem ein Benutzer Ihre Site verlassen hat. In beiden Fällen profitieren Audience Manager-Clients davon, dass Daten von Drittanbietern auf unserer Plattform synchronisiert werden, d. h. jeder Client oder jede Domäne muss keine eigene Synchronisierung durchführen. Dies hilft, die Reichweite zu erhöhen und Serveraufrufe von der Seite zu verringern.

## Übereinstimmungspartner {#match-partners}

Viele Kunden entscheiden sich für die Zusammenarbeit mit Drittanbieter-Datenerfassungspartnern. Diese Entitäten unterhalten Beziehungen zu Sites, die Registrierungsanforderungen haben und Kundendatendateien verarbeiten können, indem sie diese (in Echtzeit) je nach Registrierungsnetzwerk abgleichen.

![data-provider-match](assets/data-provider-match.png)

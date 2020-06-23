---
description: Mit Audience Manager können Sie Erstanbieter-, Zweitanbieter- und Drittanbieter-Daten erfassen und verwalten.
seo-description: Mit Audience Manager können Sie Erstanbieter-, Zweitanbieter- und Drittanbieter-Daten erfassen und verwalten.
seo-title: Datenerfassungstypen
solution: Audience Manager
title: Datenerfassungstypen
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 1%

---


# Datenerfassungstypen {#types-of-data-collected}

[!DNL Audience Manager] hilft Ihnen, Erstanbieter-, Zweitanbieter- und Drittanbieter-Daten zu erfassen und zu verwalten.

Die Entsperrung von in mehreren Silos gespeicherten Kundendatenelementen ist eine der größten Datenschwierigkeiten, vor denen Firmen heute stehen. Von [!DNL CRM] Datenbanken über Registrierungssysteme bis hin zu Anzeigenservern usw. benötigen Firmen Tools, die helfen, wertvolle Daten zu zentralisieren und Audiencen-Informationen als ein einziges strategisches Datenelement zu verwalten. [!DNL Audience Manager] hilft Ihnen, isolierte Kundeninformationen zu entsperren und die Datenerfassung aus mehreren Quellen zu verwalten. Die gesammelten Daten können auf der Grundlage der Werte für die &quot;Time-to-Live&quot;-Zeit des Datenelements verwaltet werden, was dem Herausgeber hilft, den Ablauf von Daten über alle Quellen hinweg zu steuern.[!DNL TTL] [!DNL Audience Manager] wurde entwickelt, um Ihnen bei der Verwaltung der folgenden Datentypen zu helfen:

| Datentyp | wobei Daten von |
|---|---|
| **Erstanbieter** | Bekannte. Daten werden online (aus Interaktionen der Verbraucher auf Ihren Websites) oder offline erfasst. |
| **Zweitanbieter** | Strategische Partner und Werbetreibende. |
| **Drittanbieter** | Datenanbieter und/oder Datenaustausch. Zu den Daten können Informationen wie Absichten, Demografie, Sozial-/Lebensstil, Psychografie und mehr gehören. |

## First-Party Data Collection {#first-party-data}

Die Datenerfassung durch Erstanbieter ist eine der wichtigsten [!DNL Audience Manager] Funktionen. Diese Kernkompetenz richtet sich an die Bedürfnisse unserer Kunden (Herausgeber oder Werbetreibende), die proprietäre Daten als Eckpfeiler ihrer Marketing-Programm oder für Targeting und Modellierung mit anderen Datenquellen verwenden möchten.

[!DNL Audience Manager] arbeitet mit Kunden zusammen, um ihre Datenstrategie zu verstehen und ordnet diese Strategie dann einem benutzerdefinierten Datenerfassungsplan zu. Unser Partner Solutions-Team arbeitet mit Ihnen zusammen, um Sites, Rohdatensignale und andere Benutzerinteraktionen auf Ihren Websites zu bewerten. Mit diesen Informationen helfen wir Ihnen bei der Erstellung einer maßgeschneiderten Datenerfassungsstrategie, die Datensignale auf Benutzerebene von verschiedenen Seiten in Ihrem Bestand erfasst. Erfasste Daten werden gespeichert und einer vordefinierten Taxonomie zugeordnet, die jederzeit aktualisiert werden kann, wenn sich Ihr Unternehmen ändert.

Das folgende Beispiel zeigt, wie potenzielle Datenelemente von einer Einkaufsseite erfasst werden können.

![shopping-cart-data](assets/shopping-cart-data.png)

| Element | Beschreibung |
|---|---|
| 1 | **Geschlecht**. Der Vorname eines Bestellers gibt normalerweise das Geschlecht an. In unserem Beispiel ist der Vorname des Käufers Maria, also wissen wir, dass der Käufer eine Frau ist. Namen werden nie von Audience Manager gespeichert. |
| 2 | **Interessen**. Die Artikel im Warenkorb können auf verschiedene Interessen hinweisen. In unserem Beispiel gibt Maria viel für Fitnessgeräte aus. |
| 3 | **Wohnungstyp**. Je nach Lieferadresse und/oder Rechnungsadresse können Sie entscheiden, ob Mary Fitnessgeräte für sich selbst oder für eine Firma kauft. |
| 4 | **Ort**. [!DNL ZIP] -Codes sind zuverlässiger als [!DNL IP] Adressen, wenn es darum geht, einen Ort zu bestimmen. |
| 5 | **Affinität** der Verkaufsförderung. Wenn ein Käufer Werbecodes oder Geschenkkarten verwendet, sind sie wahrscheinlich ein Schnäppchenjäger, der nach den besten Geschäften sucht. |
| 6 | **Ausgeben von Strom**. Preisdaten, die mit [!DNL ZIP+4] Codes korrelieren, geben die Ausgabenstärke eines bestimmten Standorts an. |

Nachdem die Rohdaten erfasst wurden, werden sie den benutzerdefinierten Eigenschaften innerhalb der [!DNL Audience Manager] Plattform zugeordnet. Sowohl die Taxonomie- als auch die Datenzuordnung können jederzeit angepasst werden, ohne dass Änderungen am Datenerfassungscode vorgenommen werden.

## Datenerfassung durch Zweitanbieter {#second-party-data}

Daten von Zweitanbietern stammen von einem strategischen Geschäftspartner (es handelt sich nicht um Veröffentlichungsdaten). Diese Informationen werden wie Erstanbieter-Daten gesammelt und verwaltet.

In einem Zweitanbieter-Datenszenario senden Werbetreibende ihre eigenen Daten-Assets an Herausgeber, damit sie diese Informationen mit den Daten des Herausgebers kombinieren und dann ein gezielteres Programm für Werbung ausführen können. Darüber hinaus können Herausgeber ihre Audience-Pools durch eine Partnerschaft mit ihren Werbekunden erweitern. In den meisten Fällen schließen diese Vereinbarungen vertragliche Beziehungen ein, die sich darauf beschränken, den [!DNL Audience Manager] Container-Tag auf der Partnerseite zu platzieren, um die Datenerfassung und -freigabe zu erleichtern.

Ein Beispiel für die Erhebung und das Remarketing von Daten von Zweitanbietern könnte darin bestehen, dass ein Bekleidungshändler Daten über seine Produkte sammelt und diese Informationen dann an wichtige Partner weitergibt. In diesem Fall könnte der Einzelhandel verschiedene Anzeigen auf einer [!DNL Audience Manager] Partner-Site für Kunden bereitstellen, die verschiedene Jackettfarben und -größen auswählen.

![](assets/shopping-cart-traits.png)

## Third-Party Data Collection {#third-party-data}

Daten von Drittanbietern sind Informationen, die von Anbietern außerhalb von [!DNL Audience Manager]Drittanbietern gesammelt und freigegeben werden.

Daten von Drittanbietern können verwendet werden, um vorhandene Daten zu qualifizieren [!UICONTROL segments] (z. B. Alter, Haushaltseinkommen usw.), Daten bereitzustellen, die in der Nachfrage vorhanden sind, aber nicht anderweitig verfügbar sind, oder bei der Suche nach einer bekannten Benutzerbasis aus Erstanbieter- und Zweitanbieterdaten verwendet werden. [!DNL Audience Manager] arbeitet mit vielen Drittanbietern von Daten zusammen und hilft Ihnen, die Art der Daten zu verstehen, die diese Datenanbieter erfassen, damit Sie die richtigen strategischen Geschäfte mit jedem Anbieter abschließen können.

>[!NOTE]
>
>Eine vollständige Liste der von Drittanbietern unterstützten Datenanbieter finden Sie [!DNL Audience Manager]im [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] in andere Datenanbieter auf Grundlage ihrer verfügbaren Daten [!DNL APIs] und Datensätze integriert. Die Datenerfassung funktioniert in Echtzeit, wenn ein Benutzer Ihre Site aufsucht, oder über Out-of-Band-Methoden, bei denen IDs zwischen Partnern synchronisiert werden und Daten zwischen Servern übertragen werden, nachdem ein Benutzer Ihre Site verlassen hat. In beiden Fällen profitieren [!DNL Audience Manager] Kunden davon, dass Daten von Drittanbietern auf unserer Plattform synchronisiert werden, was bedeutet, dass jeder Kunde oder jede Domäne keine eigene Synchronisierung durchführen muss. Dies hilft, die Reichweite zu erhöhen und Serveraufrufe von der Seite zu verringern.

## Übereinstimmungspartner {#match-partners}

Viele Kunden entscheiden sich für die Zusammenarbeit mit Drittanbieter-Datenerfassungspartnern. Diese Entitäten unterhalten Beziehungen zu Sites, die Registrierungsanforderungen haben und Kundendatendateien verarbeiten können, indem sie diese (in Echtzeit) je nach Registrierungsnetzwerk abgleichen.

![data-provider-match](assets/data-provider-match.png)

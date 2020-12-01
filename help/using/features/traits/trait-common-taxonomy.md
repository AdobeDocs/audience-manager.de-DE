---
description: Dieser Artikel bietet einen allgemeinen Überblick über die Klassifizierung von Eigenschaften mit einer allgemeinen Taxonomie.
keywords: DIL
seo-description: Dieser Artikel bietet einen allgemeinen Überblick über die Klassifizierung von Eigenschaften mit einer allgemeinen Taxonomie.
seo-title: Klassifizieren von Eigenschaften mit einer gemeinsamen Taxonomie
solution: Audience Manager
title: Klassifizieren von Eigenschaften mit einer gemeinsamen Taxonomie
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 4%

---


# Klassifizieren von Eigenschaften mit einer gemeinsamen Taxonomie {#classifying-traits-with-a-common-taxonomy}

Dieser Artikel bietet einen allgemeinen Überblick über die Klassifizierung von Eigenschaften mit einer allgemeinen Taxonomie.

## Die Steuersysteme im Audience Manager

<!-- c_common_taxonomy_about.xml -->

Die Taxonomie [!DNL Audience Manager] ist eine optionale Funktion, die Eigenschaften mithilfe einheitlicher, logischer und allgemein verständlicher Benennungskonventionen klassifiziert. Es arbeitet auf Plattformebene, um die Benennungskonsistenz im gesamten [!DNL Audience Manager]-Ökosystem sicherzustellen. Letztlich soll die gemeinsame Taxonomie unser Produkt stärker an die Industriestandards in Bezug auf Privatsphäre der Verbraucher und Opt-out-Verfahren anpassen.

## Vorteile der Klassifizierung von Eigenschaften

Die Möglichkeit für unsere Kunden, benutzerdefinierte Segmente und Datenmodelle zu erstellen, ist das Kernstück des [!DNL Audience Manager]-Modells und Ihrer Fähigkeit, Werte von unserer Plattform zu erfassen. Erforderlich ist jedoch auch ein robustes und skalierbares Mittel, um Informationen über Segmente an Ihre Kunden und Partner zu übermitteln. Darüber hinaus erfordert diese Kommunikation, dass Segmentinformationen in einer leicht verständlichen und allgemein verständlichen Sprache freigegeben werden, während Ihre proprietären Eigenschaften und Segmentnamen geschützt werden. Die [!DNL Audience Manager] allgemeine Taxonomie bietet diese Sprache und Funktionalität.

## Die Taxonomie nutzt die Kategorien der Branchenstandard-Klassifizierung

Die allgemeine Taxonomie basiert auf den Klassifizierungen, die von [!DNL Interactive Advertising Bureau (IAB)] erstellt werden. Weitere Informationen zu Qualitätssicherungsrichtlinien für Netzwerke und Austausche finden Sie auf der [!DNL IAB] [Website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines).

## Taxonomische Organisation

Die Taxonomie [!DNL Audience Manager] organisiert Daten in verschachtelte Kategorien, die als Stufen bezeichnet werden. Jede Kategorie kann bis zu 3 verschiedene Stufen für die Datenklassifizierung enthalten. Auf der höchsten Ebene gruppiert eine Tier-1-Kategorie Daten in ihrer allgemeinsten Form (z. B. Geografie). Nachfolgende Stufen bieten eine größere Spezifität für die höhere Ebene, die allgemeine Kategorie (z. B. *geografie —> Vereinigte Staaten —> New York*). Aber nicht jede Kategorie hat 3 Stufen, einige verwenden nur 2.

## Eigenschaften in Kategorien klassifizieren

Sie weisen beim Erstellen oder Bearbeiten von Eigenschaften im [!UICONTROL Add New Trait Wizard] (in * **[!UICONTROL Audience Data > Traits]***) taxonomische Classifications zu. Weitere Informationen zum Erstellen von Eigenschaften](../../features/traits/create-onboarded-rule-based-traits.md) finden Sie in der [Dokumentation.

## Arbeiten mit der Taxonomie: Zusätzliche Überlegungen

Wenn Sie sich entscheiden, Eigenschaften nach unserer allgemeinen Taxonomie zu klassifizieren, sollten Sie sich Folgendes merken:

* Klassifizierung ist *optional*.
* Die Eigenschaften *sind nicht* standardmäßig einer taxonomischen Kategorie zugeordnet (d. h. Eigenschaften werden nicht als &quot;unbekannt&quot;oder &quot;nicht kategorisiert&quot;usw. klassifiziert).
* Eigenschaften können nur zu *einer* taxonomischen Kategorie gehören (Mehrfachklassifizierungen und Kategorien sind nicht zulässig).
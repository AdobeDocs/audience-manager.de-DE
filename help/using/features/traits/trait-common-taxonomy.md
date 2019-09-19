---
description: Dieser Artikel bietet einen allgemeinen Überblick über die Klassifizierung von Eigenschaften mit einer allgemeinen Taxonomie.
keywords: DIL 
seo-description: Dieser Artikel bietet einen allgemeinen Überblick über die Klassifizierung von Eigenschaften mit einer allgemeinen Taxonomie.
seo-title: Klassifizieren von Eigenschaften mit einer gemeinsamen Taxonomie
solution: Audience Manager
title: Klassifizieren von Eigenschaften mit einer gemeinsamen Taxonomie
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Klassifizieren von Eigenschaften mit einer gemeinsamen Taxonomie {#classifying-traits-with-a-common-taxonomy}

Dieser Artikel bietet einen allgemeinen Überblick über die Klassifizierung von Eigenschaften mit einer allgemeinen Taxonomie.

## Audience Manager-Taxonomie

<!-- c_common_taxonomy_about.xml -->

Die [!DNL Audience Manager] Taxonomie ist eine optionale Funktion, die Eigenschaften mithilfe einheitlicher, logischer und allgemein verständlicher Benennungskonventionen klassifiziert. Es arbeitet auf Plattformebene, um die Benennungskonsistenz im gesamten [!DNL Audience Manager] Ökosystem sicherzustellen. Letztlich soll die gemeinsame Taxonomie unser Produkt stärker an die Industriestandards in Bezug auf Privatsphäre der Verbraucher und Opt-out-Verfahren anpassen.

## Vorteile der Klassifizierung von Eigenschaften

Unsere Kunden in die Lage zu versetzen, benutzerspezifische Segmente und Datenmodelle zu erstellen, ist der Kern des [!DNL Audience Manager] Modells und Ihrer Fähigkeit, Werte von unserer Plattform zu erfassen. Erforderlich ist jedoch auch ein robustes und skalierbares Mittel, um Informationen über Segmente an Ihre Kunden und Partner zu übermitteln. Darüber hinaus erfordert diese Kommunikation, dass Segmentinformationen in einer leicht verständlichen und allgemein verständlichen Sprache freigegeben werden, während Ihre proprietären Eigenschaften und Segmentnamen geschützt werden. Die [!DNL Audience Manager] gemeinsame Taxonomie bietet diese Sprache und Fähigkeit.

## Die Taxonomie verwendet die Klassifizierungskategorien "Branchenstandard"

Die allgemeine Taxonomie basiert auf den Klassifizierungen, die vom [!DNL Interactive Advertising Bureau (IAB)]. Weitere Informationen zu Qualitätssichernde Leitlinien für Netzwerke und den Austausch finden Sie auf der [!DNL IAB]auf der [Website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) der .

## Taxonomische Organisation

Die [!DNL Audience Manager] Taxonomie organisiert Daten in verschachtelte Kategorien, die als Stufen bezeichnet werden. Jede Kategorie kann bis zu 3 separate Stufen für die Datenklassifizierung enthalten. Auf der höchsten Ebene gruppiert eine Kategorie der Stufe 1 Daten in ihrer allgemeinsten Form (z. B. Geografie). Nachfolgende Stufen bieten eine größere Spezifität zu der höheren Ebene, der allgemeinen Kategorie (z.B. *Geografie —&gt; USA —&gt; New York*). Allerdings hat nicht jede Kategorie 3 Stufen, einige verwenden nur 2.

## Eigenschaften in Datenkategorien klassifizieren

Sie weisen beim Erstellen oder Bearbeiten von Eigenschaften im [!UICONTROL Add New Trait Wizard] (in * **[!UICONTROL Audience Data > Traits]***) taxonomische Classifications zu. Weitere Informationen finden Sie in der [Dokumentation zum Erstellen von Eigenschaften](../../features/traits/create-onboarded-rule-based-traits.md) .

## Arbeiten mit der Taxonomie: Zusätzliche Überlegungen

Wenn Sie sich entscheiden, Eigenschaften nach unserer allgemeinen Taxonomie zu klassifizieren, sollten Sie sich Folgendes merken:

* Die Klassifizierung ist *optional*.
* Eigenschaften *werden standardmäßig keiner* taxonomischen Kategorie zugeordnet (d. h. Eigenschaften werden nicht als "unbekannt"oder "nicht kategorisiert"usw. klassifiziert).
* Eigenschaften können nur zu *einer* taxonomischen Kategorie gehören (Mehrfachklassifizierungen und Kategorieübergreifende Klassifizierungen sind nicht zulässig).
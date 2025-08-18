---
description: Dieser Artikel bietet einen allgemeinen Überblick über die Klassifizierung von Eigenschaften mit einer gemeinsamen Taxonomie.
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: Klassifizieren von Eigenschaften mit einer gemeinsamen Taxonomie
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# Klassifizieren von Eigenschaften mit einer gemeinsamen Taxonomie {#classifying-traits-with-a-common-taxonomy}

Dieser Artikel bietet einen allgemeinen Überblick über die Klassifizierung von Eigenschaften mit einer gemeinsamen Taxonomie.

## Die Audience Manager-Taxonomie

<!-- c_common_taxonomy_about.xml -->

Die [!DNL Audience Manager] Taxonomie ist eine optionale Funktion, die Eigenschaften mithilfe einheitlicher, logischer und allgemein verständlicher Benennungskonventionen klassifiziert. Sie wird auf Plattformebene ausgeführt, um eine konsistente Benennung im gesamten [!DNL Audience Manager]-Ökosystem sicherzustellen. Letztendlich wurde die gemeinsame Taxonomie entwickelt, um unser Produkt besser an die Branchenstandards in Bezug auf Privatsphäre und Opt-out-Prozesse für Verbraucher anzupassen.

## Vorteile der Eigenschaftenklassifizierung

Die Möglichkeit für unsere Kunden, benutzerdefinierte Segmente und Datenmodelle zu erstellen, ist von zentraler Bedeutung für das [!DNL Audience Manager] und Ihre Fähigkeit, den Wert unserer Plattform zu erfassen. Was jedoch auch erforderlich ist, ist eine robuste und skalierbare Methode zur Kommunikation von Informationen zu Segmenten an Ihre Kunden und Partner. Darüber hinaus erfordert diese Kommunikation, dass Segmentinformationen in einer leicht verständlichen und allgemein verständlichen Sprache ausgetauscht werden, während gleichzeitig Ihre proprietären Merkmale und Segmentnamen geschützt werden. Die [!DNL Audience Manager] gemeinsame Taxonomie bietet diese Sprache und diese Funktion.

## Die Taxonomie verwendet Klassifizierungskategorien nach Branchenstandard

Die gemeinsame Taxonomie basiert auf den Klassifizierungen, die von der [!DNL Interactive Advertising Bureau (IAB)] erstellt wurden. Weitere Informationen über Qualitätssicherungsrichtlinien für [!DNL IAB] und [ finden Sie auf der Website der ](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines).

## taxonomische Organisation

Die [!DNL Audience Manager] Taxonomie organisiert Daten in verschachtelte Kategorien, die als Ebenen bezeichnet werden. Jede Kategorie kann bis zu 3 separate Ebenen für die Datenklassifizierung enthalten. Auf der höchsten Ebene gruppiert eine Kategorie der Stufe 1 Daten in ihrer allgemeinsten Form (z. B. Geografie). Nachfolgende Ebenen bieten eine höhere Spezifität für die übergeordnete allgemeine Kategorie (z. B. *geography —> Vereinigte Staaten —> New York*). Nicht jede Kategorie verfügt jedoch über 3 Ebenen, einige verwenden nur 2.

## Klassifizieren von Eigenschaften in Datenkategorien

Sie können beim Erstellen oder Bearbeiten von Eigenschaften in der [!UICONTROL Add New Trait Wizard] (in * **[!UICONTROL Audience Data > Traits]***) taxonomische Klassifizierungen zuweisen. Weitere Informationen finden Sie in der [Dokumentation ](../../features/traits/create-onboarded-rule-based-traits.md) Erstellen von Eigenschaften“.

## Arbeiten mit der Taxonomie: Weitere Überlegungen

Wenn Sie sich entscheiden, Eigenschaften gemäß unserer gemeinsamen Taxonomie zu klassifizieren, sollten Sie Folgendes beachten:

* Die Klassifizierung ist *optional*.
* Eigenschaften *werden standardmäßig keiner* zugeordnet (d. h. Eigenschaften werden nicht als „unbekannt“ oder „nicht kategorisiert“ usw. klassifiziert).
* Eigenschaften können nur zu *einer* taxonomischen Kategorie gehören (mehrere und kategorieübergreifende Klassifizierungen sind nicht zulässig).

---
description: Häufige Fragen und Probleme zu Produkten und Funktionen.
keywords: audience manager cookies
seo-description: Häufige Fragen und Probleme zu Produkten und Funktionen.
seo-title: Häufig gestellte Fragen zu Produktfunktionen
solution: Audience Manager
title: Häufig gestellte Fragen zu Produktfunktionen
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 1%

---


# Häufig gestellte Fragen zu Produktfunktionen{#product-features-and-functions-faq}

Häufige Fragen und Probleme zu Produkten und Funktionen.

 

<!-- 

faq_features_functions.xml

 -->

**Was ist meine Organisations-ID und wie finde ich sie?**

Die *`Organization ID`* ist eine eindeutige ID, mit der Ihr Unternehmen identifiziert [!DNL Audience Manager] und die [!DNL Adobe Experience Cloud]. Es besteht aus einer 24-stelligen alphanumerischen Zeichenfolge, gefolgt von [!UICONTROL @AdobeOrg]der Groß- und Kleinschreibung.

So *`Organization ID`* sieht zum Beispiel eine aus: `1FD6776A524453CC0A490D44@AdobeOrg`.

Die *`Organization ID`* wird von der [DIL](../dil/dil-overview.md) -API des Audience Managers, dem Identitätsdienst für [Adobe Experience Platformen](https://docs.adobe.com/content/help/en/id-service/using/home.html)und anderen [!DNL Experience Cloud] Lösungen verwendet. Benutzer mit Administratorberechtigungen finden die *`Organization ID`* auf der [!DNL Adobe Admin Console]. Siehe Häufig gestellte Fragen zur [Administration - Benutzerverwaltung](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

 

**Kann ich Eigenschaften oder Ziele stapelweise erstellen?**

Ja. Siehe [Massenverwaltungswerkzeuge](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>Die [!UICONTROL Bulk Management Tools] Werkzeuge *werden von* nicht [!DNL Audience Manager]unterstützt. Sie werden nur aus Gründen der Bequemlichkeit und als Höflichkeit zur Verfügung gestellt. Bei Massenänderungen sollten Sie stattdessen mit den [Audience Manager-APIs](../api/api.md) arbeiten.

 

**Beim Ausführen eines Massen-ID-Exports an ein Ziel fehlen einige Kunden-IDs. Why does that happen?**

Wenn eine Geräte-ID ([AAM UUID](../reference/ids-in-aam.md)) mit mehreren CRM-IDs ([DPUUIDs](../reference/ids-in-aam.md)) verknüpft ist, wird nur die neueste Zuordnung exportiert. Aus diesem Grund wird möglicherweise eine niedrigere Anzahl von Geräte-IDs als erwartet exportiert.

 

**Kann der Bedarf an Tags oder Pixeln von Drittanbietern[!DNL Audience Manager]verringert und die Seitenladezeit verkürzt werden?**

Wenn [!DNL Audience Manager] sie mit Ihrem Drittanbieter-Datenpartner integriert ist, können Sie ihre Pixel und Tags durch einen Server-zu-Server-ID-Aufruf von ersetzen [!DNL Audience Manager]. In diesem Fall [!DNL Audience Manager] würde ein einzelner ID-Aufruf ausgelöst, wenn ein Benutzer zum ersten Mal angezeigt wird und diese Informationen mit Ihrem Drittanbieter-Partner synchronisiert werden. Dadurch entfällt die Notwendigkeit, mehrere Pixel von jeder Seite aufzurufen. Die Reduzierung von Pixelaufrufen kann die Seitenladezeit verbessern.

 

**Ich habe einen Datenfeed abonniert. Wo werden diese Daten gespeichert?**

Ihr Datenfeed und alle im Feed enthaltenen Eigenschaften werden als Unterordner und Eigenschaften in angezeigt [!DNL Audience Manager]. Gehen Sie zu **[!UICONTROL Audience Data > Traits]** und erweitern Sie den [!UICONTROL 3rd-Party Data] Ordner, um Ihre Eigenschaften Ansicht oder Segmente und Modelle mit diesen Daten zu erstellen.

 

**Was ist[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager, der zum Erstellen und Verwalten verwendet [!UICONTROL Tag Insertion Manager] (TIM) wird [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

 

**Was sind die Unterschiede zwischen Algorithmusmodellen und Eigenschaftsempfehlungen? Wann sollte ich sie alle benutzen?**

**Algorithmische Modelle**

Algorithmische Modelle finden nicht nur die einflussreichsten Eigenschaften, sondern bewerten auch die Benutzer anhand dieser Eigenschaften und weisen jedem Benutzer eine individuelle Bewertung zu. Anschließend erstellen Sie algorithmische Eigenschaften zur Zielgruppe Ihrer Benutzer. Mit den Steuerelementen für Genauigkeit und Reichweite im Eigenschaften-Aufbau können Sie angeben, welche Benutzer zu den Benutzern gehören, die die einflussreichen Eigenschaften haben, die Sie Zielgruppen vornehmen möchten.

Algorithmische Modelle ermöglichen es Ihnen, Benutzer mit unterschiedlichen Genauigkeitsstufen auszuwählen und in Audience Lab zu testen, welche Benutzergruppe besser konvertiert. Weitere Informationen finden Sie unter [Vergleichen von Modellen in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

In Algorithmischen Modellen wird das Modell alle 8 Tage ausgeführt und aktualisiert die Benutzer, die für algorithmische Eigenschaften qualifiziert sind.

**Trait Recommendations**

Trait Recommendations bietet eine schnelle Möglichkeit, Einblicke in andere Eigenschaften zu erhalten, die den Eigenschaften in einem Segment ähnlich sind.

Sie sollten Eigenschaftsempfehlungen in folgenden Fällen verwenden:

* Beim Erstellen eines Segments benötigen Sie schnelle Einblicke.
* Sie verwenden die Segmente für kurze Kampagnen oder wenn Sie die Audience, die konvertiert, schnell unterdrücken möchten;
* Du versuchst, die Reichweite zu maximieren.

 

**Unterscheiden sich die Segmente von Adobe Analytics und Audience Manager?**

Ja, lesen Sie bitte [Die Segmente in Analytics und Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) für eine ausführliche Beschreibung der Unterschiede.

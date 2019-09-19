---
description: Häufige Fragen und Probleme zu Produkten und Funktionen.
keywords: Zielgruppen-Manager-Cookies
seo-description: Häufige Fragen und Probleme zu Produkten und Funktionen.
seo-title: Häufig gestellte Fragen zu Produktfunktionen
solution: Audience Manager
title: Häufig gestellte Fragen zu Produktfunktionen
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Häufig gestellte Fragen zu Produktfunktionen{#product-features-and-functions-faq}

Häufige Fragen und Probleme zu Produkten und Funktionen.

<br> 

<!-- 

faq_features_functions.xml

 -->

**Was ist meine Organisations-ID und wie finde ich sie?**

Die *`Organization ID`* ist eine eindeutige ID, mit der Ihr Unternehmen identifiziert [!DNL Audience Manager] und die [!DNL Adobe Experience Cloud]. Es besteht aus einer 24-stelligen alphanumerischen Zeichenfolge gefolgt von [!UICONTROL @AdobeOrg]der Groß- und Kleinschreibung.

So *`Organization ID`* sieht zum Beispiel eine aus: `1FD6776A524453CC0A490D44@AdobeOrg`.

Der *`Organization ID`* wird von der [DIL](../dil/dil-overview.md) -API von Audience Manager, dem [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/)und anderen [!DNL Experience Cloud] Lösungen verwendet. Benutzer mit Administratorberechtigungen finden die *`Organization ID`* auf der [!DNL Adobe Admin Console]. Siehe Häufig gestellte Fragen zur [Administration - Benutzerverwaltung](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**Kann ich Eigenschaften oder Ziele stapelweise erstellen?**

Ja. Siehe [Massenverwaltungswerkzeuge](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>Die [!UICONTROL Bulk Management Tools] Werkzeuge *werden von* nicht[!DNL Audience Manager] unterstützt. Sie werden nur aus Gründen der Bequemlichkeit und als Höflichkeit bereitgestellt. Bei Massenänderungen sollten Sie stattdessen mit den [Audience Manager-APIs](../api/api.md) arbeiten.

<br> 

**Kann der Bedarf an Tags oder Pixeln von Drittanbietern[!DNL Audience Manager]verringert und die Seitenladezeit verkürzt werden?**

Wenn [!DNL Audience Manager] sie in Ihren Drittanbieter-Datenpartner integriert ist, können Sie ihre Pixel und Tags durch einen Server-zu-Server-ID-Aufruf von ersetzen [!DNL Audience Manager]. In diesem Fall [!DNL Audience Manager] würde ein einzelner ID-Aufruf ausgelöst, wenn ein Benutzer zum ersten Mal angezeigt wird und diese Informationen mit Ihrem Drittanbieter-Partner synchronisiert werden. Dadurch entfällt die Notwendigkeit, mehrere Pixel von jeder Seite aufzurufen. Die Reduzierung von Pixelaufrufen kann die Seitenladezeit verbessern.

<br> 

**Ich habe einen Datenfeed abonniert. Wo werden diese Daten gespeichert?**

Ihr Datenfeed und alle im Feed enthaltenen Eigenschaften werden als Unterordner und Eigenschaften in angezeigt [!DNL Audience Manager]. Gehen Sie zu **[!UICONTROL Audience Data > Traits]** und erweitern Sie den [!UICONTROL 3rd-Party Data] Ordner, um Ihre Eigenschaften anzuzeigen oder Segmente und Modelle mit diesen Daten zu erstellen.

<br> 

**Was ist[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager verwendet [!UICONTROL Tag Insertion Manager] (TIM), um zu erstellen und zu verwalten [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. Weitere Informationen finden Sie unter [Adobe Launch](https://docs.adobelaunch.com/) und [Dynamisches Tag-Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**Was sind die Unterschiede zwischen Algorithmusmodellen und Eigenschaftsempfehlungen? Wann sollte ich sie benutzen?**

**Algorithmische Modelle**

Algorithmische Modelle finden nicht nur die einflussreichsten Eigenschaften, sondern bewerten auch Benutzer anhand dieser Eigenschaften und weisen jedem Benutzer eine individuelle Bewertung zu. Anschließend erstellen Sie algorithmische Eigenschaften, die auf Ihre Benutzer zugeschnitten sind. Mit den Steuerelementen für Genauigkeit und Reichweite im Eigenschaften-Aufbau können Sie festlegen, welche Benutzer zu allen Benutzern gehören, die die einflussreichen Eigenschaften haben, die Sie ansprechen möchten.

Algorithmische Modelle ermöglichen es Ihnen, Benutzer mit unterschiedlichen Genauigkeitsstufen auszuwählen und in Audience Lab zu testen, welche Benutzergruppe besser konvertiert. Siehe den ausführlichen Verwendungsfall unter [Modelle vergleichen im Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

In Algorithmic Modellen wird das Modell alle 8 Tage ausgeführt und aktualisiert die Benutzer, die für algorithmische Eigenschaften qualifiziert sind.

**Trait Recommendations**

Trait Recommendations bietet eine schnelle Möglichkeit, Einblicke in andere Eigenschaften zu erhalten, die den Eigenschaften in einem Segment ähnlich sind.

Sie sollten Eigenschaftsempfehlungen verwenden, wenn:

* Beim Erstellen eines Segments benötigen Sie schnelle Einblicke.
* Sie verwenden die Segmente für kurze Kampagnen oder wenn Sie die Konvertierung der Zielgruppe schnell unterdrücken möchten.
* Sie versuchen, die Reichweite zu maximieren.

<br> 

**Gibt es Unterschiede zwischen Adobe Analytics- und Audience Manager-Segmenten?**

Ja. Eine ausführliche Beschreibung der Unterschiede finden Sie unter [Verstehen von Segmenten in Analytics und Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) .

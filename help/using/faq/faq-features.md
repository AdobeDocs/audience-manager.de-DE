---
description: Häufige produkt- und funktionsbezogene Fragen und Probleme.
keywords: Cookies in Audience Manager
seo-description: Häufige produkt- und funktionsbezogene Fragen und Probleme.
seo-title: Häufig gestellte Fragen zu Produktfunktionen
solution: Audience Manager
title: Häufig gestellte Fragen zu Produktfunktionen
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Überblick
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 88%

---

# Häufig gestellte Fragen zu Produktfunktionen {#product-features-and-functions-faq}

Häufige produkt- und funktionsbezogene Fragen und Probleme.

 

<!-- 

faq_features_functions.xml

 -->

**Was ist meine Organisations-ID und wie finde ich sie?**

Die *`Organization ID`* ist eine eindeutige ID, mit der Ihr Unternehmen in [!DNL Audience Manager] und in [!DNL Adobe Experience Cloud] identifiziert wird. Sie besteht aus einer 24-stelligen alphanumerischen Zeichenfolge, bei der die der Groß- und Kleinschreibung berücksichtigt wird, gefolgt von [!UICONTROL @AdobeOrg].

Eine *`Organization ID`* sieht beispielsweise so aus: `1FD6776A524453CC0A490D44@AdobeOrg`.

Die *`Organization ID`* wird von der [DIL](../dil/dil-overview.md)-API von Audience Manager, dem [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html) und anderen [!DNL Experience Cloud]-Lösungen verwendet. Benutzer mit Administratorberechtigungen können die *`Organization ID`* in der [!DNL Adobe Admin Console] finden. Siehe [Häufig gestellte Fragen zur Administration – Benutzerverwaltung](https://docs.adobe.com/content/help/de-DE/core-services/interface/manage-users-and-products/admin-getting-started.html).

 

**Kann ich Eigenschaften oder Ziele stapelweise erstellen?**

Ja. Siehe [Tools zur Massenverwaltung](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>Die [!UICONTROL Bulk Management Tools] werden von [!DNL Audience Manager] *nicht* unterstützt. Sie werden nur zur Vereinfachung und als Höflichkeit zur Verfügung gestellt. Bei Massenänderungen sollten Sie stattdessen mit den [Audience Manager-APIs](../api/api.md) arbeiten.

 

**Beim Ausführen eines Massen-ID-Exports für ein Ziel fehlen einige Kunden-IDs. Warum passiert das?**

Wenn eine Geräte-ID ([AAM UUID](../reference/ids-in-aam.md)) mit mehreren CRM-IDs ([DPUUIDs](../reference/ids-in-aam.md)) verknüpft ist, wird nur die neueste Zuordnung exportiert. Aus diesem Grund kann es vorkommen, dass weniger Geräte-IDs als erwartet exportiert werden.

 

**Kann [!DNL Audience Manager] den Bedarf an Tags oder Pixeln von Drittanbietern reduzieren und die Seitenladezeiten verbessern?**

Wenn [!DNL Audience Manager] in Ihren Drittdatenpartner integriert ist, können Sie dessen Pixel und Tags durch einen Server-zu-Server-ID-Aufruf an [!DNL Audience Manager] ersetzen. In diesem Fall würde [!DNL Audience Manager] einen einzelnen ID-Aufruf auslösen, wenn wir einen Benutzer zum ersten Mal sehen, und diese Informationen mit Ihrem Partner synchronisieren. Dadurch entfällt die Notwendigkeit, von jeder Seite mehrere Pixel aufzurufen. Die Reduzierung von Pixelaufrufen kann die Seitenladezeit verbessern.

 

**Ich habe einen Daten-Feed abonniert. Wo werden diese Daten gespeichert?**

Ihr Daten-Feed und alle im Feed enthaltenen Eigenschaften werden als Unterordner und Eigenschaften in [!DNL Audience Manager] angezeigt. Gehen Sie zu **[!UICONTROL Audience Data > Traits]** und erweitern Sie den Ordner [!UICONTROL 3rd-Party Data], um Ihre Eigenschaften anzuzeigen oder Segmente und Modelle mit diesen Daten zu erstellen.

 

**Was ist [!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager verwendete [!UICONTROL Tag Insertion Manager] (TIM) zum Erstellen und Verwalten von [!UICONTROL data collection code (DIL)]. Diese Funktion ist mittlerweile veraltet und wurde zuerst durch [!UICONTROL Dynamic Tag Manager (DTM)] und später durch [!DNL Adobe Experience Platform Launch] ersetzt. Weitere Informationen finden Sie unter [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html).

 

**Was sind die Unterschiede zwischen algorithmischen Modellen und Eigenschaftsempfehlungen? Wann sollte ich jede dieser Funktionen verwenden?**

**Algorithmische Modelle**

Algorithmische Modelle finden nicht nur die einflussreichsten Eigenschaften, sondern bewerten Benutzer auch anhand dieser Eigenschaften und weisen jedem Benutzer eine individuelle Bewertung zu. Anschließend erstellen Sie algorithmische Eigenschaften, um Ihre Benutzer anzusprechen. Mit den Genauigkeits- und Reichweitenkontrollen in Trait Builder können Sie festlegen, welche Benutzer unter all denjenigen, die über die einflussreichen Eigenschaften verfügen, Sie ins Visier nehmen möchten.

Algorithmische Modelle ermöglichen es Ihnen, Benutzer mit unterschiedlichen Genauigkeitsstufen auszuwählen und in Audience Lab zu testen, welche Benutzergruppe besser konvertiert. Weitere Informationen finden Sie im detaillierten Anwendungsfall unter [Vergleichen von Modellen in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

In algorithmischen Modellen läuft das Modell alle 8 Tage und aktualisiert die für algorithmische Eigenschaften qualifizierten Benutzer.

**Eigenschaftenempfehlungen**

Mit den Eigenschaftenempfehlungen erhalten Sie schnell Einblicke in andere Eigenschaften, die denen ähnlich sind, die Sie in einem Segment verwenden.

Sie sollten Eigenschaftsempfehlungen in folgenden Fällen verwenden:

* Sie benötigen schnelle Einblicke beim Erstellen eines Segments.
* Sie verwenden die Segmente für kurze Kampagnen oder wenn Sie schnell konvertierende Zielgruppen unterdrücken möchten.
* Sie versuchen, die Reichweite zu maximieren.

 

**Gibt es einen Unterschied zwischen Adobe Analytics- und Audience Manager-Segmenten?**

Ja. Eine ausführliche Beschreibung der Unterschiede finden Sie unter [Grundlegendes zu Segmenten in Analytics und Audience Manager](https://docs.adobe.com/content/help/de-DE/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

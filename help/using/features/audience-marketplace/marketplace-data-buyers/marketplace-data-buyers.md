---
description: Übersicht und Workflow für Datenkäufer, die Daten von Drittanbietern aus Audience Manager erwerben möchten
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: Audience Marketplace für Datenkäufer
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 1%

---

# [!UICONTROL Audience Marketplace] für Datenkäufer {#audience-marketplace-for-data-buyers}

Übersicht und Workflow für Datenkäufer, die Daten von Drittanbietern innerhalb von [!DNL Audience Manager] kaufen möchten.

>[!NOTE]
>[ Rollenbasierte Berechtigungen](../../../reporting/reports-dashboard.md) steuern den Zugriff auf Funktionen von [!UICONTROL Audience Marketplace].
>
>* Administratoren können Daten-Feeds erstellen, Abonnenten verwalten und Daten-Feeds abonnieren.
>* Benutzer können nur Feeds suchen und anzeigen.

## Die [!UICONTROL Marketplace]: Info {#about-marketplace}

Die [!UICONTROL Marketplace] ist eine [!DNL Audience Manager]-Funktion für Datenkäufer, die Daten-Feeds auflistet, die Sie abonnieren können. Er listet pauschale, [!DNL CPM] und private Daten-Feeds auf. Diese Feeds werden von Drittanbietern bereitgestellt, die [!DNL Audience Manager] zum Verkauf von Daten verwenden.

Mit den Berichterstellungs-Tools im Bereich [!UICONTROL Marketplace] können Sie die Feed-Nutzung und die Überschneidung zwischen Ihrem [!UICONTROL traits] und den in einem abonnierten Daten-Feed vorhandenen nachverfolgen. Mit [!UICONTROL Audience Marketplace] kümmert sich [!DNL Adobe] schließlich um Rechnungen und Honorarzahlungen (obwohl Sie die Nutzung selbst melden müssen, wenn Sie einen [!DNL CPM] -Feed abonniert haben). Mit diesen Funktionen können Sie effektive Datenquellen finden, ohne Zeit für die Suche nach einem Datenanbieter zu verschwenden.

>[!TIP]
>
>Verwenden Sie den **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)**, um hochwertige Daten-Feeds zu finden, die Sie abonnieren können. Gehen Sie dann zurück zur Benutzeroberfläche von [!DNL Audience Manager] oder verwenden Sie die [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) , um die gefundenen Feeds zu abonnieren.

![Käufermarketplace-overview](assets/buyer-marketplace-overview.png)

Die Liste [!UICONTROL Marketplace] enthält Informationen, die Sie sortieren und suchen können, um den für Sie geeigneten Daten-Feed zu finden. Die Artikel in der Liste der [!UICONTROL Marketplace] Käufer umfassen:

* **[!UICONTROL Search]**: Suchen Sie nach Daten-Feeds nach Namen oder Textbeschreibung.
* **[!UICONTROL Similar Traits]**: Zeigt die Anzahl ähnlicher [!UICONTROL traits] aus einem Daten-Feed an. Diese Spalte wird angezeigt, nachdem Sie einen [!UICONTROL trait] oder [!UICONTROL segment] eingegeben haben, nach dem im Abschnitt **[!UICONTROL Similarity To]** gefiltert werden soll.
* **[!UICONTROL Name]**: Name des Daten-Feeds.
* **[!UICONTROL Description]**: Informationen zum Inhalt eines Daten-Feeds.
* **[!UICONTROL Provider]**: Name des Datenanbieters
* **[!UICONTROL Traits]**: Die Anzahl von [!UICONTROL traits] in einem Daten-Feed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Die Anzahl der Unique Users, die in den letzten 30 Tagen gesehen wurden.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Die Anzahl der Benutzer in Ihrem Konto, die sich mit den Benutzern im Konto des Anbieters überschneiden.
* **[!UICONTROL Feed Overlap]**: Der Wert für die 30 Tage überlappenden eindeutigen Werte, der in Prozentsätzen angezeigt wird, berechnet als: 30-tägige Datenkäufer-Eindeutigkeit (30-tägige Eindeutigkeit) x 100.
* **[!UICONTROL Private Feeds]**: Siehe [Private Daten-Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Die Anzahl der Abonnements, die Sie für einen Datenanbieter haben.

 

Verwenden Sie die folgenden Filter auf der linken Seite der Seite &quot;[!UICONTROL Marketplace]&quot;, um die besten Daten-Feeds für Ihre Anforderungen zu finden:

* **[!UICONTROL Similarity To]**: Filtern Sie Daten-Feeds basierend auf ihrer Ähnlichkeit mit einem [!UICONTROL trait] oder einem [!UICONTROL segment] Ihrer Wahl. Beim Eingeben des [!UICONTROL trait] oder Segments, mit dem Sie vergleichen möchten, können Sie die [!UICONTROL trait] - oder [!UICONTROL segment] -ID oder ihre jeweiligen Namen verwenden.
* **[!UICONTROL Similarity Cutoff]**: Ziehen Sie den Schieberegler, um die Daten-Feeds danach zu filtern, wie ähnlich ihre [!UICONTROL traits] Ihrem ausgewählten [!UICONTROL trait] oder [!UICONTROL segment] sind. Weitere Informationen zu [!UICONTROL trait] Ähnlichkeitswerten finden Sie unter [Wert für die Ähnlichkeitsbewertung von Eigenschaften](../../segments/trait-recommendations.md#trait-similarity-score) .
* **[!UICONTROL Subscription Status]**: Filtern Sie die Daten-Feeds nach Ihrem Abonnementstatus.
* **[!UICONTROL Plan Use Case]**: Filtern Sie Daten-Feeds anhand der unterstützten Anwendungsfälle: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** und **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtern Sie Daten-Feeds nach ihrem Preistyp.

## Suchen ähnlicher [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] gibt Ihnen die Möglichkeit, [!UICONTROL traits] aus verschiedenen Daten-Feeds zu finden, basierend auf ihrer Ähnlichkeit mit Ihren vorhandenen [!UICONTROL traits] oder Segmenten. Gehen Sie dazu folgendermaßen vor:

1. Gehen Sie zu **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Verwenden Sie den &quot;**[!UICONTROL Similarity To]**&quot;-Selektor, um zwischen der Filterung anhand eines &quot;[!UICONTROL trait]&quot; oder &quot;[!UICONTROL segment]&quot; zu wählen. Sie können nach [!UICONTROL trait]/[!UICONTROL segment] ID oder Name filtern. Das Suchfeld zeigt Ihnen automatisch relevante Vorschläge basierend auf Ihrer Eingabe an.
3. Nachdem Sie die Eigenschaft oder das Segment identifiziert haben, nach der/dem Sie filtern möchten, klicken Sie in der Liste mit Vorschlägen auf sie.
4. Verwenden Sie zum Eingrenzen der Ergebnisse den Regler **[!UICONTROL Similarity Cutoff]** , um von weniger ähnlichen [!UICONTROL traits] zu ähnlichen zu wechseln.

Nach Abschluss der Filterung wird auf der Ergebnisseite eine neue Spalte angezeigt: **[!UICONTROL Similar Traits]**. In dieser Spalte wird die Anzahl der [!UICONTROL traits] angezeigt, die der von Ihnen gefilterten ähnelt. Sie wird aus jedem Daten-Feed ermittelt, der die Filterkriterien erfüllt.

Um die vollständige Liste ähnlicher Eigenschaften anzuzeigen, klicken Sie auf die Zahl in der Spalte **[!UICONTROL Similar Traits]** .

>[!NOTE]
>
> Audience Marketplace zeigt die 500 beliebtesten ähnlichen [!UICONTROL trait] Ergebnisse aus allen Daten-Feeds an.

Sehen Sie sich das Video unten an, um einen vollständigen Überblick darüber zu erhalten, wie Sie ähnliche [!UICONTROL traits] finden.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## private Datenfeeds {#private-data-feeds}

In der Liste [!UICONTROL Marketplace] werden manchmal der Name des Providers und [!UICONTROL trait] Daten als privat markiert. Dies zeigt einen [privaten Datenfeed](../../../features/audience-marketplace/marketplace-private-feeds.md) an. Mit einem privaten Daten-Feed können Verkäufer den Zugriff von Käufern auf ihre Daten einschränken. Verkäufer können Feeds privat machen, wenn sie spezielle Angebote, Rabatte anbieten oder wenn Privatsphäre und Zugriffskontrolle für sie wichtig sind. Als Käufer müssen Sie eine Abonnement-Anfrage an den Verkäufer senden, wenn Sie Zugriff auf einen privaten Feed wünschen. Weitere Informationen finden Sie unter [Abonnieren eines privaten Daten-Feeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) .

>[!MORELIKETHIS]
>
>* [Grundlegendes zur Abo-Detailseite im Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatte für Datenkäufer](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

---
description: Übersicht und Workflow für Datenkäufer, die Daten von Drittanbietern aus Audience Manager erwerben möchten
seo-description: Übersicht und Workflow für Datenkäufer, die Daten von Drittanbietern aus Audience Manager erwerben möchten
seo-title: Audience Marketplace für Datenkäufer
solution: Audience Manager
title: Audience Marketplace für Datenkäufer
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 3%

---

# [!UICONTROL Audience Marketplace] für Datenkäufer  {#audience-marketplace-for-data-buyers}

Übersicht und Workflow für Datenkäufer, die Daten von Drittanbietern über [!DNL Audience Manager] erwerben möchten.

>[!NOTE]
>[Rollenbasierte Berechtigungen](../../../reporting/reports-dashboard.md) steuern den Zugriff auf [!UICONTROL Audience Marketplace]-Funktionen.
>
>* Administratoren können Daten-Feeds erstellen, Abonnenten verwalten und Daten-Feeds abonnieren.
>* Benutzer können nur Feeds suchen und anzeigen.


## Die [!UICONTROL Marketplace]: Über {#about-marketplace}

Die [!UICONTROL Marketplace] ist eine [!DNL Audience Manager]-Funktion für Datenkäufer, die Daten-Feeds auflistet, die Sie abonnieren können. Er listet pauschale, [!DNL CPM] und private Daten-Feeds auf. Diese Feeds werden von Drittanbietern bereitgestellt, die [!DNL Audience Manager] verwenden, um Daten zu verkaufen.

Mit den Reporting-Tools von [!UICONTROL Marketplace] können Sie die Feed-Nutzung und die Überschneidung zwischen [!UICONTROL traits] und den in einem abonnierten Daten-Feed vorhandenen nachverfolgen. Mit [!UICONTROL Audience Marketplace] übernimmt [!DNL Adobe] schließlich Rechnungen und Gebührenzahlungen (obwohl Sie die Nutzung selbst melden müssen, wenn Sie einen [!DNL CPM]-Feed abonniert haben). Mit diesen Funktionen können Sie effektive Datenquellen finden, ohne Zeit für die Suche nach einem Datenanbieter zu verschwenden.

>[!TIP]
>
>Verwenden Sie den **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)**, um hochwertige Daten-Feeds zu finden, die Sie abonnieren können. Gehen Sie dann zurück zur [!DNL Audience Manager]-Benutzeroberfläche oder verwenden Sie die [Audience Marketplace Buyer-API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API), um die gefundenen Feeds zu abonnieren.

![Buyer-Marketplace-overview](assets/buyer-marketplace-overview.png)

Die Liste [!UICONTROL Marketplace] enthält Informationen, die Sie sortieren und suchen können, um den für Sie geeigneten Daten-Feed zu finden. Zu den Artikeln in der Liste [!UICONTROL Marketplace] des Käufers gehören:

* **[!UICONTROL Search]**: Suchen Sie nach Daten-Feeds nach Name oder Textbeschreibung.
* **[!UICONTROL Similar Traits]**: Zeigt die Anzahl der ähnlichen Daten  [!UICONTROL traits] aus einem Daten-Feed an. Diese Spalte wird angezeigt, nachdem Sie einen [!UICONTROL trait] oder [!UICONTROL segment] eingeben, nach dem im Abschnitt **[!UICONTROL Similarity To]** gefiltert werden soll.
* **[!UICONTROL Name]**: Name des Daten-Feeds.
* **[!UICONTROL Description]**: Informationen zum Inhalt eines Daten-Feeds.
* **[!UICONTROL Provider]**: Name des Datenanbieters.
* **[!UICONTROL Traits]**: Die Anzahl der  [!UICONTROL traits] in einem Daten-Feed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Die Anzahl der Unique Users, die in den letzten 30 Tagen gesehen wurden.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Die Anzahl der Benutzer in Ihrem Konto, die sich mit den Benutzern im Konto des Anbieters überschneiden.
* **[!UICONTROL Feed Overlap]**: Der Wert der eindeutigen 30 Tage, der in Prozent angezeigt wird, wurde wie folgt berechnet: Data Buyer 30 Tage überlagerte eindeutiger Titel / Data Buyer 30 Tage (Individuelle Daten) x 100.
* **[!UICONTROL Private Feeds]**: Siehe  [Private Daten-Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Die Anzahl der Abonnements, die Sie bei einem Datenanbieter haben.

 

Verwenden Sie die folgenden Filter auf der linken Seite der Seite [!UICONTROL Marketplace] , um die besten Daten-Feeds für Ihre Anforderungen zu finden:

* **[!UICONTROL Similarity To]**: Filtern Sie Daten-Feeds anhand ihrer Ähnlichkeit mit einem  [!UICONTROL trait] oder  [!UICONTROL segment] Ihrer Wahl. Bei der Eingabe von [!UICONTROL trait] oder Segment, mit dem Sie vergleichen möchten, können Sie die ID [!UICONTROL trait] oder [!UICONTROL segment] oder deren Namen verwenden.
* **[!UICONTROL Similarity Cutoff]**: Ziehen Sie den Schieberegler, um die Daten-Feeds danach zu filtern, wie ähnlich sie  [!UICONTROL traits] Ihrer ausgewählten  [!UICONTROL trait] oder  [!UICONTROL segment]sind. Weitere Informationen zu [!UICONTROL trait]-Ähnlichkeitswerten finden Sie unter [Wert der Eigenschaftsähnlichkeit](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtern Sie die Daten-Feeds nach Ihrem Abonnementstatus.
* **[!UICONTROL Plan Use Case]**: Filtern von Daten-Feeds anhand der unterstützten Anwendungsfälle:  **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]** und  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtern von Daten-Feeds nach ihrem Preistyp.

## Ähnliches finden [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] bietet Ihnen die Möglichkeit, basierend auf der Ähnlichkeit  [!UICONTROL traits] Ihrer vorhandenen  [!UICONTROL traits] oder Segmente aus verschiedenen Daten-Feeds zu suchen. Gehen Sie wie folgt vor:

1. Gehen Sie zu **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Verwenden Sie den Selektor **[!UICONTROL Similarity To]**, um zwischen Filtern nach [!UICONTROL trait] oder [!UICONTROL segment] zu wählen. Sie können nach [!UICONTROL trait]/[!UICONTROL segment] ID oder Name filtern. Das Suchfeld zeigt Ihnen automatisch relevante Vorschläge basierend auf Ihrer Eingabe an.
3. Nachdem Sie die Eigenschaft oder das Segment identifiziert haben, nach der/dem Sie filtern möchten, klicken Sie in der Liste mit Vorschlägen auf sie.
4. Verwenden Sie zum Eingrenzen der Ergebnisse den Regler **[!UICONTROL Similarity Cutoff]** , um von weniger ähnlichen [!UICONTROL traits] zu ähnlichen zu wechseln.

Nach Abschluss der Filterung wird auf der Ergebnisseite eine neue Spalte angezeigt: **[!UICONTROL Similar Traits]**. Diese Spalte zeigt die Anzahl der [!UICONTROL traits], die der von Ihnen gefilterten ähnelt, von jedem Datenfeed, der die Filterkriterien erfüllt.

Um die vollständige Liste ähnlicher Eigenschaften anzuzeigen, klicken Sie auf die Zahl in der Spalte **[!UICONTROL Similar Traits]** .

>[!NOTE]
>
> Audience Marketplace zeigt die 500 wichtigsten ähnlichen [!UICONTROL trait]-Ergebnisse aus allen Daten-Feeds an.

Sehen Sie sich das Video unten an, um einen vollständigen Überblick darüber zu erhalten, wie Sie ähnliche [!UICONTROL traits] finden.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Private Daten-Feeds {#private-data-feeds}

In der Liste [!UICONTROL Marketplace] werden manchmal der Name des Anbieters und die [!UICONTROL trait]-Daten als privat markiert. Dies zeigt einen [privaten Daten-Feed](../../../features/audience-marketplace/marketplace-private-feeds.md) an. Mit einem privaten Daten-Feed können Verkäufer den Zugriff von Käufern auf ihre Daten einschränken. Verkäufer können Feeds privat machen, wenn sie spezielle Angebote, Rabatte anbieten oder wenn Privatsphäre und Zugriffskontrolle für sie wichtig sind. Als Käufer müssen Sie eine Abonnement-Anfrage an den Verkäufer senden, wenn Sie Zugriff auf einen privaten Feed wünschen. Weitere Informationen finden Sie unter [Abonnieren eines privaten Daten-Feeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) .

>[!MORELIKETHIS]
>
>* [Grundlegendes zur Abo-Detailseite im Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
* [Rabatte für Datenkäufer](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)


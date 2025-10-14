---
description: Übersicht und Workflow für Datenkäufer, die Daten von Drittanbietern über Audience Manager erwerben möchten
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

Übersicht und Workflow für Datenkäufer, die Daten von Drittanbietern aus [!DNL Audience Manager] erwerben möchten.

>[!NOTE]
>[Rollenbasierte Berechtigungen](../../../reporting/reports-dashboard.md) steuern den Zugriff auf [!UICONTROL Audience Marketplace] Funktionen.
>
>* Administratoren können Daten-Feeds erstellen, Abonnenten verwalten und Daten-Feeds abonnieren.
>* Benutzer können nur Feeds suchen und anzeigen.

## Die [!UICONTROL Marketplace]: Über {#about-marketplace}

Die [!UICONTROL Marketplace] ist eine [!DNL Audience Manager] Funktion für Datenerwerber, in der Daten-Feeds aufgelistet sind, die Sie abonnieren können. Es werden Flatrate-, [!DNL CPM]- und private Daten-Feeds aufgelistet. Diese Feeds werden von Drittanbietern bereitgestellt, die [!DNL Audience Manager] zum Verkauf von Daten verwenden.

In der [!UICONTROL Marketplace] können Sie mit Reporting-Tools die Feed-Nutzung und die Überschneidung zwischen Ihren [!UICONTROL traits] und denen in einem abonnierten Daten-Feed verfolgen. Schließlich kümmert sich [!UICONTROL Audience Marketplace] bei [!DNL Adobe] um Rechnungen und Gebührenzahlungen (obwohl Sie die Nutzung eines [!DNL CPM] Feeds selbst melden müssen). Mit diesen Funktionen können Sie effektive Datenquellen finden, ohne Zeit mit der Suche nach einem Datenanbieter zu verlieren.

>[!TIP]
>
>Verwenden Sie den **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** um qualitativ hochwertige Daten-Feeds zu finden, die Sie abonnieren können. Kehren Sie dann zur [!DNL Audience Manager]-Benutzeroberfläche zurück oder verwenden Sie die [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) um die gefundenen Feeds zu abonnieren.

![Einkäufer-Marktplatz-Übersicht](assets/buyer-marketplace-overview.png)

Die [!UICONTROL Marketplace] enthält Informationen, die Sie sortieren und suchen können, um den für Sie geeigneten Daten-Feed zu finden. Zu den Elementen in der Liste des [!UICONTROL Marketplace]-Käufers gehören:

* **[!UICONTROL Search]**: Daten-Feeds nach Name oder Textbeschreibung suchen.
* **[!UICONTROL Similar Traits]**: Zeigt die Anzahl ähnlicher [!UICONTROL traits] aus einem Daten-Feed an. Diese Spalte wird angezeigt, nachdem Sie im Abschnitt [!UICONTROL trait] einen [!UICONTROL segment] oder eine **[!UICONTROL Similarity To]** zum Filtern eingegeben haben.
* **[!UICONTROL Name]**: Name des Daten-Feeds.
* **[!UICONTROL Description]**: Informationen zum Inhalt eines Daten-Feeds.
* **[!UICONTROL Provider]**: Name des Datenanbieters.
* **[!UICONTROL Traits]**: Die Anzahl der [!UICONTROL traits] in einem Daten-Feed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Die Anzahl der eindeutigen Benutzer, die in den letzten 30 Tagen angezeigt wurden.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Die Anzahl der Benutzerinnen und Benutzer in Ihrem Konto, die sich mit den Benutzerinnen und Benutzern im Konto des Anbieters überschneiden.
* **[!UICONTROL Feed Overlap]**: Der eindeutige Wert mit Überschneidung von 30 Tagen, angezeigt in Prozentsätzen, berechnet als: Dateneinkäufer 30 Tage Überschneidung / Dateneinkäufer 30 Tage (eindeutige) x 100.
* **[!UICONTROL Private Feeds]**: Siehe [Private Daten-Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Die Anzahl der Abonnements, die Sie bei einem Datenanbieter haben.

 

Verwenden Sie die folgenden Filter auf der linken Seite der [!UICONTROL Marketplace], um ganz einfach die besten Daten-Feeds für Ihre Anforderungen zu finden:

* **[!UICONTROL Similarity To]**: Filtern Sie Daten-Feeds nach ihrer Ähnlichkeit mit einem [!UICONTROL trait] oder einer [!UICONTROL segment] Ihrer Wahl. Beim Eingeben des zu vergleichenden [!UICONTROL trait] oder Segments können Sie die [!UICONTROL trait]- oder [!UICONTROL segment]-ID oder die entsprechenden Namen verwenden.
* **[!UICONTROL Similarity Cutoff]**: Ziehen Sie den Schieberegler, um die Daten-Feeds danach zu filtern, wie ähnlich ihre [!UICONTROL traits] Ihren ausgewählten [!UICONTROL trait] oder [!UICONTROL segment] sind. Weitere Informationen zu [!UICONTROL trait] Ähnlichkeitswerten finden Sie unter [Eigenschaftenähnlichkeitswert](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtern Sie die Daten-Feeds nach Ihrem Abonnementstatus.
* **[!UICONTROL Plan Use Case]**: Filtern von Daten-Feeds auf der Grundlage ihrer unterstützten Anwendungsfälle: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** und **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtern Sie Daten-Feeds nach ihrem Preistyp.

## Suchen ähnlicher [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] bietet Ihnen die Möglichkeit, [!UICONTROL traits] aus verschiedenen Daten-Feeds zu finden, basierend auf ihrer Ähnlichkeit mit Ihren vorhandenen [!UICONTROL traits] oder Segmenten. Gehen Sie wie folgt vor:

1. Navigieren Sie zu **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Verwenden Sie den **[!UICONTROL Similarity To]**-Selektor, um zwischen der Filterung nach einem [!UICONTROL trait] oder einer [!UICONTROL segment] zu wählen. Sie können nach [!UICONTROL trait]/[!UICONTROL segment] ID oder Namen filtern. Das Suchfeld zeigt automatisch relevante Vorschläge basierend auf Ihrer Eingabe an.
3. Nachdem Sie das Merkmal oder Segment identifiziert haben, nach dem Sie filtern möchten, klicken Sie in der Liste mit den Vorschlägen darauf.
4. Um die Ergebnisse einzugrenzen, bewegen Sie mit dem Schieberegler **[!UICONTROL Similarity Cutoff]** von weniger ähnlichen [!UICONTROL traits] zu ähnlicheren.

Sobald die Filterung abgeschlossen ist, wird auf der Ergebnisseite eine neue Spalte angezeigt: **[!UICONTROL Similar Traits]**. In dieser Spalte wird die Anzahl der [!UICONTROL traits] angezeigt, die dem von Ihnen gefilterten in jedem Daten-Feed entspricht, der die Filterkriterien erfüllt.

Um die vollständige Liste der ähnlichen Eigenschaften anzuzeigen, klicken Sie auf die Zahl in der Spalte **[!UICONTROL Similar Traits]** .

>[!NOTE]
>
> Audience Marketplace zeigt die 500 wichtigsten ähnlichen [!UICONTROL trait] aus allen Daten-Feeds an.

Sehen Sie sich das folgende Video an, um einen vollständigen Überblick darüber zu erhalten, wie Sie ähnliche [!UICONTROL traits] finden.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## private Datenfeeds {#private-data-feeds}

In der [!UICONTROL Marketplace] Liste werden manchmal der Name und die [!UICONTROL trait] des Anbieters als privat markiert. Dies zeigt einen [privaten Daten-Feed](../../../features/audience-marketplace/marketplace-private-feeds.md) an. Mit einem privaten Daten-Feed können Verkäufer den Käuferzugriff auf ihre Daten einschränken. Verkäufer können Feeds privat machen, wenn sie Sonderangebote, Rabatte anbieten oder wenn Datenschutz und Zugriffskontrolle für sie wichtig sind. Als Käufer müssen Sie eine Abonnementanfrage an den Verkäufer senden, wenn Sie Zugriff auf einen privaten Feed wünschen. Weitere [&#x200B; finden Sie unter „Abonnieren &#x200B;](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) privaten Daten-Feeds“.

>[!MORELIKETHIS]
>
>* [Grundlegendes zur Abo-Detailseite im Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatte für Datenkäufer](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

---
description: Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern in Audience Manager erwerben möchten
seo-description: Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern in Audience Manager erwerben möchten
seo-title: Audience Marketplace für Datenkäufer
solution: Audience Manager
title: Audience Marketplace für Datenkäufer
topic: DIL-API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Audience Marketplace für Datenkäufer {#audience-marketplace-for-data-buyers}

Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern von innerhalb [!DNL Audience Manager]der Website erwerben möchten.

>[!NOTE]
>[Rollenbasierte Berechtigungen](../../../reporting/reports-dashboard.md) steuern den Zugriff auf [!UICONTROL Audience Marketplace] Funktionen.
>
>* Administratoren können Datenfeeds erstellen, Abonnenten verwalten und Datenfeeds abonnieren.
>* Benutzer können nur Feeds suchen und anzeigen.


## Der Marktplatz: Info {#about-marketplace}

<!-- c_marketplace_about.xml -->

Das [!UICONTROL Marketplace] ist eine [!DNL Audience Manager] Funktion für Datenkäufer, die Datenfeeds auflistet, die Sie abonnieren können. Er listet pauschale [!DNL CPM]und private Datenfeeds auf. Diese Feeds werden von Drittanbietern bereitgestellt, die Daten [!DNL Audience Manager] zum Verkauf verwenden.

Mit den [!UICONTROL Marketplace]Berichterstellungstools können Sie die Nutzung von Feeds und die Überschneidung zwischen Ihren Eigenschaften und denen in einem abonnierten Data Feed verfolgen. Schließlich, mit [!UICONTROL Audience Marketplace]der [!DNL Adobe] kümmert sich um Rechnungen und Gebührenzahlungen (obwohl Sie die Nutzung selbst melden müssen, wenn Sie ein Feed abonniert [!DNL CPM] ). Mit diesen Funktionen können Sie effektive Datenquellen finden, ohne Zeit mit der Suche nach einem Datenanbieter zu verschwenden.

>[!TIP]
>
>Verwenden Sie den **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** , um hochwertige Datenfeeds zu finden, die Sie abonnieren können. Gehen Sie dann zurück zur Benutzeroberfläche von Audience Manager oder verwenden Sie die [Audience Marketplace-Käufer-API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) , um die von Ihnen gefundenen Feeds zu abonnieren.

![Käufermarktplatz-overview](assets/buyer-marketplace-overview.png)

Die [!UICONTROL Marketplace] Liste enthält Informationen, die Sie sortieren und suchen können, um den für Sie richtigen Datenfeed zu finden. Die Liste der [!UICONTROL Marketplace] Käufer enthält unter anderem:

* **[!UICONTROL Search]**: Suchen Sie nach Datenfeeds anhand des Namens oder der Textbeschreibung.
* **[!UICONTROL Similar Traits]**: Zeigt die Anzahl ähnlicher Eigenschaften aus einem Datenfeed an. Diese Spalte wird angezeigt, nachdem Sie eine Eigenschaft oder ein Segment eingegeben haben, nach der im **[!UICONTROL Similarity To]** Abschnitt gefiltert werden soll.
* **[!UICONTROL Name]**: Name des Datenfeeds.
* **[!UICONTROL Description]**: Informationen zum Inhalt eines Datenfeeds.
* **[!UICONTROL Provider]**: Name des Datenanbieters.
* **[!UICONTROL Traits]**: Die Anzahl der Eigenschaften in einem Datenfeed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Die Anzahl der Unique Users, die in den letzten 30 Tagen gesehen wurden.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Die Anzahl der Benutzer in Ihrem Konto, die sich mit den Benutzern im Konto des Anbieters überschneiden.
* **[!UICONTROL Feed Overlap]**: Der 30-Tage-Überschneidungswert für individuelle Werte, in Prozent angezeigt, berechnet als: Data Buffer 30 day überlappte Uniques / Data Buffer 30 day Uniques) x 100.
* **[!UICONTROL Private Feeds]**: Siehe [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Die Anzahl der Abonnements, die Sie bei einem Datenanbieter haben.

Verwenden Sie die folgenden Filter, die auf der linken Seite der [!UICONTROL Marketplace] Seite verfügbar sind, um die besten Datenfeeds für Ihre Anforderungen leicht zu finden:

* **[!UICONTROL Similarity To]**: Filtern Sie Datenfeeds basierend auf ihrer Ähnlichkeit mit einer Eigenschaft oder einem Segment Ihrer Wahl. Beim Eingeben der Eigenschaft oder des Segments, mit der bzw. dem Sie vergleichen möchten, können Sie die Eigenschaften- oder Segment-ID oder deren jeweilige Namen verwenden.
* **[!UICONTROL Similarity Cutoff]**: Ziehen Sie den Schieberegler, um die Datenfeeds nach der Ähnlichkeit ihrer Eigenschaften mit Ihrer ausgewählten Eigenschaft oder Ihrem Segment zu filtern.
* **[!UICONTROL Subscription Status]**: Filtern Sie die Datenfeeds nach Ihrem Abonnementstatus.
* **[!UICONTROL Plan Use Case]**: Filtern Sie Datenfeeds nach unterstützten Anwendungsfällen: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** und **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtern Sie Datenfeeds nach ihrem Preistyp.

Sehen Sie sich das folgende Video an, um einen Überblick über die Verwendung dieser Filter zu erhalten.

## Suchen ähnlicher Eigenschaften {#finding-similar-traits}

[!UICONTROL Audience Marketplace] gibt Ihnen die Möglichkeit, Eigenschaften aus verschiedenen Data Feeds zu suchen, die auf der Ähnlichkeit mit Ihren vorhandenen Eigenschaften oder Segmenten basieren. So geht das:

1. Gehen Sie zu **[!UICONTROL Audience Marketplace]** &gt; **[!UICONTROL Marketplace]**.
2. Verwenden Sie den **[!UICONTROL Similarity To]** Selektor, um zwischen der Filterung nach Eigenschaften oder Segmenten zu wählen. Sie können nach Eigenschaften-/Segment-ID oder Namen filtern. Das Suchfeld zeigt Ihnen anhand Ihrer Eingabe automatisch relevante Vorschläge an.
3. Nachdem Sie die Eigenschaft oder das Segment identifiziert haben, nach der Sie filtern möchten, klicken Sie in der Liste der Vorschläge darauf.
4. Um die Ergebnisse einzugrenzen, verwenden Sie den **[!UICONTROL Similarity Cutoff]** Schieberegler, um von weniger ähnlichen Eigenschaften zu ähnlichen Eigenschaften zu wechseln.

Nach Abschluss der Filterung wird eine neue Spalte auf der Ergebnisseite angezeigt: **[!UICONTROL Similar Traits]**. Diese Spalte zeigt Ihnen die Anzahl ähnlicher Eigenschaften, nach denen Sie gefiltert sind, aus jedem Datenfeed, der die Filterkriterien erfüllt.

Um die vollständige Liste ähnlicher Eigenschaften anzuzeigen, klicken Sie auf die Zahl in der **[!UICONTROL Similar Traits]** Spalte.

>[!NOTE]
>
> Audience Marketplace zeigt die 500 beliebtesten Ergebnisse ähnlicher Eigenschaften aus allen Datenfeeds an.

Sehen Sie sich das unten stehende Video an, um einen vollständigen Überblick darüber zu erhalten, wie ähnliche Eigenschaften gefunden werden können.

>[!VIDEO](https://video.tv.adobe.com/v/29370/?captions=ger)


## Private Daten-Feeds {#private-data-feeds}

In der [!UICONTROL Marketplace] Liste werden manchmal der Name und die Eigenschaften des Anbieters als privat gekennzeichnet. Dies zeigt einen [privaten Datenfeed](../../../features/audience-marketplace/marketplace-private-feeds.md)an. Mit einem privaten Datenfeed können Verkäufer den Zugriff auf ihre Daten einschränken. Verkäufer können Feeds privat gestalten, wenn sie spezielle Angebote, Rabatte oder Zugriffskontrollen anbieten. Als Käufer müssen Sie eine Abonnementanforderung an den Verkäufer senden, wenn Sie Zugriff auf einen privaten Feed haben möchten. Weitere Informationen finden Sie unter [Abonnieren eines privaten Datenfeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) .

>[!MORELIKETHIS]
>
>* [Grundlegendes zur Abo-Detailseite im Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatte für Datenkäufer](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)


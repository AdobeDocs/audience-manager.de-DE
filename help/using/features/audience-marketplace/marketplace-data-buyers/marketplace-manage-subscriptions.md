---
description: Der Marktplatz ist der Ort, an dem Datenkäufer recherchieren und öffentliche und private Datenfeeds abonnieren. Führen Sie die folgenden Schritte aus, um einen öffentlichen Datenfeed zu abonnieren.
seo-description: Der Marktplatz ist der Ort, an dem Datenkäufer recherchieren und öffentliche und private Datenfeeds abonnieren. Führen Sie die folgenden Schritte aus, um einen öffentlichen Datenfeed zu abonnieren.
seo-title: Verwalten von Daten-Feed-Abonnements
solution: Audience Manager
title: Verwalten von Daten-Feed-Abonnements
topic: DIL API
uuid: 7305adb6-cbb8-4430-8204-2243095c0ba5
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '2186'
ht-degree: 2%

---


# Verwalten von Daten-Feed-Abonnements {#manage-data-feed-subscriptions}

Im [!UICONTROL Marketplace] können Datenkäufer recherchieren und öffentliche und private Datenfeeds abonnieren. Führen Sie die folgenden Schritte aus, um einen öffentlichen Datenfeed zu abonnieren.

## Abonnieren eines öffentlichen Datenfeeds {#subscript-public-data-feed}

Im [!UICONTROL Marketplace] können Datenkäufer recherchieren und öffentliche und private Datenfeeds abonnieren. Führen Sie die folgenden Schritte aus, um einen öffentlichen Datenfeed zu abonnieren.

<!-- t_subscribe_feed.xml -->

So abonnieren Sie einen öffentlichen Datenfeed:

1. Gehen Sie zu **[!UICONTROL Audience Marketplace > Marketplace]**. Verwenden Sie die Suchfunktion oder durchsuchen Sie die Liste, um einen Datenfeed zu finden.

   ![abonnieren](assets/subscribe1.png)

1. Klicken Sie auf den Namen des zu verwendenden Datenfeeds. Dadurch wird die Seite [Plandetails](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details) für den ausgewählten Feed geöffnet.

   ![plan-details](assets/plan-details.png)

1. Wählen Sie in der Tabelle &quot;Abonnement&quot;eine Anwendungsszenario aus und:
   * Verschieben Sie den Schieberegler **[!UICONTROL Subscription]** nach **[!UICONTROL On]**.
   * Klicken **[!UICONTROL Review & Subscribe]**. Dadurch wird das Fenster [!UICONTROL Terms and Conditions] geöffnet.

   ![abonnieren](assets/subscribe3.png)

1. Im Fenster [!UICONTROL Terms and Conditions]:

   * **Wichtig:** Lassen Sie das  **[!UICONTROL ID sync]** Kontrollkästchen aktiviert. Diese Einstellung hilft, die Übereinstimmungsraten mit Ihrem Datenanbieter zu verbessern.
   * Markieren Sie das Feld &quot;Geschäftsbedingungen&quot;und klicken Sie auf **[!UICONTROL Accept]**, um den Abonnement abzuschließen.

   ![abonnieren](assets/subscribe4.png)

### Nächste Schritte

Nachdem Sie einen Datenfeed abonniert haben:

* Überprüfen Sie das Abonnement, indem Sie den Ordner [!UICONTROL Traits] überprüfen. Siehe [Datenspeicherung für abonnierte Data Feeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee).

* Lesen Sie die Dokumentation zur Rechnungsstellung und zur Zahlung. Siehe die entsprechenden Links unten.

### Best Practices {#best-practices}

Im Folgenden finden Sie eine Reihe Best Practices, die Sie beim Arbeiten mit [!UICONTROL Audience Marketplace] befolgen sollten:

Wenn Sie neue Drittanbieter- und Zweitanbieter-Datensätze über [!UICONTROL Audience Marketplace] erkunden, empfehlen wir zunächst, Datenfeeds für [!UICONTROL Segments & Overlap] zu aktivieren. Auf diese Weise können Benutzer Daten untersuchen, indem sie Segmente erstellen, um die Größe der Audience zu bewerten, und Überschneidungsberichte ausführen, um Einblicke in die Audience zu erhalten. Bei den meisten Datenanbietern ist dieser Anwendungsfall kostenlos Angebot, sodass Sie diese Analyse ohne zusätzliche Kosten durchführen können.

Befolgen Sie beim Ausführen von Überschneidungsberichten die folgenden Best Practices, um sicherzustellen, dass Sie nützliche Ergebnisse erhalten.

1. Stellen Sie sicher, dass Ihre sich überlappenden Datensätze hinsichtlich Datentyp und Erfassungsmethoden ähnlich sind, z. B.:
   * Geografischer Besucher
   * Cookie im Vergleich zu mobilen IDs
   * Lookback-Fenster
   * Offline- oder Online-Aktivität
   * Die Häufigkeit, mit der der Datenanbieter die Daten aktualisiert

1. Überschneidungen können im Laufe der Zeit leicht zunehmen. Stellen Sie daher sicher, dass bis zu 30 Tage vergehen, bevor Sie Überschneidungsberichte ausführen, damit die Daten synchronisiert werden können.
1. Die Überschneidung kann zunehmen, wenn Sie Daten eines Datenanbieters in mehreren Marketing-Kampagnen verwenden.
und Initiativen. Dadurch erhalten Benutzer aus den beiden Datensätzen mehr Möglichkeiten zum Synchronisieren.
1. Es gibt keine Garantie dafür, dass sich Ihre Datensätze überschneiden. Damit eine Überschneidung gültig ist, muss ein Benutzer aus dem Kundendatensatz mit den Daten verknüpft werden
Anbieterdaten, die während des Zeitrahmens des Berichte eingestellt werden. Wenn die Mediendaten des Kunden nicht an die Benutzer im Datensatz des Datenanbieters gesendet wurden, gibt es keine Überschneidung.
1. Denke nicht an niedrige Überschneidungen. Profitieren Sie von einer geringen Überschneidung beim Potenzieller Kunde und binden Sie neue Benutzer ein.

## Abonnieren eines privaten Datenfeeds {#subscript-private-data-feed}

Käufer abonnieren private Datenfeeds und Pläne in **[!UICONTROL Audience Marketplace > Marketplace]**.

<!-- t_private_feed.xml -->

>[!TIP]
>
>Manchmal kann es vorkommen, dass Datenanbieter einen Rabatt auf einen privaten Datenfeed Angebot haben. Möglicherweise möchten Sie beim Senden Ihrer Abonnement-Anfrage nach einem Rabatt fragen.

So abonnieren Sie einen privaten Datenfeed:

1. Klicken Sie auf den Datenfeed-Namen in [!UICONTROL Marketplace].
1. Klicken **[!UICONTROL Request Access]**. Dadurch wird das Dialogfeld &quot;Anforderung&quot;geöffnet.
1. Schreiben Sie im Dialogfeld &quot;Anforderung&quot;einen Hinweis, der Ihr Interesse an ihrem Datenfeed zum Ausdruck bringt, und klicken Sie auf **[!UICONTROL Send]**. Der Verkäufer wird Ihre Nachricht überprüfen und Ihre Anfrage genehmigen oder ablehnen. Während Sie auf die Genehmigung warten, wird in der [!UICONTROL Marketplace]-Liste für diesen Datenfeed &quot;Angefordert&quot;angezeigt.

   * **[!UICONTROL Request approved]**: Der Status in der  [!UICONTROL Marketplace] Liste ändert sich in &quot;Zugriff gewährt&quot; und Sie erhalten eine automatische Benachrichtigung. An dieser Stelle können Sie den Feed abonnieren. Anweisungen finden Sie unter [Abonnieren eines öffentlichen Datenfeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed).
   * **[!UICONTROL Request denied]**: Der Text &quot;Angefordert&quot;wird aus der  [!UICONTROL Marketplace] Liste für den Feed entfernt. Sie können versuchen, ein Abonnement erneut zu erwerben oder einen anderen Feed auszuwählen.

## Data Feed-Rabatte für Käufer {#buyer-discount}

In [!UICONTROL Audience Marketplace] können Anbieter Angebot-Käufern einen Rabatt auf den veröffentlichten Preis eines [!DNL CPM]- oder pauschalen Datenfeeds gewähren. Abzinsungsbeträge sind jedoch für Käufer in der Feed-Liste [!DNL Marketplace] nicht sichtbar. Sie können jedoch auch einen Rabatt beantragen, wenn Sie einen privaten Datenfeed abonnieren oder weitere Informationen zu einem bestimmten Feed anfordern.

## Rabatt {#request-discount} anfordern

<!-- marketplace-buyer-discounts.xml -->

<table id="table_3C6E58F593BA48EC89ACBD9A26E4E74F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Käuferstatus </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Aktuelle Abonnenten</b> </p> </td> 
   <td colname="col2"> <p>Wenn Sie bereits einen privaten Data Feed abonniert haben und einen Rabatt anfordern möchten: </p> 
    <ol id="ol_A58D419EBB9349E9B1225202535130F6"> 
     <li id="li_D0DDC8AC6E9C4675AA4630D63FE8F071"> <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe"> Rückgängigmachen </a> des Abonnements für den Datenfeed. </li> 
     <li id="li_05A5379F2A944FB28AB39C196DDE3A1D">Wenden Sie sich an den Datenanbieter und fordern Sie einen ermäßigten Preis an. </li> 
     <li id="li_B1B5AA6F6CC64512A02D5E8861A5F266">Wenn der Anbieter Ihnen einen Rabatt gewährt, abonnieren Sie den Feed am Tag 1<sup>st</sup> des nächsten Monats erneut. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Neue private Datenfeed-Abonnenten</b> </p> </td> 
   <td colname="col2"> <p>Fordern Sie einen Rabatt in Ihrem Abonnement an. Siehe <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed"> Einen privaten Datenfeed abonnieren</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Potenzielle Abonnenten</b> </p> </td> 
   <td colname="col2"> <p>Ein <a href="../../../features/audience-marketplace/marketplace-private-feeds.md"> potenzieller Abonnent</a> ist ein Datenkäufer, der Zugriff auf einen privaten Datenfeed beantragt hat, die Zustimmung des Verkäufers erhalten hat, den Feed jedoch nicht abonniert hat. So fordern Sie einen Rabatt als potenziellen Abonnenten an: </p> 
    <ol id="ol_9CECDA92E7894B20AC8A777D78962188"> 
     <li id="li_618B64160CF24549AFCA73E006DCA35A">Gehen Sie zu <b><span class="uicontrol"> Audience Marketplace &gt; Marketplace</span></b>. </li> 
     <li id="li_FE52A06B30FC4858B48AF81954365FE9">Klicken Sie auf den Namen des Feeds, für den Sie genehmigt wurden. </li> 
     <li id="li_763C050AC9464BE380D00F6085B6E540">Klicken Sie auf <b><span class="uicontrol"> Weitere Details anfordern</span></b>. Fordern Sie einen Rabatt in Ihrer Anfrage an den Verkäufer. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## Überprüfen Sie die diskontierten Feeds {#review-discounted-feeds}

So überprüfen Sie Ihre vergünstigten Feeds:

1. Gehen Sie zu **[!UICONTROL Audience Marketplace > Marketplace]**.
1. Klicken Sie auf den Namen eines Feeds, den Sie bereits abonniert haben.
1. Sehen Sie sich die Spalten [!UICONTROL Price] und [!UICONTROL Your Price] in der Tabelle [!UICONTROL Plan Details] an. Wenn der Feed abgezinst wird:

   * Der ursprüngliche Preis ist mit einer roten Linie markiert.
   * Die Gebühr in der Spalte [!UICONTROL Your Price] ist niedriger als die Gebühr in der Spalte [!UICONTROL Price].

In diesem Beispiel erhält der Käufer einen Rabatt von 10 % auf den [!UICONTROL Segments and Overlap]-Plan in **[!UICONTROL Software Audience Feed]**.

![](assets/buyer-discount.png)

## Abonnierte Feed-Daten suchen {#find-subscribed-data-fee}

Die Daten (Eigenschaften) für Ihre Datenfeeds werden in ihren eigenen Ordnern zur Datenspeicherung der Eigenschaften angezeigt. Wechseln Sie zu **[!UICONTROL Audience Data > Traits]** und erweitern Sie den Ordner **[!UICONTROL 3rd-Party Data]**, um Ansichten zu erstellen und mit den Eigenschaften in Ihren abonnierten Feeds zu arbeiten. Suchen Sie nach dem Unterordner, der nach Ihrem Datenanbieter benannt ist. Diese enthalten Ordner, die nach den vom Feed bereitgestellten Datenfeed- und Listen-Eigenschaften benannt sind.

<!-- marketplace-feed-storage.xml -->

![](assets/subscribe5.png)

## Abmelden von einem Datenfeed {#unsubscribe}

Datenkäufer melden sich von Datenfeeds und Plänen in **[!UICONTROL Audience Marketplace > Marketplace]** ab.

<!-- t_unsubscribe_feed.xml -->

So melden Sie sich von einem Datenfeed ab:

1. Klicken Sie auf den Datenfeed-Namen in [!UICONTROL Marketplace].
1. Suchen Sie im Abschnitt [!UICONTROL Use Case] den zu verwendenden Plan und verschieben Sie den Schieberegler **[!UICONTROL Subscription]** nach **[!UICONTROL Off]**.

## Deaktivierung des Datenfeeds: Warum dies geschieht und wie {#data-feed-deactivation-reasons} reagiert wird

In [!UICONTROL Audience Marketplace] können Datenanbieter den Zugriff auf Ihre abonnierten Data Feeds sperren. Sei nicht alarmiert, wenn dir das passiert! Wir haben dich abgedeckt. In diesem Abschnitt finden Sie Prozesse und Verfahren im Zusammenhang mit Deaktivierungen von Datenfeeds.

## Allgemeine Gründe für die Deaktivierung des Datenfeeds {#reasons-for-deactivation}

<!-- marketplace-subscriber-deactivated.xml -->

Es kann rätselhaft oder sogar verstörend sein, wenn ein Feed, den Sie abonnieren, abgeschaltet wird. Datenanbieter können einen Datenfeed jedoch aus verschiedenen Gründen deaktivieren. Einige häufige Gründe sind:

* **Rechnungsstellung:** Datenanbieter deaktivieren einen Feed, wenn Sie immer wieder mit Gebührenzahlungen verspätet sind oder Ihre Gebühren nicht bezahlen.
* **Feed-Aktualisierungen:** Datenanbieter müssen Feeds deaktivieren, wenn sie ihre Feed-Taxonomie- oder Kostenstrukturen aktualisieren.
* **Inaktive Käufer:** Datenanbieter behalten sich das Recht vor, Feeds zu deaktivieren, wenn Abonnenten über einen längeren Zeitraum keine Ausgaben anzeigen.
* **Inaktive Verkäufer:** Datenanbieter, die den Dienst verlassen,  [!UICONTROL Audience Marketplace] deaktivieren und löschen alle ihre Datenfeeds.

>[!TIP]
>
>Wenden Sie sich direkt an Ihren Datenanbieter, wenn Sie glauben, dass ein Datenfeed versehentlich deaktiviert wurde. Ihr [!DNL Adobe]-Berater kann Ihnen mit Kontaktinformationen oder zusätzlichen Support behilflich sein.

## Deaktivierungs-E-Mail {#deactivation-email}

Wenn ein Datenanbieter einen Ihrer Data Feeds deaktiviert, sendet [!DNL Audience Manager] eine E-Mail an die Benutzer Ihrer Firma, die über die Berechtigung [!UICONTROL Administrator] verfügen. Manchmal klassifizieren E-Mail-Filter diese Nachricht als Spam. Daher können Sie diese wichtige Benachrichtigung verpassen. Diese E-Mail enthält die folgenden Elemente, um Sie bei der Identifizierung der Deaktivierungsmeldung zu unterstützen:

* **Von:** Die Deaktivierungs-E-Mail stammt von  `aam-noreply@adobe.com`. Pro-Tipp: Antworten Sie nicht auf diese E-Mail.

* **Betreffzeile:** Abonnement zum  *Namen der Data Feed-* Hereien ist abgebrochen.

* **Anlagen:** Die E-Mail enthält eine Anlage mit dem Titel &quot;  `list-of-affected-entities-by-feed-revocation.csv`&quot;. Das ist eine verwirrte Art, zu sagen, dass die Anlage alle Eigenschaften, die im abgebrochenen Feed enthalten sind, Liste. Als Käufer von Daten sollten Sie diese Anlage lesen. Es hilft Ihnen, deaktivierte Eigenschaften aus Ihren Segmenten und [algorithmische Modelle](../../../features/algorithmic-models/understanding-models.md) zu finden und zu entfernen.

## Eigenschafts-Liste {#deactivation-trait-list} deaktiviert

Die Liste, die eine Deaktivierungs-E-Mail begleitet, enthält die folgenden Felder.

<table id="table_5C3800F9D8AA43EFAB4690959A721F63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Datenfeed-ID</span></b> </p> </td> 
   <td colname="col2"> <p>ID des deaktivierten Datenfeeds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Datenfeed-Name</span></b> </p> </td> 
   <td colname="col2"> <p>Name des deaktivierten Datenfeeds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> EIGENSCHAFT</span></b> </p> </td> 
   <td colname="col2"> <p>Eigenschaften-IDs wurden deaktiviert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Eigenschaftsname</span></b> </p> </td> 
   <td colname="col2"> <p>Eigenschaftsnamen wurden deaktiviert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Segment-SID</span></b> </p> </td> 
   <td colname="col2"> <p>ID des Segments, das deaktivierte Eigenschaften enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Segmentname</span></b> </p> </td> 
   <td colname="col2"> <p>Name des Segments, das deaktivierte Eigenschaften enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Algo-Modell-ID</span></b> </p> </td> 
   <td colname="col2"> <p>Die ID des algorithmischen Modells, das deaktivierte Eigenschaften enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Name des Alpha-Modells</span></b> </p> </td> 
   <td colname="col2"> <p>Die Namen der algorithmischen Modelle, die deaktivierte Eigenschaften enthalten. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Deaktivierte Eigenschaften {#remove-deactivated-traits} entfernen

Als Datenkäufer sind Sie dafür verantwortlich, die Eigenschaften in einem abgebrochenen Feed aus all Ihren aktiven/in Verwendung befindlichen oder inaktiven Segmenten zu entfernen. Zu den Entfernungsoptionen gehören:

* Massenentfernung mit den [REST-APIs](../../../api/rest-api-main/rest-api-main.md) oder den [Massenverwaltungswerkzeugen](../../../reference/bulk-management-tools/bulk-management-intro.md).

* Suchen Sie manuell nach betroffenen Segmenten und entfernen Sie deaktivierte Eigenschaften mit [!UICONTROL Segment Builder]. Siehe [Eigenschaften aus einem Segment](../../../features/segments/segment-builder.md#segment-builder-controls-traits) entfernen.

>[!NOTE]
>
>Das Entfernen von Eigenschaften aus aktiven algorithmischen Modellen oder Zielen wirkt sich auf die Genauigkeit von Skalierung und Targeting aus. Versuchen Sie, gesperrte Eigenschaften nach Möglichkeit durch neue, aktive Eigenschaften zu ersetzen.

[Melden Sie sich von der deaktivierten ](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe) Datenmeldung ab, nachdem Sie alle gesperrten Eigenschaften aus Ihrem Konto entfernt haben. Wenn es sich hierbei um eine vorübergehende Deaktivierung handelt, können Sie das Abonnement erneut abschließen, nachdem der Datenanbieter die erforderlichen Änderungen vorgenommen und den Feed reaktiviert hat. Wie bei den meisten Dingen kann Ihnen eine gute Kommunikation mit Ihren Partnern (dem Datenanbieter und [!DNL Adobe]) dabei helfen, diesen Prozess zu durchlaufen.

## Grundlegendes zur Abo-Detailseite im Audience Marketplace {#marketplace-buyer-details}

Wenn Sie auf den Namen eines Datenplans in [!UICONTROL Marketplace] klicken, stellt [!DNL Audience Manager] Informationen bereit, die Ihnen helfen, fundierte Entscheidungen über das Abonnieren eines Datenfeeds zu treffen.

<!-- marketplace-buyer-details.xml -->

![](assets/plan-details-numbered.png)

Auf dieser Seite finden Sie die folgenden Informationen:

1. **Basisinformationen**. Dazu gehören Feed-Informationen wie:
   * Data Feed-Name. Wie oben gezeigt lautet der Name dieses Feeds beispielsweise &quot;Beispieldaten-Feed&quot;.
   * Name des Datenanbieters;
   * Datenfeed-ID;
   * Beschreibung;
   * Anzahl der Eigenschaften im Feed;

1. Informationsschaltflächen planen.
   * Klicken Sie auf **[!UICONTROL Explore All Traits]**, um Details zu allen Eigenschaften im ausgewählten Datenfeed anzuzeigen.
   * Klicken Sie auf **[!UICONTROL Request More Details]**, um dem Datenanbieter Fragen zum ausgewählten Datenfeed zu stellen oder einen Rabatt anzufordern. Diese Funktion sendet Ihre Kommentare und Fragen direkt an den Datenanbieter.

1. Datenfeed-Berichtsmetriken. Das Venn-Diagramm (und zugehörige Metriken) zeigt Ihnen die Daten der letzten 30 Tage mit Eigenschaften, die sich überschneiden. Siehe [Der Marketplace: Info](marketplace-data-buyers.md#about-marketplace) für Details.
   * **[!UICONTROL 30 Day Overlapped Uniques]**: Die Anzahl der Unique Users in Ihrem Konto, die sich mit den Benutzern im Konto des Anbieters überschneiden. Eine Definition individueller Benutzer finden Sie unter AAM UUUID im Index der IDs in Audience Manager[.](/help/using/reference/ids-in-aam.md)
   * **[!UICONTROL 30 Day Provider Unique Users]**: Die Anzahl der Unique Users, die vom Konto des Anbieters kommen.
   * **[!UICONTROL Your Unique Users]**: Die Anzahl der Unique Users, die von Ihrem Konto kommen.

1. **[!UICONTROL Plan Details]** Tabelle. Diese Tabelle zeigt Ihnen die Anwendungsfälle, für die Sie den Datenfeed abonnieren können, sowie das Preismodell. Siehe [Anwendungsfälle des Datenfeeds](#use-cases).

1. Aktionstasten planen.
   * Klicken Sie auf **[!UICONTROL Cancel]**, um die Seite zu verlassen, ohne Änderungen vorzunehmen.
   * Klicken Sie auf **[!UICONTROL Review & Subscribe]**, um einen Datenfeed zu abonnieren. Diese Schaltfläche ist ausgegraut, bis Sie einen [!UICONTROL Subscription]-Umschalter zu [!UICONTROL On] umschalten. Siehe auch [Abonnieren eines öffentlichen Datenfeeds](#subscript-public-data-feed) und [Abonnieren eines privaten Datenfeeds](#subscript-private-data-feed).

## Anwendungsfälle für Datenfeeds {#use-cases}

Als [!UICONTROL Audience Marketplace]-Datenkäufer können Sie Daten für Überschneidungen, Modellierungs- und Anwendungsfälle der Aktivierung erwerben. Jeder Anwendungsfall ist für einen bestimmten Zweck konzipiert und schränkt das, was Sie mit den Daten tun können, ein. Diese Verwendungsfallbeschreibungen können Ihnen dabei helfen, die richtige Entscheidung darüber zu treffen, welche Art von Datenplan Sie kaufen möchten.

## Vergleich mit Segmenten und Überschneidungsplänen {#comparisons}

<!-- c_use_cases_for_buyers.xml -->

### Segmente und Überschneidungen

In diesem Anwendungsfall können Sie Ihre Eigenschaften mit Anbietereigenschaften in einem Bericht mit einer Überschneidung von Eigenschaften vergleichen.[](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report) Außerdem können Sie Anbietereigenschaften zu einem Segment erstellen oder hinzufügen und weitere Vergleiche mit  [Segment-zu-](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) Trait- und  [Segment-zu-](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) Segment-Berichten vornehmen. Überschneidungsvergleiche können Ihnen helfen,

* **Reichweite der Audience erweitern:** Geringe Überschneidungen deuten darauf hin, dass Ihre Eigenschaften Benutzer enthalten, die Sie noch nicht gesehen haben. Möglicherweise möchten Sie, dass diese Eigenschaften versuchen, neue Benutzer zu erreichen.
* **Vorhandene Audiencen verbessern:** Hohe Überschneidungen deuten darauf hin, dass Ihre Eigenschaften denen des Datenanbieters ähnlich sind. Möglicherweise möchten Sie, dass diese Eigenschaften zu gezielten, schrittweisen Verbesserungen an einer bereits entwickelten Audience beitragen.

### Algorithmische Modelle

In diesem Anwendungsfall können Sie Lieferanteneigenschaften anhand Ihrer Eigenschaften mit [algorithmischer Modellierung](../../../features/algorithmic-models/understanding-models.md#understanding-models) auswerten. Zum Beispiel verwendet unser algorithmisches Modellierungssystem eine Ihrer Eigenschaften als Grundlage für den Vergleich mit einer Lieferanteneigenschaft. Wenn das Modell ausgeführt wird, kann es anzeigen, ob Audiencen in Lieferanteneigenschaften ähnliche Konversionsattribute wie Ihre Eigenschaften aufweisen.

### Activation

In diesem Anwendungsfall können Sie Daten an ein [Ziel](../../../features/destinations/destinations.md) senden. In [!DNL Audience Manager] ist ein Ziel ein Drittanbietersystem (Anzeigen-Server, [!DNL DSP], [!DNL DMP], Austausch usw.) für das Sie Daten freigeben möchten. Bei Verwendung von [!UICONTROL Activation] können Sie jedoch keine Überschneidungsberichte ausführen oder die Daten in einem algorithmischen Modell testen.

>[!MORELIKETHIS]
>
>* [Rechnungsstellung und Impressionszuordnung für CPM-Datenfeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Rechnungsstellung und Impressionszuordnung für einfache Feeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Bericht zur CPM-Nutzung](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
>* [Abonnieren eines öffentlichen Datenfeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed)
>* [Rabatte für Datenkäufer](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
>* [Der Marktplatz: Info](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace)


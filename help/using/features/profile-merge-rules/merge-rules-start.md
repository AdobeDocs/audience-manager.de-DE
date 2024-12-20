---
description: Um Profilzusammenführungsregeln zu erstellen, überprüfen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren und führen Sie sie aus.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Erste Schritte mit Profilzusammenführungsregeln
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 1%

---

# Erste Schritte mit Profilzusammenführungsregeln {#getting-started-with-profile-merge-rules}

Um [!UICONTROL Profile Merge Rules] zu erstellen, überprüfen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren und führen Sie sie aus.

<!-- merge-rules-start.xml -->

## Erstellen eines geräteübergreifenden Daten-Source {#create-data-source}

Um eine geräteübergreifende Datenquelle zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie die Schritte für jeden hier beschriebenen Abschnitt aus. Zum Erstellen oder Bearbeiten einer geräteübergreifenden Datenquelle sind Administratorberechtigungen erforderlich.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Beschreibungen [ verschiedenen Steuerelemente finden Sie unter Einstellungen für Data Source ](../datasources-list-and-settings.md#settings-menu-options) Menüoptionen.

## Data Source-Details {#details}

So schließen Sie den Abschnitt [!UICONTROL Data Source Details] ab:

1. Benennen Sie die Datenquelle.
2. *(Optional)* Beschreibt die Datenquelle. Eine knappe Beschreibung hilft Ihnen, die Rolle oder den Zweck der Datenquelle zu definieren.
3. Geben Sie einen Integrations-Code an. Ein Integrations-Code ist Ihre eigene, eindeutige ID für diese Datenquelle.
4. Wählen Sie in der Liste **[!UICONTROL ID Type]** die Option **[!UICONTROL Cross Device]** aus.
5. Wählen Sie in der Liste **[!UICONTROL ID Definition]** eine Option aus, die den Datenquellentyp definiert. Zu den Optionen zählen:
   * **[!UICONTROL Person]**: Eine ID, die eine einzelne Person definiert. Diese ID kann mehreren [!DNL Audience Manager]-IDs zugeordnet werden.
   * **[!UICONTROL Household]**: Eine ID, die eine Personengruppe definiert. Diese ID kann mehreren [!DNL Audience Manager]-IDs zugeordnet werden.

## Datenexportkontrolle {#export-controls}

[Datenexportsteuerelemente](../data-export-controls.md) sind optionale Klassifizierungsregeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls] nicht verwenden.

## Einstellungen für Data Source {#settings}

[!UICONTROL Data Source Settings] Abschnitt enthält mehrere Optionen, diese beiden sind jedoch für die Erstellung einer geräteübergreifenden Datenquelle wichtig:

* **[!UICONTROL Use as Authenticated Profile]**: Diese Einstellung ist standardmäßig ausgewählt und ermöglicht Ihnen das Erstellen eines [!UICONTROL Profile Merge Rule] mit Ihren eigenen, authentifizierten Daten.

* **[!UICONTROL Use as a Device Graph]**: Dieses Steuerelement steht nur Konten zur Verfügung, die als Datenanbieter aufgeführt sind. Wenn Sie dieses Kontrollkästchen aktivieren, wird Ihre Datenquelle als Gerätediagramm erstellt und Sie können sie für andere [!DNL Audience Manager] freigeben. Arbeiten Sie mit Ihrem [!DNL Audience Manager] Berater zusammen, um sich als Datenanbieter einzurichten und festzulegen, für welche Kunden dieses [!UICONTROL Data Source] freigegeben werden soll. Ihr Berater stellt Ihr Konto und die Freigabe von Gerätediagrammen über interne Bereitstellungsprozesse bereit.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Mit dieser Steuerung können Sie die Datenaufbewahrungsdauer für inaktive Kunden-IDs festlegen. Dadurch wird bestimmt, wie lange Audience Manager-IDs in unserer Datenbank aufbewahren, nachdem sie zuletzt auf der Audience Manager-Plattform gesehen wurden. Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie festlegen können, ist 1 Monat und der Höchstwert ist 5 Jahre. Beachten Sie, dass wir alle Monate als 30-Tage zählen. Audience Manager führt einen Prozess aus, der inaktive Kunden-IDs einmal wöchentlich gemäß der Datenaufbewahrung löscht, die Sie für inaktive Kunden-IDs festgelegt haben.

Mit den mit diesen Einstellungen verknüpften Textfeldern können Sie die [!UICONTROL Data Source] mit einem Alias umbenennen, der in den [Optionen für Profilzusammenführungsregeln“ angezeigt ](merge-rule-definitions.md). Wenn Sie beispielsweise einen Alias zu **[!UICONTROL Use as Authenticated Profile]** hinzufügen, wird dieser Name in der [!UICONTROL Authenticated Profile Options] angezeigt. Wenn Sie **[!UICONTROL Use as a Device Graph]** einen Alias hinzufügen, wird dieser Name in der [!UICONTROL Device Options] angezeigt.

## Erstellen einer Profilzusammenführungsregel {#create-profile-merge-rule}

Um ein [!UICONTROL Profile Merge Rule] zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** und führen Sie die Schritte für jeden hier beschriebenen Abschnitt aus.

Nach dem Einrichten einer geräteübergreifenden Datenquelle können Sie bis zu 3 Zusammenführungsregeln erstellen. Sie erhalten Zugriff auf eine 4. Profilzusammenführungsregel ([!UICONTROL All Cross-Device Profiles]), wenn Sie sich für [Personenbasierte Ziele“ ](../destinations/people-based-destinations-overview.md).

Zum Erstellen, Bearbeiten oder Löschen einer Regel sind Administratorberechtigungen erforderlich. Alle Benutzer können vorhandene [!UICONTROL Profile Merge Rules] anzeigen und verwenden.

<!-- create-profile-merge-rule.xml -->

**Voraussetzungen:** Zum Erstellen eines [!UICONTROL Profile Merge Rule] ist eine geräteübergreifende Datenquelle erforderlich. Siehe [Erstellen einer Daten-Source](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Unter [Optionen für Profilzusammenführungsregeln definiert](merge-rule-definitions.md) finden Sie Beschreibungen dieser verschiedenen Steuerelemente.

## Basisinformationen {#basic-info}

So schließen Sie den Abschnitt [!UICONTROL Basic Information] ab:

1. Benennen Sie die [!UICONTROL Profile Merge Rule].
2. *(Optional)* Beschreiben Sie die [!UICONTROL Profile Merge Rule]. Eine knappe Beschreibung hilft Ihnen, die Rolle oder den Zweck Ihrer Regel zu definieren.
3. *(Optional)* Wählen Sie **[!UICONTROL Set as default]** aus, wenn Sie dies zum [!UICONTROL Profile Merge Rule] machen möchten. Neue Segmente werden automatisch mit der Standardregel verknüpft.

## Datenexportkontrolle {#data-export-controls}

[Datenexportsteuerelemente](../data-export-controls.md) sind optionale Klassifizierungsregeln, die Sie auf Ihre [!UICONTROL Profile Merge Rule] anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls] nicht verwenden.

## Einrichtung der Profilzusammenführungsregel {#profile-merge-rule-setup}

So schließen Sie den Abschnitt [!UICONTROL Proflie Merge Rule Setup] ab:

1. **[!UICONTROL Authenticated Option]** auswählen. Zu den Optionen zählen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Wählen Sie eine **[!UICONTROL Authenticated Profile Option]** aus (maximal 3). Dies sind die [geräteübergreifenden Datenquellen](merge-rules-start.md) die Sie zuvor erstellt haben.
3. **[!UICONTROL Device Option]** auswählen. Zu den Optionen zählen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Klicken Sie auf **[!UICONTROL Save]**.

### Überlegungen zu Adobe Campaign-Zielen, die geräteübergreifende IDs als Benutzer-ID-Schlüssel verwenden {#considerations}

Ende 2019 haben wir eine Reihe von Verbesserungen an Profilzusammenführungsregeln veröffentlicht, um die Genauigkeit von Batch-Dateien zu verbessern, die mit geräteübergreifenden IDs generiert wurden. Diese Verbesserungen werden in Ihrer Audience Manager-Instanz ab Montag, dem 16. März 2020 streng berücksichtigt. Daher produzieren Segmente, die einem Ziel mit geräteübergreifenden IDs zugeordnet sind, in einigen Profilzusammenführungsregeln-Konfigurationen keine Exporte mehr.

Um mithilfe geräteübergreifender IDs wie Adobe Campaign die richtige Integration zwischen Ihrer Audience Manager-Instanz und Zielen sicherzustellen, müssen Sie die folgenden Anforderungen erfüllen:

1. Überprüfen Sie die Profilzusammenführungsregel, die von den Segmenten verwendet wird, die Ihrem deklarierten Adobe Campaign-ID-Ziel zugeordnet sind. Die Profilzusammenführungsregel muss die Option [!UICONTROL Last Authenticated Profile] verwenden, damit alle authentifizierten Profile in die Exporte einbezogen werden können. Wenn Ihre Profilzusammenführungsregel eine andere Option verwendet, wechseln Sie sie zu [!UICONTROL Last Authenticated Profile].
2. Wählen Sie die Datenquelle Adobe Campaign Declared ID in den Einstellungen Profilzusammenführungsregel aus.

>[!NOTE]
>
> Wenn Sie Ihre maximale Anzahl an [!UICONTROL Profile Merge Rules] erreicht haben und Hilfe bei der Konfiguration basierend auf den obigen Anweisungen benötigen, wenden Sie sich bitte an die Kundenunterstützung.

## Konfigurieren des Zusammenführungsregel-Codes {#configure-merge-rule-code}

Befolgen Sie diese Anweisungen, um den [!UICONTROL Adobe Experience Platform Identity Service]-, [!UICONTROL DIL]- und Mobile-[!DNL SDK]-Code für die Verwendung mit Ihren Zusammenführungsregeln einzurichten.

<!-- merge-rules-configure-code.xml -->

### Voraussetzungen

Sie müssen eine [geräteübergreifende Datenquelle“ und ](#create-data-source)Profilzusammenführungsregeln[ einrichten](#create-profile-merge-rule) *bevor Sie*.

## Für Kunden von Adobe Experience Platform Identity Service {#id-service-customers}

Für die Arbeit mit [!UICONTROL Profile Merge Rules] werden die [!UICONTROL Adobe Experience Platform Identity Service] und die neueste Version ](../../dil/dil-overview.md) [DILempfohlen. Sie müssen die [!UICONTROL Adobe Experience Platform Identity Service] jedoch nicht verwenden, um mit dieser Funktion zu arbeiten. Wenn Sie nur [!UICONTROL DIL] verwenden, lesen Sie den Abschnitt [Legacy-DIL](#legacy-dil) weiter unten.

### Konfigurieren der Funktion „Kunden-ID festlegen“

Beim Arbeiten mit dem [!UICONTROL Adobe Experience Platform Identity Service] übergibt die `setCustomerIDs` deklarierte IDs an [!DNL Audience Manager]. Um eine Profilzusammenführungsregel zu verwenden, müssen Sie `setCustomerIDs` so ändern, dass der beim Erstellen einer geräteübergreifenden Datenquelle angegebene Integrations-Code verwendet wird. Angenommen, Sie haben eine geräteübergreifende Datenquelle mit dem Integrations-Code `my_datasource_ic` erstellt. Um eine deklarierte ID zu übergeben, fügen Sie den Integrations-Code zur Funktion Besucher-ID hinzu, wie im folgenden geänderten Code-Beispiel gezeigt.

#### Generisches Codebeispiel

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Geändertes Code-Beispiel

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Weitere Informationen finden Sie unter [Erstellen einer geräteübergreifenden Daten-Source](#create-data-source) und [Kunden-IDs und Authentifizierungsstatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### `DIL.create` konfigurieren

Die neuesten Versionen von [!UICONTROL DIL] übernehmen nun automatisch die [!UICONTROL declared ID] aus der `visitorService` in `DIL.create` (siehe [Declared ID Variables](../declared-ids.md#declared-id-variables)). Überprüfen Sie Ihre `DIL.create`, um sicherzustellen, dass sie ordnungsgemäß eingerichtet ist, wie im folgenden Code-Beispiel gezeigt.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Im Schlüssel-Wert-Paar des Namespace ist die `*`MCORG`*`-Variable Ihre [!DNL Experience Cloud] Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im Abschnitt [!UICONTROL Administration] des [!DNL Experience Cloud]-Dashboards. Sie benötigen Administratorberechtigungen, um dieses Dashboard anzeigen zu können. Siehe [Administration: Zentrale Dienste](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Konfigurieren von SDKs

Siehe Abschnitt [Konfigurieren von SDKs](#configure-sdks-legacy-dil) unten.

## Legacy-DIL {#legacy-dil}

Wenn Sie [!DNL Adobe Experience Platform Identity Service] noch nicht verwenden, sollten Sie wirklich. Wir wissen jedoch, dass die Umstellung auf neuen Code sorgfältige Überlegungen und Tests erfordert. Überprüfen Sie in diesen Fällen Ihre `DIL.create`, um sicherzustellen, dass sie ordnungsgemäß eingerichtet ist, wie im folgenden Codebeispiel dargestellt.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Weitere Informationen finden Sie im Abschnitt zu älteren [!UICONTROL DIL] in [Declared ID Variables](../declared-ids.md#declared-id-variables).

### Konfigurieren von SDKs {#configure-sdks-legacy-dil}

Überprüfen Sie die Methoden in Ihrem [!DNL SDK]-Code, mit denen Sie [!UICONTROL declared IDs] von [!DNL Android] und [!DNL iOS] Mobilgeräten übergeben können. Die Variablennamen für die [!DNL Android]- und [!DNL iOS]-Code-Bibliotheken sind identisch:

* `dpid`: Die ID der geräteübergreifenden Datenquelle.
* `dpuuid`: Die [!UICONTROL declared ID] (d. h. die Benutzer-ID).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gerätetyp </th> 
   <th colname="col2" class="entry"> Methode </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntax:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Beispiel:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid(„myDpid“,„myDpuuid„); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>Syntax:</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>Beispiel:</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Siehe auch [Audience Manager-Methoden für Android](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) und [Audience Manager-Methoden für iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Erstellen einer Datenquelle](../manage-datasources.md#create-data-source)

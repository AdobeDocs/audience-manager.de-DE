---
description: Um Profilzusammenführungsrichtlinien zu erstellen, überprüfen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren und führen Sie sie aus.
seo-description: Um Profilzusammenführungsrichtlinien zu erstellen, überprüfen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren und führen Sie sie aus.
seo-title: Erste Schritte mit Profilzusammenführungsrichtlinien
solution: Audience Manager
title: Erste Schritte mit Profilzusammenführungsrichtlinien
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profilzusammenführung
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: b8c8f35376c5a8a85fa4eeace7b447385ee9f339
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 4%

---

# Erste Schritte mit Profilzusammenführungsrichtlinien {#getting-started-with-profile-merge-rules}

Um [!UICONTROL Profile Merge Rules] zu erstellen, überprüfen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren und führen Sie sie aus.

<!-- merge-rules-start.xml -->

## Geräteübergreifende Datenquelle erstellen {#create-data-source}

Um eine geräteübergreifende Datenquelle zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie die Schritte für jeden Abschnitt aus, der hier beschrieben wird. Zum Erstellen oder Bearbeiten einer geräteübergreifenden Datenquelle sind Administratorberechtigungen erforderlich.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Datenquelleneinstellungen und Menüoptionen](../datasources-list-and-settings.md#settings-menu-options) .

## Datenquellendetails {#details}

So schließen Sie den Abschnitt [!UICONTROL Data Source Details] ab:

1. Benennen Sie die Datenquelle.
2. *(Optional)* Beschreiben Sie die Datenquelle. Eine kurze Beschreibung hilft Ihnen bei der Definition der Rolle oder des Zwecks der Datenquelle.
3. Geben Sie einen Integrationscode an. Ein Integrationscode ist Ihre eigene eindeutige ID für diese Datenquelle.
4. Wählen Sie in der Liste **[!UICONTROL ID Type]** **[!UICONTROL Cross Device]** aus.
5. Wählen Sie in der Liste **[!UICONTROL ID Definition]** eine Option, die den Datenquellentyp definiert. Zu den Optionen zählen:
   * **[!UICONTROL Person]**: Eine ID, die eine einzelne Person definiert. Diese ID kann mehreren [!DNL Audience Manager] -IDs zugeordnet werden.
   * **[!UICONTROL Household]**: Eine ID, die eine Gruppe von Personen definiert. Diese ID kann mehreren [!DNL Audience Manager] -IDs zugeordnet werden.

## Datenexportkontrollen {#export-controls}

[Datenexportkontrollen ](../data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern das Senden von Daten an ein Ziel, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls] nicht verwenden.

## Datenquelleneinstellungen {#settings}

[!UICONTROL Data Source Settings] -Abschnitt bietet mehrere Optionen, diese beiden sind jedoch für die Erstellung einer geräteübergreifenden Datenquelle wichtig:

* **[!UICONTROL Use as Authenticated Profile]**: Standardmäßig aktiviert diese Einstellung die Erstellung einer  [!UICONTROL Profile Merge Rule] mit eigenen, authentifizierten Daten.

* **[!UICONTROL Use as a Device Graph]**: Dieses Steuerelement ist nur für Konten verfügbar, die als Datenanbieter aufgeführt sind. Wenn Sie dieses Kontrollkästchen aktivieren, wird Ihre Datenquelle als Gerätediagramm erstellt und Sie können sie für andere [!DNL Audience Manager]-Kunden freigeben. Arbeiten Sie mit Ihrem [!DNL Audience Manager]-Berater zusammen, um sich als Datenanbieter einzurichten und anzugeben, für welche Kunden dieser [!UICONTROL Data Source]-Dienst freigegeben werden soll. Ihr Berater stellt Ihre Freigabe von Konten und Gerätediagrammen über interne Bereitstellungsprozesse bereit.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Mit dieser Steuerung können Sie die Datenaufbewahrungsdauer für inaktive Kunden-IDs festlegen. Dadurch wird bestimmt, wie lange der Audience Manager Kunden-IDs in unserer Datenbank aufbewahrt, nachdem sie zuletzt auf der Audience Manager-Plattform angezeigt wurden. Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie einstellen können, ist 1 Monat und der Höchstwert 5 Jahre. Beachten Sie, dass wir alle Monate als 30 Tage zählen. Audience Manager führt einen Prozess aus, der inaktive Kunden-IDs einmal wöchentlich löscht. Dies entspricht der Datenaufbewahrung, die Sie für inaktive Kunden-IDs festgelegt haben.

Mithilfe der mit diesen Einstellungen verknüpften Textfelder können Sie [!UICONTROL Data Source] durch einen Alias umbenennen, der in den [Optionen für Profilzusammenführungsregeln](merge-rule-definitions.md) angezeigt wird. Wenn Sie beispielsweise **[!UICONTROL Use as Authenticated Profile]** einen Alias hinzufügen, wird dieser Name in der Liste [!UICONTROL Authenticated Profile Options] angezeigt. Wenn Sie **[!UICONTROL Use as a Device Graph]** einen Alias hinzufügen, wird dieser Name in der Liste [!UICONTROL Device Options] angezeigt.

## Erstellen einer Profilzusammenführungsrichtlinie {#create-profile-merge-rule}

Um ein [!UICONTROL Profile Merge Rule] zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** und führen Sie die Schritte für jeden Abschnitt aus, der hier beschrieben wird.

Sie können bis zu 3 Zusammenführungsregeln erstellen, nachdem Sie eine geräteübergreifende Datenquelle eingerichtet haben. Sie erhalten Zugriff auf eine 4. Profilzusammenführungsrichtlinie ([!UICONTROL All Cross-Device Profiles]), wenn Sie sich für [People-Based Destinations](../destinations/people-based-destinations-overview.md) registrieren.

Zum Erstellen, Bearbeiten oder Löschen einer Regel sind Administratorberechtigungen erforderlich. Alle Benutzer können vorhandene [!UICONTROL Profile Merge Rules] anzeigen und verwenden.

<!-- create-profile-merge-rule.xml -->

**Voraussetzungen:** Zum Erstellen einer  [!UICONTROL Profile Merge Rule]ist eine geräteübergreifende Datenquelle erforderlich. Siehe [Erstellen einer Datenquelle](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Optionen für Profilzusammenführungsregeln definiert](merge-rule-definitions.md) .

## Basisinformationen {#basic-info}

So schließen Sie den Abschnitt [!UICONTROL Basic Information] ab:

1. Benennen Sie [!UICONTROL Profile Merge Rule].
2. *(Optional)* Beschreiben Sie die  [!UICONTROL Profile Merge Rule]. Eine kurze Beschreibung hilft Ihnen bei der Definition der Rolle oder des Zwecks Ihrer Regel.
3. *(Optional)* Wählen Sie  **[!UICONTROL Set as default]** aus, ob Sie dies zur Standardeinstellung machen möchten  [!UICONTROL Profile Merge Rule]. Neue Segmente werden automatisch mit der Standardregel verknüpft.

## Datenexportkontrollen {#data-export-controls}

[Datenexportkontrollen ](../data-export-controls.md) sind optionale Classification-Regeln, die Sie auf Ihre  [!UICONTROL Profile Merge Rule]anwenden können. Sie verhindern das Senden von Daten an ein Ziel, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls] nicht verwenden.

## Einrichten von Profilzusammenführungsregeln {#profile-merge-rule-setup}

So schließen Sie den Abschnitt [!UICONTROL Proflie Merge Rule Setup] ab:

1. Wählen Sie einen **[!UICONTROL Authenticated Option]**. Zu den Optionen zählen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Wählen Sie ein **[!UICONTROL Authenticated Profile Option]** (bis zu 3, Maximum). Dies sind die [geräteübergreifenden Datenquellen](merge-rules-start.md), die Sie zuvor erstellt haben.
3. Wählen Sie eine **[!UICONTROL Device Option]**. Zu den Optionen zählen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Klicken **[!UICONTROL Save]**.

### Überlegungen zu Adobe Campaign-Zielen, die geräteübergreifende IDs als Benutzer-ID-Schlüssel verwenden {#considerations}

Ende 2019 haben wir eine Reihe von Verbesserungen der Profilzusammenführungsrichtlinien veröffentlicht, um die Genauigkeit von Batch-Dateien zu verbessern, die mit geräteübergreifenden IDs generiert wurden. Diese Verbesserungen werden in Ihrer Audience Manager-Instanz ab Montag, dem 16. März 2020 strikt berücksichtigt. Folglich produzieren Segmente, die mit geräteübergreifenden IDs einem Ziel zugeordnet sind, in einigen Konfigurationen der Profilzusammenführungsrichtlinien keine Exporte mehr.

Um die korrekte Integration zwischen Ihrer Audience Manager-Instanz und Zielen mithilfe geräteübergreifender IDs wie Adobe Campaign sicherzustellen, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

1. Überprüfen Sie die Profilzusammenführungsrichtlinie , die von den Segmenten verwendet wird, die Ihrem Adobe Campaign Declared ID-Ziel zugeordnet sind. Die Profilzusammenführungsrichtlinie muss die Option [!UICONTROL Last Authenticated Profile] verwenden, damit alle authentifizierten Profile in die Exporte einbezogen werden können. Wenn Ihre Profilzusammenführungsrichtlinie eine andere Option verwendet, wechseln Sie zu [!UICONTROL Last Authenticated Profile].
2. Wählen Sie die Datenquelle Adobe Campaign Declared ID in den Profilzusammenführungsregeleinstellungen aus.

>[!NOTE]
>
> Wenn Sie die maximale Anzahl von [!UICONTROL Profile Merge Rules] erreicht haben und Unterstützung bei der Konfiguration dieser Variablen anhand der oben stehenden Anweisungen benötigen, wenden Sie sich an die Kundenunterstützung.

## Konfigurieren des Zusammenführungsregelcodes {#configure-merge-rule-code}

Befolgen Sie diese Anweisungen, um den [!UICONTROL Adobe Experience Platform Identity Service]-, [!UICONTROL DIL]- und mobilen [!DNL SDK]-Code für die Verwendung mit Ihren Zusammenführungsregeln einzurichten.

<!-- merge-rules-configure-code.xml -->

### Voraussetzungen

Sie müssen eine [geräteübergreifende Datenquelle](#create-data-source) und [Regeln zur Profilzusammenführung](#create-profile-merge-rule) *einrichten, bevor Sie diese Verfahren abschließen.*

## Für Adobe Experience Platform Identity Service-Kunden {#id-service-customers}

Die [!UICONTROL Adobe Experience Platform Identity Service] und die neueste Version von [DIL](../../dil/dil-overview.md) werden beim Arbeiten mit [!UICONTROL Profile Merge Rules] empfohlen. Sie müssen jedoch nicht [!UICONTROL Adobe Experience Platform Identity Service] verwenden, um mit dieser Funktion zu arbeiten. Wenn Sie nur [!UICONTROL DIL] verwenden, lesen Sie den [alten DIL-Abschnitt](#legacy-dil) weiter unten.

### Konfigurieren der Funktion zum Festlegen der Kunden-ID

Bei der Arbeit mit [!UICONTROL Adobe Experience Platform Identity Service] übergibt die Funktion `setCustomerIDs` deklarierte IDs an [!DNL Audience Manager]. Um eine Profilzusammenführungsregel zu verwenden, müssen Sie `setCustomerIDs` ändern, um den Integrationscode zu verwenden, der beim Erstellen einer geräteübergreifenden Datenquelle angegeben wurde. Angenommen, Sie haben eine geräteübergreifende Datenquelle mit dem Integrationscode `my_datasource_ic` erstellt. Um eine deklarierte ID zu übergeben, fügen Sie den Integrationscode zur Besucher-ID-Funktion hinzu, wie im geänderten Code-Beispiel unten dargestellt.

#### Beispiel für generischen Code

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Muster für modifizierten Code

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Weitere Informationen finden Sie unter [Erstellen einer geräteübergreifenden Datenquelle](#create-data-source) und [Kunden-IDs und Authentifizierungsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html).

### Funktion `DIL.create` konfigurieren

In den neuesten Versionen von [!UICONTROL DIL] wird [!UICONTROL declared ID] jetzt automatisch von der Funktion `visitorService` in `DIL.create` abgerufen (siehe [Deklarierte ID-Variablen](../declared-ids.md#declared-id-variables)). Überprüfen Sie Ihre `DIL.create`-Funktion, um sicherzustellen, dass sie ordnungsgemäß eingerichtet ist, wie im Code-Beispiel unten dargestellt.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Im Schlüssel-Wert-Paar des Namespace ist die Variable `*`MCORG`*` Ihre [!DNL Experience Cloud] Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im Abschnitt [!UICONTROL Administration] des [!DNL Experience Cloud]-Dashboards. Sie benötigen Administratorberechtigungen, um dieses Dashboard anzuzeigen. Siehe [Administration: Hauptdienste](https://docs.adobe.com/content/help/de-DE/core-services/interface/manage-users-and-products/admin-getting-started.html).

### SDKs konfigurieren

Siehe den Abschnitt [SDKs konfigurieren](#configure-sdks-legacy-dil) unten.

## Legacy-DIL {#legacy-dil}

Wenn Sie [!DNL Adobe Experience Platform Identity Service] noch nicht verwenden, sollten Sie das wirklich tun. Wir wissen jedoch, dass die Umstellung auf neuen Code sorgfältiges Denken und Testen erfordert. Überprüfen Sie in diesen Fällen Ihre `DIL.create`-Funktion, um sicherzustellen, dass sie ordnungsgemäß eingerichtet ist, wie im Code-Beispiel unten dargestellt.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Weitere Informationen finden Sie im Abschnitt [!UICONTROL DIL] im Abschnitt [Deklarierte ID-Variablen](../declared-ids.md#declared-id-variables).

### SDKs konfigurieren {#configure-sdks-legacy-dil}

Überprüfen Sie die Methoden in Ihrem [!DNL SDK]-Code, mit denen Sie [!UICONTROL declared IDs] von [!DNL Android] und [!DNL iOS] Mobilgeräten übergeben können. Die Variablennamen für die Code-Bibliotheken [!DNL Android] und [!DNL iOS] sind identisch:

* `dpid`: Die geräteübergreifende Datenquellen-ID.
* `dpuuid`: Die  [!UICONTROL declared ID] (d. h. die Benutzer-ID).

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntax:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Beispiel:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
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

Siehe auch [Audience Manager-Methoden für Android](https://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) und [Audience Manager-Methoden für iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Erstellen einer Datenquelle](../manage-datasources.md#create-data-source)


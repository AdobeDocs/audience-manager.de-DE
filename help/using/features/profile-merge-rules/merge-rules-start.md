---
description: Um Profil Merge Rules zu erstellen, überprüfen und führen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren aus.
seo-description: Um Profil Merge Rules zu erstellen, überprüfen und führen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren aus.
seo-title: Erste Schritte mit Profil-Zusammenführungsregeln
solution: Audience Manager
title: Erste Schritte mit Profil-Zusammenführungsregeln
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Erste Schritte mit Profil-Zusammenführungsregeln {#getting-started-with-profile-merge-rules}

Um die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren zu erstellen, zu überprüfen und durchzuführen, müssen Sie diese Schritte durchführen. [!UICONTROL Profile Merge Rules]

<!-- merge-rules-start.xml -->

## Geräteübergreifende Datenquelle erstellen {#create-data-source}

Um eine geräteübergreifende Datenquelle zu erstellen, gehen Sie zu den Schritten für jeden Abschnitt, der hier beschrieben wird, **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie sie aus. Zum Erstellen oder Bearbeiten einer geräteübergreifenden Datenquelle sind Administratorberechtigungen erforderlich.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Datenquelleneinstellungen und Menüoptionen](../datasources-list-and-settings.md#settings-menu-options) .

## Datenquellendetails {#details}

So füllen Sie den [!UICONTROL Data Source Details] Abschnitt aus:

1. Benennen Sie die Datenquelle.
2. *(Optional)* Beschreiben Sie die Datenquelle. Eine knappe Beschreibung hilft Ihnen, die Rolle oder den Zweck der Datenquelle zu definieren.
3. Geben Sie einen Integrationscode ein. Ein Integrationscode ist Ihre eigene eindeutige ID für diese Datenquelle.
4. Wählen Sie in der **[!UICONTROL ID Type]** Liste **[!UICONTROL Cross Device]**.
5. Wählen Sie in der **[!UICONTROL ID Definition]** Liste eine Option, die den Datenquellentyp definiert. Zu den Optionen zählen:
   * **[!UICONTROL Person]**: Eine ID, die eine einzelne Person definiert. Diese ID kann mehreren [!DNL Audience Manager] IDs zugeordnet werden.
   * **[!UICONTROL Household]**: Eine ID, die eine Gruppe von Personen definiert. Diese ID kann mehreren [!DNL Audience Manager] IDs zugeordnet werden.

## Datenexportkontrolle {#export-controls}

[Data Export Controls](../data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie nicht verwenden [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] bietet mehrere Optionen, diese beiden sind jedoch wichtig für die Erstellung einer geräteübergreifenden Datenquelle:

* **[!UICONTROL Use as Authenticated Profile]**: Diese Einstellung ist standardmäßig aktiviert und ermöglicht es Ihnen, eine [!UICONTROL Profile Merge Rule] mit eigenen, authentifizierten Daten zu erstellen.

* **[!UICONTROL Use as a Device Graph]**: Dieses Steuerelement steht nur für Konten zur Verfügung, die als Datenanbieter aufgeführt sind. Wenn Sie dieses Kontrollkästchen aktivieren, wird Ihre Datenquelle als Gerätediagramm erstellt und Sie können sie für andere [!DNL Audience Manager] Kunden freigeben. Wenden Sie sich an Ihren [!DNL Audience Manager] Berater, um sich als Datenanbieter einzurichten und anzugeben, für welche Kunden diese freigegeben werden [!UICONTROL Data Source] soll. Ihr Berater stellt Ihre Konto- und Gerätediagrammfreigabe über interne Bereitstellungsprozesse bereit.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Mit diesem Steuerelement können Sie die Datenaufbewahrungszeit für inaktive Kunden-IDs festlegen. Dadurch wird bestimmt, wie lange Audience Manager Kunden-IDs in unserer Datenbank aufbewahrt, nachdem sie zuletzt auf der Audience Manager-Plattform angezeigt wurden. Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie einstellen können, ist 1 Monat und der Höchstwert 5 Jahre. Beachten Sie, dass wir alle Monate als 30 Tage zählen. Audience Manager führt einen Prozess aus, bei dem inaktive Kunden-IDs einmal wöchentlich gelöscht werden, entsprechend der für inaktive Kunden-IDs festgelegten Datenaufbewahrung.

Mit den mit diesen Einstellungen verknüpften Textfeldern können Sie die [!UICONTROL Data Source] mit einem Alias umbenennen, der in den Optionen [für die](merge-rule-definitions.md)Profil-Merge-Regel angezeigt wird. Wenn Sie beispielsweise einen Alias zu **[!UICONTROL Use as Authenticated Profile]** hinzufügen, wird dieser Name in der [!UICONTROL Authenticated Profile Options] Liste angezeigt. Wenn Sie einem Alias einen Namen hinzufügen, **[!UICONTROL Use as a Device Graph]** wird dieser in der [!UICONTROL Device Options] Liste angezeigt.

## Eine Profil Merge Rule erstellen {#create-profile-merge-rule}

Um eine [!UICONTROL Profile Merge Rule]zu erstellen, gehen Sie zu den Schritten für die einzelnen Abschnitte, die hier beschrieben werden, **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** und führen Sie sie aus.

Sie können bis zu 3 Zusammenführungsregeln erstellen, nachdem Sie eine geräteübergreifende Datenquelle eingerichtet haben. Sie erhalten Zugriff auf eine 4. Profil Merge Rule ([!UICONTROL All Cross-Device Profiles]), wenn Sie sich für [People-Based Destination](../destinations/people-based-destinations-overview.md)registrieren.

Zum Erstellen, Bearbeiten oder Löschen einer Regel sind Administratorberechtigungen erforderlich. Alle Benutzer können Ansichten durchführen und bestehende verwenden [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Voraussetzungen:** Eine geräteübergreifende Datenquelle ist erforderlich, um eine [!UICONTROL Profile Merge Rule]zu erstellen. Siehe Datenquelle [erstellen](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Profil Merge Rule Options Defined](merge-rule-definitions.md) .

## Basisinformationen {#basic-info}

So füllen Sie den [!UICONTROL Basic Information] Abschnitt aus:

1. Benennen Sie die [!UICONTROL Profile Merge Rule].
2. *(Optional)* Beschreiben Sie die [!UICONTROL Profile Merge Rule]. Eine kurze Beschreibung hilft Ihnen, die Rolle oder den Zweck Ihrer Regel zu definieren.
3. *(Optional)* Wählen Sie **[!UICONTROL Set as default]** , wenn Sie dies als Standard festlegen möchten [!UICONTROL Profile Merge Rule]. Neue Segmente werden automatisch mit der Standardregel verknüpft.

## Datenexportkontrolle {#data-export-controls}

[Datenexportkontrollen](../data-export-controls.md) sind optionale Classification-Regeln, die Sie auf Ihre [!UICONTROL Profile Merge Rule]Anwendung anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie nicht verwenden [!UICONTROL Data Export Controls].

## Profil Merge Rule Setup {#profile-merge-rule-setup}

So füllen Sie den [!UICONTROL Proflie Merge Rule Setup] Abschnitt aus:

1. Wählen Sie eine **[!UICONTROL Authenticated Option]**. Zu den Optionen zählen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Wählen Sie eine **[!UICONTROL Authenticated Profile Option]** (maximal 3) aus. Dies sind die zuvor erstellten [geräteübergreifenden Datenquellen](merge-rules-start.md) .
3. Wählen Sie eine **[!UICONTROL Device Option]**. Zu den Optionen zählen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Klicken **[!UICONTROL Save]**.

## Regelcode zusammenführen konfigurieren {#configure-merge-rule-code}

Befolgen Sie diese Anweisungen, um den [!UICONTROL Adobe Experience Platform Identity Service]-, [!UICONTROL DIL]- und mobilen [!DNL SDK] Code für die Verwendung mit den Zusammenführungsregeln einzurichten.

<!-- merge-rules-configure-code.xml -->

### Voraussetzungen

Sie müssen eine [geräteübergreifende Datenquellen](#create-data-source) - und [Profil-Zusammenführungsregel](#create-profile-merge-rule) einrichten, *bevor* Sie diese Verfahren abschließen.

## Kunden mit dem Identitätsdienst für Adobe Experience Platform {#id-service-customers}

Die [!UICONTROL Adobe Experience Platform Identity Service] und die neueste Version von [DIL](../../dil/dil-overview.md) werden beim Arbeiten mit [!UICONTROL Profile Merge Rules]DIL empfohlen. Sie müssen jedoch nicht die verwenden, [!UICONTROL Adobe Experience Platform Identity Service] um mit dieser Funktion zu arbeiten. Wenn Sie nur [!UICONTROL DIL]die [ältere DIL verwenden, lesen Sie den Abschnitt](#legacy-dil) unten.

### Konfigurieren der Funktion &quot;Kunden-ID festlegen&quot;

Bei der Arbeit mit der [!UICONTROL Adobe Experience Platform Identity Service]Funktion übergibt die `setCustomerIDs` Funktion deklarierte IDs an [!DNL Audience Manager]. Um eine Profil Merge-Regel zu verwenden, müssen Sie den Integrationscode ändern, der beim Erstellen einer geräteübergreifenden Datenquelle angegeben wurde. `setCustomerIDs` Angenommen, Sie haben eine geräteübergreifende Datenquelle mit dem Integrationscode erstellt `my_datasource_ic`. Um eine deklarierte ID zu übergeben, fügen Sie den Integrationscode zur Besucher-ID-Funktion hinzu, wie im folgenden Codebeispiel für Änderungen dargestellt.

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

### Konfigurieren `DIL.create` der Funktion

Die neuesten Versionen von [!UICONTROL DIL] übernehmen nun automatisch die [!UICONTROL declared ID] Funktion in `visitorService` (siehe `DIL.create` Deklarierte ID-Variablen [](../declared-ids.md#declared-id-variables)). Überprüfen Sie Ihre `DIL.create` Funktion, um sicherzustellen, dass sie ordnungsgemäß eingerichtet ist, wie im folgenden Codebeispiel dargestellt.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Im Schlüssel-Wert-Paar des Namensraums ist die `*`MCORG`*` -Variable Ihre [!DNL Experience Cloud] Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im [!UICONTROL Administration] Abschnitt des [!DNL Experience Cloud] Dashboards. Sie benötigen Administratorrechte, um dieses Dashboard Ansicht. See [Administration: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

### SDKs konfigurieren

Siehe Abschnitt SDKs [konfigurieren](#configure-sdks-legacy-dil) unten.

## Legacy-DIL {#legacy-dil}

Wenn du [!DNL Adobe Experience Platform Identity Service] noch nicht verwendest, solltest du das wirklich tun. Aber wir verstehen, dass die Umstellung auf neuen Code sorgfältige Überlegungen und Tests erfordert. Überprüfen Sie in diesen Fällen Ihre `DIL.create` Funktion, um sicherzustellen, dass diese ordnungsgemäß eingerichtet ist, wie im folgenden Codebeispiel dargestellt.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Weitere Informationen finden Sie im [!UICONTROL DIL] Abschnitt &quot;Legacy&quot;in [Deklarierten ID-Variablen](../declared-ids.md#declared-id-variables).

### SDKs konfigurieren {#configure-sdks-legacy-dil}

Überprüfen Sie die Methoden in Ihrem [!DNL SDK] Code, mit denen Sie [!UICONTROL declared IDs] von [!DNL Android] und [!DNL iOS] Mobilgeräten weiterleiten können. Die Variablennamen für die [!DNL Android] und [!DNL iOS] Code-Bibliotheken sind identisch:

* `dpid`: Die geräteübergreifende Datenquellen-ID.
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

Siehe auch [Audience Manager-Methoden für Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) und [Audience Manager-Methoden für iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Datenquelle erstellen](../manage-datasources.md#create-data-source)


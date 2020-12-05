---
description: Im Eigenschaften-Aufbau können Sie mit dem Ausdruck-Builder Regeln erstellen und testen, die die Anforderungen an die Audience-Qualifizierung festlegen. Regeln bestehen aus Schlüssel-Wert-Paaren wie "color == blue" oder "price&gt; 100". Vergleichsoperatoren ermitteln die Beziehung zwischen Schlüsseln und Werten. Boolesche Ausdruck bestimmen die Beziehung zwischen Regelgruppen.
seo-description: Im Eigenschaften-Aufbau können Sie mit dem Ausdruck-Builder Regeln erstellen und testen, die die Anforderungen an die Audience-Qualifizierung festlegen. Regeln bestehen aus Schlüssel-Wert-Paaren wie "color == blue" oder "price&gt; 100". Vergleichsoperatoren ermitteln die Beziehung zwischen Schlüsseln und Werten. Boolesche Ausdruck bestimmen die Beziehung zwischen Regelgruppen.
seo-title: Verwalten von Eigenschaftsregeln
solution: Audience Manager
title: Verwalten von Eigenschaftsregeln
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
translation-type: tm+mt
source-git-commit: 14c5ac091a27d125c96d17ce750c6e25ad844856
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---


# Verwalten von Eigenschaftsregeln {#managing-trait-rules}

In [!UICONTROL Trait Builder] können Sie mit [!UICONTROL Expression Builder] Regeln erstellen und testen, die die Anforderungen an die Audience-Qualifizierung festlegen. Regeln bestehen aus Schlüssel-Wert-Paaren wie `color == blue` oder `price > 100`. Vergleichsoperatoren ermitteln die Beziehung zwischen Schlüsseln und Werten. [!DNL Boolean] ausdruck bestimmen die Beziehung zwischen Regelgruppen.

<!-- c_tb_rules.xml -->

## Beschreibung der wichtigsten Funktionen der Signalregeln

![](assets/manage-trait-rules.png)

1. Die Registerkarten **[!UICONTROL Expression Builder]** oder **[!UICONTROL Code View]** bieten einen Überblick über die Regeln in Ihrer Eigenschaft. Auf der Registerkarte **[!UICONTROL Expression Builder]** können Sie Regeln mit Feldern und Dropdown-Menüs erstellen. Mit **[!UICONTROL Code View]** können Sie Regeln erstellen, indem Sie diese Ausdruck manuell als Code schreiben. Die Abbildung oben zeigt eine einfache Eigenschaft, die aus einem Signal besteht, das Daten für eine qualifizierte Bedingung auswertet, bei der ein Produktschlüssel einem bestimmten Wert entspricht, in diesem Fall `color == "blue"`.

1. Mit den Feldern und Steuerelementen in diesem Abschnitt können Sie Signale aus Schlüssel-Wert-Paaren erstellen und die Beziehung zwischen ihnen und einem Vergleichsoperator festlegen. Ein Schlüssel, ein Operator und ein Wert sind erforderlich.
1. Mit dem [!UICONTROL Data Explorer Options] können Sie Eigenschaften für Ihre Signale aufstocken.

   >[!NOTE]
   >
   >Diese Option ist nur für [!UICONTROL Data Explorer]-Kunden verfügbar. Weitere Informationen erhalten Sie von Ihrem Adobe-Berater.

1. Dieser Abschnitt zeigt Ihnen eine Schätzung der Eigenschaftenrealisierungen für die letzten 7 Tage für die in [!UICONTROL Expression Builder] definierten Signale für rückgefüllte und nicht rückgefüllte Eigenschaften.

   >[!NOTE]
   >
   >Diese Option ist nur für [!UICONTROL Data Explorer]-Kunden verfügbar. Weitere Informationen erhalten Sie von Ihrem Adobe-Berater.

1. Mit den Testfeldern können Sie Kombinationen von Signalregeln oder den [!DNL URL]s überprüfen, die Sie beim Senden von Daten an Audience Manager verwenden möchten.

## Eine Eigenschaftsregel {#create-trait-rule} erstellen

Regeln (oder Ausdruck) bestehen aus einzelnen oder Gruppen von Schlüssel-Wert-Paaren. Vergleichsoperatoren legen die Beziehung zwischen Schlüssel/Wert-Paaren fest. Um eine Regel zu erstellen, geben Sie einen Schlüssel und einen Wert ein, wählen Sie einen Operator aus und klicken Sie auf **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Füllen Sie die erforderlichen Felder im Abschnitt **[!UICONTROL Basic Information]** *aus, bevor Sie die Eigenschaftenregeln erstellen.*

1. Erweitern Sie den Abschnitt **[!UICONTROL Trait Expression]** und geben Sie einen Schlüssel- und Wertnamen ein. Dadurch wird ein *`signal`* erstellt.

   >[!NOTE]
   >
   >Schließen Sie das Präfix `c_` (oder eine andere Benennungsregel) für die Schlüsselvariable ein, wenn Ihr Ereignis Daten mit dieser Syntax an [!DNL Audience Manager] sendet.

1. Wählen Sie einen [Vergleichsoperator](../../features/traits/trait-comparison-operators.md) aus der Dropdownliste **[!UICONTROL Operator]**. Der Vergleichsoperator bewertet die Beziehung zwischen den Elementen in einem Signal.

   >[!NOTE]
   >
   >Der [!DNL Boolean] [!UICONTROL OR]-Operator stellt die Beziehung zwischen mehreren Signalen *innerhalb* einer Gruppe her und kann nicht geändert werden.

1. Klicken **[!UICONTROL Add Rule]**. Die gespeicherte Regel wird im Arbeitsbereich &quot;Eigenschaften&quot;über den Dateneingabefeldern angezeigt.

### Beispiel {#example-trait-rule}

Im Beispiel unten hat ein Benutzer eine neue Eigenschaftsregel erstellt, die auf der Produkt-ID basiert. Um diese Regel zu erstellen, stellte der Benutzer den Schlüssel `productkey` bereit, der mit einem Gleichheitsoperator ( `==`) mit dem Wert `2093` verknüpft ist.

![](assets/tb_sample_rule1.png)

Durch Klicken auf **[!UICONTROL Add Rule]** wird das Merkmal gespeichert und in den Arbeitsbereich [!UICONTROL Expression Builder] verschoben.

![](assets/tb_sample_rule2.png)

## Neue Regelgruppe {#create-rule-group} erstellen

Dieser Vorgang beschreibt, wie Sie eine neue Regelgruppe erstellen.

<!-- t_tb_new_rule_group.xml -->

Ihre Eigenschaft muss mindestens zwei Regeln enthalten, bevor Sie eine neue Regelgruppe erstellen können.

1. Bewegen Sie den Cursor über die Regel, die Sie verschieben möchten, um sie hervorzuheben.
1. Bewegen Sie den Mauszeiger über den markierten Regelrand.

   Dadurch wird die Regel automatisch von der aktuellen Gruppe getrennt und in eine neue Gruppe verschoben.

   >[!NOTE]
   >
   >Ziehen Sie eine Regel zurück in die ursprüngliche Gruppe, wenn Sie sie versehentlich verschieben.

1. Wählen Sie einen [!DNL Boolean]-Operator ([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) aus dem Dropdown-Menü, um die Beziehung zwischen den Regelgruppen festzulegen.

## Regeln zwischen Gruppen {#move-rules-between-groups} verschieben

Um eine Regel zu verschieben, klicken Sie auf und ziehen Sie sie in eine andere Gruppe.

## Eigenschaften bearbeiten {#edit-trait}

Dieser Vorgang beschreibt, wie Sie eine Eigenschaft bearbeiten.

<!-- t_tb_edit.xml -->

1. Bewegen Sie den Mauszeiger im Dashboard [!UICONTROL Traits] über die Spalte **[!UICONTROL Actions]** für die Eigenschaft, die Sie bearbeiten möchten. Dadurch werden die Symbole zur Eigenschaftsverwaltung angezeigt.
1. Klicken Sie auf den Stift, um die Eigenschaft zu bearbeiten.

   ![](assets/tb_edit_trait.png)

## Eine Eigenschaftsregel {#delete-trait} löschen

Dieser Vorgang beschreibt, wie Sie eine Eigenschaftsregel löschen.

<!-- t_tb_delete_rule.xml -->

1. Bewegen Sie im Dashboard [!UICONTROL Traits] den Mauszeiger über die Spalten [!UICONTROL Actions] für die Eigenschaft, die Sie bearbeiten möchten, und klicken Sie auf das Stiftsymbol. Dadurch werden die Symbole zur Eigenschaftsverwaltung angezeigt.
1. Erweitern Sie den Abschnitt [!UICONTROL Trait Expression].
1. Bewegen Sie den Mauszeiger über die Regel, die Sie löschen möchten, und klicken Sie auf das X-Symbol. Die Regel wird sofort gelöscht.

>[!MORELIKETHIS]
>
>* [Neue Regelgruppe erstellen](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Regeln zwischen Gruppen verschieben](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eine Eigenschaftsregel erstellen](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Eine Eigenschaftsregel löschen](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Regeln zwischen Gruppen verschieben](../../features/traits/manage-trait-rules.md#move-rules-between-groups)


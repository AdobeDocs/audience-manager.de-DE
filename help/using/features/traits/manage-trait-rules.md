---
description: Im Eigenschaften-Aufbau können Sie mit dem Ausdruck-Builder Regeln erstellen und testen, die die Anforderungen an die Audience-Qualifizierung festlegen. Regeln bestehen aus Schlüssel-Wert-Paaren wie "color == blue"oder "price > 100". Vergleichsoperatoren ermitteln die Beziehung zwischen Schlüsseln und Werten. Boolesche Ausdruck bestimmen die Beziehung zwischen Regelgruppen.
seo-description: Im Eigenschaften-Aufbau können Sie mit dem Ausdruck-Builder Regeln erstellen und testen, die die Anforderungen an die Audience-Qualifizierung festlegen. Regeln bestehen aus Schlüssel-Wert-Paaren wie "color == blue"oder "price > 100". Vergleichsoperatoren ermitteln die Beziehung zwischen Schlüsseln und Werten. Boolesche Ausdruck bestimmen die Beziehung zwischen Regelgruppen.
seo-title: Verwalten von Eigenschaftsregeln
solution: Audience Manager
title: Verwalten von Eigenschaftsregeln
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 1%

---


# Verwalten von Eigenschaftsregeln {#managing-trait-rules}

In [!UICONTROL Trait Builder]der [!UICONTROL Expression Builder] können Sie Regeln erstellen und testen, die Anforderungen an die Audience-Qualifikation festlegen. Regeln bestehen aus Schlüssel-Wert-Paaren wie `color == blue` oder `price > 100`. Vergleichsoperatoren ermitteln die Beziehung zwischen Schlüsseln und Werten. [!DNL Boolean] Ausdruck bestimmen die Beziehung zwischen Regelgruppen.

<!-- c_tb_rules.xml -->

## Beschreibung der wichtigsten Funktionen der Signalregeln

![](assets/manage-trait-rules.png)

1. Die **[!UICONTROL Expression Builder]** oder **[!UICONTROL Code View]** Registerkarten bieten einen Überblick über die Regeln in Ihren Eigenschaften. Auf der **[!UICONTROL Expression Builder]** Registerkarte können Sie Regeln mit Feldern und Dropdownmenüs erstellen. Mit der **[!UICONTROL Code View]** können Sie Regeln erstellen, indem Sie diese Ausdruck manuell als Code schreiben. Die Abbildung oben zeigt eine einfache Eigenschaft, die aus einem Signal besteht, das Daten für eine qualifizierte Bedingung auswertet, bei der ein Produktschlüssel einem bestimmten Wert entspricht, in diesem Fall `color == "blue"`.

1. Mit den Feldern und Steuerelementen in diesem Abschnitt können Sie Signale aus Schlüssel-Wert-Paaren erstellen und die Beziehung zwischen ihnen und einem Vergleichsoperator festlegen. Ein Schlüssel, ein Operator und ein Wert sind erforderlich.
1. Mit [!UICONTROL Data Explorer Options] dem können Sie Eigenschaften für Ihre Signale aufstocken.
   >[!NOTE]
   >
   >Diese Option steht nur [!UICONTROL Data Explorer] Kunden zur Verfügung. Weitere Informationen erhalten Sie von Ihrem Adobe-Berater.
1. Dieser Abschnitt zeigt Ihnen eine Schätzung der Eigenschaftenrealisierungen der letzten 7 Tage für die in der [!UICONTROL Expression Builder]definierten Signale, für aufgestockte und nicht aufgestockte Eigenschaften.
   >[!NOTE]
   >
   >Diese Option steht nur [!UICONTROL Data Explorer] Kunden zur Verfügung. Weitere Informationen erhalten Sie von Ihrem Adobe-Berater.
1. Mit den Testfeldern können Sie Kombinationen von Signalregeln oder [!DNL URL]s überprüfen, die Sie beim Senden von Daten an Audience Manager verwenden möchten.

## Eine Eigenschaftsregel erstellen {#create-trait-rule}

Regeln (oder Ausdruck) bestehen aus einzelnen oder Gruppen von Schlüssel-Wert-Paaren. Vergleichsoperatoren legen die Beziehung zwischen Schlüssel/Wert-Paaren fest. Um eine Regel zu erstellen, geben Sie einen Schlüssel und einen Wert ein, wählen Sie einen Operator aus und klicken Sie auf **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Füllen Sie die erforderlichen Felder im **[!UICONTROL Basic Information]** Abschnitt aus, *bevor* Sie Eigenschaftenregeln erstellen.

1. Erweitern Sie den **[!UICONTROL Trait Expression]** Abschnitt und geben Sie einen Schlüssel und einen Wertnamen ein. Dadurch wird eine *`signal`* erstellt.
   >[!NOTE]
   >
   >Schließen Sie das `c_` Präfix (oder eine andere Benennungsregel) für die Schlüsselvariable ein, wenn Ihre Ereignis-Aufrufe Daten senden, um diese Syntax zu [!DNL Audience Manager] verwenden.
1. Wählen Sie einen [Vergleichsoperator](../../features/traits/trait-comparison-operators.md) aus der **[!UICONTROL Operator]** Dropdownliste. Der Vergleichsoperator bewertet die Beziehung zwischen den Elementen in einem Signal.
   >[!NOTE]
   >
   >Der [!DNL Boolean] Betreiber stellt die Beziehung zwischen mehreren Signalen [!UICONTROL OR] innerhalb ** einer Gruppe her und kann nicht geändert werden.
1. Klicken **[!UICONTROL Add Rule]**. Die gespeicherte Regel wird im Arbeitsbereich &quot;Eigenschaften&quot;über den Dateneingabefeldern angezeigt.

### Beispiel {#example-trait-rule}

Im Beispiel unten hat ein Benutzer eine neue Eigenschaftsregel erstellt, die auf der Produkt-ID basiert. Um diese Regel zu erstellen, stellte der Benutzer den Schlüssel bereit, der mit einem Gleichheitsoperator ( `productkey` ) mit dem Wert `==`verknüpft ist `2093`.
![](assets/tb_sample_rule1.png)

Durch Klicken **[!UICONTROL Add Rule]** wird die Eigenschaft gespeichert und in den [!UICONTROL Expression Builder] Arbeitsbereich verschoben.

![](assets/tb_sample_rule2.png)

## Create a New Rule Group {#create-rule-group}

Dieser Vorgang beschreibt, wie Sie eine neue Regelgruppe erstellen.

<!-- t_tb_new_rule_group.xml -->

Ihre Eigenschaft muss mindestens zwei Regeln enthalten, bevor Sie eine neue Regelgruppe erstellen können.

1. Bewegen Sie den Cursor über die Regel, die Sie verschieben möchten, um sie hervorzuheben.
1. Bewegen Sie den Mauszeiger über den markierten Regelrand.
Dadurch wird die Regel automatisch von der aktuellen Gruppe getrennt und in eine neue Gruppe verschoben.
   >[!NOTE]
   >
   >Ziehen Sie eine Regel zurück in die ursprüngliche Gruppe, wenn Sie sie versehentlich verschieben.
1. Wählen Sie einen [!DNL Boolean] Operator ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) aus dem Dropdown-Menü, um die Beziehung zwischen den Regelgruppen festzulegen.

## Regeln zwischen Gruppen verschieben {#move-rules-between-groups}

Um eine Regel zu verschieben, klicken Sie auf und ziehen Sie sie in eine andere Gruppe.

## Eigenschaften bearbeiten {#edit-trait}

Dieser Vorgang beschreibt, wie Sie eine Eigenschaft bearbeiten.

<!-- t_tb_edit.xml -->

1. Bewegen Sie den Mauszeiger im [!UICONTROL Traits] Dashboard über die **[!UICONTROL Actions]** Spalte für die Eigenschaft, die Sie bearbeiten möchten. Dadurch werden die Symbole zur Eigenschaftsverwaltung angezeigt.
1. Klicken Sie auf den Stift, um die Eigenschaft zu bearbeiten.

   ![](assets/tb_edit_trait.png)

## Eine Eigenschaftsregel löschen {#delete-trait}

Dieser Vorgang beschreibt, wie Sie eine Eigenschaftsregel löschen.

<!-- t_tb_delete_rule.xml -->

1. Bewegen Sie den Mauszeiger im [!UICONTROL Traits] Dashboard über die [!UICONTROL Actions] Spalten für die Eigenschaft, die Sie bearbeiten möchten, und klicken Sie auf das Stiftsymbol. Dadurch werden die Symbole zur Eigenschaftsverwaltung angezeigt.
1. Expand the [!UICONTROL Trait Expression] section.
1. Bewegen Sie den Mauszeiger über die Regel, die Sie löschen möchten, und klicken Sie auf das X-Symbol. Die Regel wird sofort gelöscht.

>[!MORELIKETHIS]
>
>* [Neue Regelgruppe erstellen](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Regeln zwischen Gruppen verschieben](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eine Eigenschaftsregel erstellen](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Eine Eigenschaftsregel löschen](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Regeln zwischen Gruppen verschieben](../../features/traits/manage-trait-rules.md#move-rules-between-groups)


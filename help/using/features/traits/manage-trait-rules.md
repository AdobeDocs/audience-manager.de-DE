---
description: Im Eigenschaftenaufbau können Sie mit dem Expression Builder Regeln erstellen und testen, die Anforderungen für die Zielgruppenqualifizierung einrichten. Regeln bestehen aus Schlüssel-Wert-Paaren wie "color = = blue" oder" price > 100" . Vergleichsoperatoren stellen die Beziehung zwischen Schlüssel und Werten her. Boolesche Ausdrücke bestimmen die Beziehung zwischen Regelgruppen.
seo-description: Im Eigenschaftenaufbau können Sie mit dem Expression Builder Regeln erstellen und testen, die Anforderungen für die Zielgruppenqualifizierung einrichten. Regeln bestehen aus Schlüssel-Wert-Paaren wie "color = = blue" oder" price > 100" . Vergleichsoperatoren stellen die Beziehung zwischen Schlüssel und Werten her. Boolesche Ausdrücke bestimmen die Beziehung zwischen Regelgruppen.
seo-title: Verwalten von Trait-Regeln
solution: Audience Manager
title: Verwalten von Trait-Regeln
uuid: 827 d 4567-2 b 6 f -411 e-bd 5 c -9735 c 916291 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Verwalten von Trait-Regeln {#managing-trait-rules}

In [!UICONTROL Trait Builder]können [!UICONTROL Expression Builder] Sie Regeln erstellen und testen, die Anforderungen für die Zielgruppenqualifikation einrichten. Regeln bestehen aus Schlüssel-Wert-Paaren wie `color == blue` z. B. oder `price > 100`. Vergleichsoperatoren stellen die Beziehung zwischen Schlüssel und Werten her. [!DNL Boolean] Ausdrücke bestimmen die Beziehung zwischen Regelgruppen.

<!-- c_tb_rules.xml -->

## Hauptsignal-Regelfunktionen beschrieben

![](assets/manage-trait-rules.png)

1. Die **[!UICONTROL Expression Builder]****[!UICONTROL Code View]** Registerkarten oder Registerkarten bieten einen Überblick über die Regeln in Ihrer Eigenschaft. Auf der **[!UICONTROL Expression Builder]** Registerkarte können Sie Regeln mit Feldern und Dropdown-Menüs erstellen. Mit der Option **[!UICONTROL Code View]** können Sie Regeln erstellen, indem Sie diese Ausdrücke manuell als Code schreiben. Die obige Abbildung zeigt eine einfache Eigenschaft, die aus einem Signal besteht, das Daten für eine qualifizierende Bedingung auswertet, bei der ein Produktschlüssel einen bestimmten Wert entspricht, in diesem Fall `color == "blue"`.

1. Mit den Feldern und Steuerelementen in diesem Abschnitt können Sie Signale aus Schlüssel-Wert-Paaren erstellen und die Beziehung zwischen den Schlüsselwertpaaren festlegen. Ein Schlüssel, ein Operator und ein Wert sind erforderlich.
1. Auf diese [!UICONTROL Data Explorer Options] Weise können Sie Eigenschaften von Eigenschaften für Ihre Signale aufstocken.
   >[!NOTE]
   >
   >Diese Option steht [!UICONTROL Data Explorer] nur Kunden zur Verfügung. Weitere Informationen erhalten Sie von Ihrem Adobe-Berater.
1. In diesem Abschnitt finden Sie eine Schätzung der Eigenschaften von Eigenschaften in den letzten 7 Tagen, für die Signatur, die im Abschnitt [!UICONTROL Expression Builder]für Backfill- und nicht-backfill-Eigenschaften definiert ist.
   >[!NOTE]
   >
   >Diese Option steht [!UICONTROL Data Explorer] nur Kunden zur Verfügung. Weitere Informationen erhalten Sie von Ihrem Adobe-Berater.
1. Mit den Testfeldern können Sie Kombinationen von Signalregeln oder die [!DNL URL]zu verwendenden s überprüfen, wenn Sie Daten an Audience Manager senden.

## Erstellen einer Eigenschaftenregel {#create-trait-rule}

Regeln (oder Ausdrücke) bestehen aus einzelnen oder Gruppen von Schlüsselwertpaaren. Vergleichsoperatoren stellen die Beziehung zwischen Schlüssel-Wert-Paaren fest. Um eine Regel zu erstellen, geben Sie einen Schlüssel ein, einen Wert, wählen Sie einen Operator und klicken **[!UICONTROL Add Rule]** Sie auf.

<!-- t_tb_create_rules.xml -->

Füllen Sie die erforderlichen Felder im **[!UICONTROL Basic Information]** Abschnitt *aus, bevor* Sie Trait-Regeln erstellen.

1. Erweitern Sie den **[!UICONTROL Trait Expression]** Abschnitt und geben Sie einen Schlüssel und einen Wertnamen ein. This creates a *`signal`*.
   >[!NOTE]
   >
   >Fügen Sie das `c_` Präfix (oder eine andere Benennungsregel) für die Schlüsselvariable ein, wenn Ihre Ereignisaufrufe Daten an [!DNL Audience Manager] die Verwendung dieser Syntax senden.
1. Wählen Sie einen [Vergleichsoperator](../../features/traits/trait-comparison-operators.md) aus der **[!UICONTROL Operator]** Dropdown-Liste aus. Der Vergleichsoperator wertet die Beziehung zwischen den Elementen in einem Signal aus.
   >[!NOTE]
   >
   >Der [!DNL Boolean][!UICONTROL OR] Operator legt die Beziehung zwischen mehreren Signalen *innerhalb* einer Gruppe fest und kann nicht geändert werden.
1. Klicken Sie auf **[!UICONTROL Add Rule]**. Die gespeicherte Regel wird in den Eigenschaften oberhalb der Dateneingabefelder angezeigt.

### Beispiel {#example-trait-rule}

Im unten stehenden Beispiel hat ein Benutzer basierend auf der Produkt-ID eine neue Regel für Eigenschaften erstellt. Um diese Regel zu erstellen, stellte der Benutzer den Schlüssel `productkey` bereit, der mit einem Gleichheitsoperator ( `==`) für den Wert verknüpft `2093`war.![](assets/tb_sample_rule1.png)


Durch Klicken **[!UICONTROL Add Rule]** auf die Schaltfläche speichern und verschieben Sie die Eigenschaft in die [!UICONTROL Expression Builder] Arbeitsfläche.

![](assets/tb_sample_rule2.png)

>[!MORE_ LIKE_ THIS]
>
>* [Neue Regelgruppe erstellen](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Regeln zwischen Gruppen verschieben](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eine Trait-Regel löschen](../../features/traits/manage-trait-rules.md#delete-trait)


## Neue Regelgruppe erstellen {#create-rule-group}

Dieser Vorgang beschreibt, wie Sie eine neue Regelgruppe erstellen.

<!-- t_tb_new_rule_group.xml -->

Die Eigenschaft muss mindestens zwei Regeln enthalten, bevor Sie eine neue Regelgruppe erstellen können.

1. Bewegen Sie den Cursor über die Regel, die Sie verschieben möchten, um ihn hervorzuheben.
1. Bewegen Sie den Mauszeiger über den hervorgehobenen Regelrand.
Dadurch wird die Regel automatisch von der aktuellen Gruppe getrennt und in eine neue Gruppe verschoben.
   >[!NOTE]
   >
   >Ziehen Sie eine Regel zurück in die ursprüngliche Gruppe, wenn Sie sie unbeabsichtigt verschieben.
1. Wählen Sie einen [!DNL Boolean] Operator ( [!UICONTROL AND][!UICONTROL OR], [!UICONTROL AND NOT]) aus dem Dropdownmenü aus, um die Beziehung zwischen den Regelgruppen festzulegen.

>[!MORE_ LIKE_ THIS]
>
>* [Erstellen einer Eigenschaftenregel](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Regeln zwischen Gruppen verschieben](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eine Trait-Regel löschen](../../features/traits/manage-trait-rules.md#delete-trait)


## Regeln zwischen Gruppen verschieben {#move-rules-between-groups}

Um eine Regel zu verschieben, klicken Sie auf eine andere Gruppe und ziehen Sie sie.

>[!MORE_ LIKE_ THIS]
>
>* [Erstellen einer Eigenschaftenregel](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Neue Regelgruppe erstellen](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Eine Trait-Regel löschen](../../features/traits/manage-trait-rules.md#delete-trait)


## Bearbeiten eines Merkmals {#edit-trait}

Dieser Vorgang beschreibt, wie Sie eine Eigenschaft bearbeiten.

<!-- t_tb_edit.xml -->

1. Bewegen Sie den Mauszeiger im [!UICONTROL Traits] Dashboard über die **[!UICONTROL Actions]** Spalte, die Sie bearbeiten möchten. Dadurch werden die Symbole für das Trait-Management angezeigt.
1. Klicken Sie auf den Stiftsymbol, um die Eigenschaft zu bearbeiten.

   ![](assets/tb_edit_trait.png)

## Eine Trait-Regel löschen {#delete-trait}

Dieser Vorgang beschreibt, wie Sie eine Eigenschaftenregel löschen.

<!-- t_tb_delete_rule.xml -->

1. Bewegen Sie den Mauszeiger im [!UICONTROL Traits] Dashboard über [!UICONTROL Actions] die Spalten, die Sie bearbeiten möchten, und klicken Sie auf das Stiftsymbol. Dadurch werden die Symbole für das Trait-Management angezeigt.
1. Erweitern Sie den [!UICONTROL Trait Expression] Abschnitt.
1. Bewegen Sie den Mauszeiger über die Regel, die Sie löschen möchten, und klicken Sie auf das X-Symbol. Die Regel wird sofort gelöscht.
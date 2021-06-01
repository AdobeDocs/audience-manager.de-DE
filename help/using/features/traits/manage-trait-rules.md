---
description: Im Trait Builder können Sie mit dem Expression Builder Regeln erstellen und testen, die Anforderungen an die Zielgruppenqualifizierung festlegen. Regeln bestehen aus Schlüssel-Wert-Paaren wie "color == blue" oder "price &gt; 100". Vergleichsoperatoren stellen die Beziehung zwischen Schlüsseln und Werten her. Boolesche Ausdrücke bestimmen die Beziehung zwischen Regelgruppen.
seo-description: Im Trait Builder können Sie mit dem Expression Builder Regeln erstellen und testen, die Anforderungen an die Zielgruppenqualifizierung festlegen. Regeln bestehen aus Schlüssel-Wert-Paaren wie "color == blue" oder "price &gt; 100". Vergleichsoperatoren stellen die Beziehung zwischen Schlüsseln und Werten her. Boolesche Ausdrücke bestimmen die Beziehung zwischen Regelgruppen.
seo-title: Verwalten von Eigenschaftsregeln
solution: Audience Manager
title: Verwalten von Eigenschaftsregeln
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: 'Eigenschaften '
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 1%

---

# Verwalten von Eigenschaftsregeln {#managing-trait-rules}

In [!UICONTROL Trait Builder] können Sie mit [!UICONTROL Expression Builder] Regeln erstellen und testen, die Anforderungen an die Zielgruppenqualifizierung festlegen. Regeln bestehen aus Schlüssel-Wert-Paaren wie `color == blue` oder `price > 100`. Vergleichsoperatoren stellen die Beziehung zwischen Schlüsseln und Werten her. [!DNL Boolean] -Ausdrücke bestimmen die Beziehung zwischen Regelgruppen.

<!-- c_tb_rules.xml -->

## Beschreibung der Hauptfunktionen für Signalregeln

![](assets/manage-trait-rules.png)

1. Die Registerkarten **[!UICONTROL Expression Builder]** oder **[!UICONTROL Code View]** bieten einen Überblick über die Regeln in Ihrer Eigenschaft. Im Tab **[!UICONTROL Expression Builder]** können Sie Regeln mit Feldern und Dropdown-Menüs erstellen. Mit **[!UICONTROL Code View]** können Sie Regeln erstellen, indem Sie diese Ausdrücke manuell als Code schreiben. Die obige Abbildung zeigt eine einfache Eigenschaft, die aus einem Signal besteht, das Daten für eine qualifizierende Bedingung auswertet, bei der ein Produktschlüssel einem bestimmten Wert entspricht, in diesem Fall `color == "blue"`.

1. Die Felder und Steuerelemente in diesem Abschnitt ermöglichen Ihnen das Erstellen von Signalen aus Schlüssel-Wert-Paaren und das Festlegen der Beziehung zwischen ihnen und einem Vergleichsoperator. Ein Schlüssel, ein Operator und ein Wert sind erforderlich.
1. Mit [!UICONTROL Data Explorer Options] können Sie Eigenschaftsrealisierungen für Ihre Signale aufstocken.

   >[!NOTE]
   >
   >Diese Option ist nur für [!UICONTROL Data Explorer] -Kunden verfügbar. Weitere Informationen erhalten Sie von Ihrem Adobe Consultant.

1. Dieser Abschnitt zeigt Ihnen eine Schätzung der Eigenschaftsrealisierungen für die letzten 7 Tage für die in [!UICONTROL Expression Builder] definierten Signale für aufgestockte und nicht aufgestockte Eigenschaften.

   >[!NOTE]
   >
   >Diese Option ist nur für [!UICONTROL Data Explorer] -Kunden verfügbar. Weitere Informationen erhalten Sie von Ihrem Adobe Consultant.

1. Mit den Testfeldern können Sie Kombinationen aus Signalregeln oder den [!DNL URL]s validieren, die Sie beim Senden von Daten an Audience Manager verwenden möchten.

## Erstellen einer Eigenschaftsregel {#create-trait-rule}

Regeln (oder Ausdrücke) bestehen aus einzelnen oder Gruppen von Schlüssel-Wert-Paaren. Vergleichsoperatoren legen die Beziehung zwischen Schlüssel-Wert-Paaren fest. Um eine Regel zu erstellen, geben Sie einen Schlüssel und einen Wert an, wählen Sie einen Operator aus und klicken Sie auf **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Füllen Sie die erforderlichen Felder im Abschnitt **[!UICONTROL Basic Information]** *aus, bevor* Eigenschaftenregeln erstellt werden.

1. Erweitern Sie den Abschnitt **[!UICONTROL Trait Expression]** und geben Sie einen Schlüssel- und einen Wertnamen ein. Dadurch wird ein *`signal`* erstellt.

   >[!NOTE]
   >
   >Fügen Sie das `c_`-Präfix (oder eine andere Benennungsregel) für die Schlüsselvariable ein, wenn Ihre Ereignisaufrufe Daten mit dieser Syntax an [!DNL Audience Manager] senden.

1. Wählen Sie einen [Vergleichsoperator](../../features/traits/trait-comparison-operators.md) aus der Dropdown-Liste **[!UICONTROL Operator]** aus. Der Vergleichsoperator wertet die Beziehung zwischen den Elementen in einem Signal aus.

   >[!NOTE]
   >
   >Der [!DNL Boolean] [!UICONTROL OR]-Operator stellt die Beziehung zwischen mehreren Signalen *innerhalb* einer Gruppe her und kann nicht geändert werden.

1. Klicken **[!UICONTROL Add Rule]**. Die gespeicherte Regel wird im Arbeitsbereich &quot;Eigenschaften&quot;über den Dateneingabefeldern angezeigt.

### Beispiel {#example-trait-rule}

Im folgenden Beispiel hat ein Benutzer eine neue Eigenschaftsregel erstellt, die auf der Produkt-ID basiert. Um diese Regel zu erstellen, hat der Benutzer den Schlüssel `productkey` bereitgestellt, der mit einem Gleichheitsoperator ( `==`) verknüpft ist, mit dem Wert `2093`.

![](assets/tb_sample_rule1.png)

Durch Klicken auf **[!UICONTROL Add Rule]** wird die Eigenschaft gespeichert und in den Arbeitsbereich [!UICONTROL Expression Builder] verschoben.

![](assets/tb_sample_rule2.png)

## Erstellen einer neuen Regelgruppe {#create-rule-group}

Dieser Vorgang beschreibt, wie Sie eine neue Regelgruppe erstellen.

<!-- t_tb_new_rule_group.xml -->

Ihre Eigenschaft muss mindestens zwei Regeln enthalten, bevor Sie eine neue Regelgruppe erstellen können.

1. Bewegen Sie den Cursor über die Regel, die Sie verschieben möchten, um sie hervorzuheben.
1. Bewegen Sie den Mauszeiger über den markierten Regelrahmen.

   Dadurch wird die Regel automatisch von der aktuellen Gruppe getrennt und in eine neue Gruppe verschoben.

   >[!NOTE]
   >
   >Ziehen Sie eine Regel zurück in die ursprüngliche Gruppe, wenn Sie sie unbeabsichtigt verschieben.

1. Wählen Sie einen [!DNL Boolean] -Operator ([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) aus dem Dropdown-Menü aus, um die Beziehung zwischen den Regelgruppen festzulegen.

## Verschieben von Regeln zwischen Gruppen {#move-rules-between-groups}

Um eine Regel zu verschieben, klicken Sie auf und ziehen Sie sie in eine andere Gruppe.

## Eine Eigenschaft bearbeiten {#edit-trait}

Dieser Vorgang beschreibt, wie Sie eine Eigenschaft bearbeiten.

<!-- t_tb_edit.xml -->

1. Bewegen Sie im Dashboard [!UICONTROL Traits] den Mauszeiger über die Spalte **[!UICONTROL Actions]** für die Eigenschaft, die Sie bearbeiten möchten. Dadurch werden die Symbole für die Verwaltung von Eigenschaften angezeigt.
1. Klicken Sie auf den Stift, um die Eigenschaft zu bearbeiten.

   ![](assets/tb_edit_trait.png)

## Eine Eigenschaftsregel löschen {#delete-trait}

Dieser Vorgang beschreibt, wie Sie eine Eigenschaftsregel löschen.

<!-- t_tb_delete_rule.xml -->

1. Bewegen Sie im Dashboard [!UICONTROL Traits] den Mauszeiger über die [!UICONTROL Actions]-Spalten für die Eigenschaft, die Sie bearbeiten möchten, und klicken Sie auf das Stiftsymbol. Dadurch werden die Symbole für die Verwaltung von Eigenschaften angezeigt.
1. Erweitern Sie den Abschnitt [!UICONTROL Trait Expression] .
1. Bewegen Sie den Mauszeiger über die Regel, die Sie löschen möchten, und klicken Sie auf das X-Symbol. Die Regel wird sofort gelöscht.

>[!MORELIKETHIS]
>
>* [Neue Regelgruppe erstellen](../../features/traits/manage-trait-rules.md#create-rule-group)
* [Verschieben von Regeln zwischen Gruppen](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
* [Erstellen einer Eigenschaftsregel](../../features/traits/manage-trait-rules.md#create-trait-rule)
* [Eine Eigenschaftsregel löschen](../../features/traits/manage-trait-rules.md#delete-trait)
* [Verschieben von Regeln zwischen Gruppen](../../features/traits/manage-trait-rules.md#move-rules-between-groups)


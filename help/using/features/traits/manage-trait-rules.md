---
description: In Trait Builder können Sie mit dem Ausdrucksgenerator Regeln erstellen und testen, die Anforderungen an die Zielgruppenqualifizierung festlegen. Regeln bestehen aus Schlüssel-Wert-Paaren wie „Farbe == Blau“ oder „Preis &gt; 100“. Vergleichsoperatoren stellen die Beziehung zwischen Schlüsseln und Werten her. Boolesche Ausdrücke bestimmen die Beziehung zwischen Regelgruppen.
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price &gt; 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: Verwalten von Eigenschaftsregeln
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 0%

---

# Verwalten von Eigenschaftsregeln {#managing-trait-rules}

[!UICONTROL Trait Builder] können Sie mit dem [!UICONTROL Expression Builder] Regeln erstellen und testen, die die Anforderungen an die Zielgruppen-Qualifizierung festlegen. Regeln bestehen aus Schlüssel-Wert-Paaren wie `color == blue` oder `price > 100`. Vergleichsoperatoren stellen die Beziehung zwischen Schlüsseln und Werten her. [!DNL Boolean] Ausdrücke bestimmen die Beziehung zwischen Regelgruppen.

<!-- c_tb_rules.xml -->

## Beschreibung der wichtigsten Signalregelfunktionen

![](assets/manage-trait-rules.png)

1. Die Registerkarten **[!UICONTROL Expression Builder]** oder **[!UICONTROL Code View]** bieten einen Überblick über die Regeln in Ihrem Merkmal. Auf der Registerkarte **[!UICONTROL Expression Builder]** können Sie Regeln mit Feldern und Dropdown-Menüs erstellen. Mit dem **[!UICONTROL Code View]** können Sie Regeln erstellen, indem Sie diese Ausdrücke manuell als Code schreiben. Die obige Abbildung zeigt eine einfache Eigenschaft, die aus einem Signal besteht, das Daten für eine qualifizierte Bedingung auswertet, bei der ein Produktschlüssel einem bestimmten Wert entspricht, in diesem Fall `color == "blue"`.

1. Mit den Feldern und Steuerelementen in diesem Abschnitt können Sie Signale aus Schlüssel-Wert-Paaren erstellen und die Beziehung zwischen ihnen mit einem Vergleichsoperator festlegen. Schlüssel, Operator und Wert sind erforderlich.
1. Mit den [!UICONTROL Data Explorer Options] können Sie die Realisierungen von Eigenschaften für Ihre Signale aufstocken.

   >[!NOTE]
   >
   >Diese Option steht nur [!UICONTROL Data Explorer] Kunden zur Verfügung. Weitere Informationen erhalten Sie von Ihrem Adobe-Berater.

1. Dieser Abschnitt zeigt eine Schätzung der Realisierungen von Eigenschaften für die letzten 7 Tage für die in der [!UICONTROL Expression Builder] definierten Signale, für aufgestockte und nicht aufgestockte Eigenschaften.

   >[!NOTE]
   >
   >Diese Option steht nur [!UICONTROL Data Explorer] Kunden zur Verfügung. Weitere Informationen erhalten Sie von Ihrem Adobe-Berater.

1. Mit den Testfeldern können Sie Kombinationen von Signalregeln oder die [!DNL URL] überprüfen, die Sie beim Senden von Daten an Audience Manager verwenden möchten.

## Erstellen einer Eigenschaftsregel {#create-trait-rule}

Regeln (oder Ausdrücke) bestehen aus einzelnen Schlüssel-Wert-Paaren oder Gruppen von Schlüssel-Wert-Paaren. Vergleichsoperatoren legen die Beziehung zwischen Schlüssel-Wert-Paaren fest. Um eine Regel zu erstellen, geben Sie einen Schlüssel und einen Wert an, wählen Sie einen Operator aus und klicken Sie auf **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Füllen Sie die erforderlichen Felder im Abschnitt **[!UICONTROL Basic Information]** aus *erstellen* Eigenschaftsregeln.

1. Erweitern Sie den Abschnitt **[!UICONTROL Trait Expression]** und geben Sie einen Schlüssel- und einen Wertnamen ein. Dadurch wird ein *`signal`* erstellt.

   >[!NOTE]
   >
   >Schließen Sie das `c_` (oder eine andere Namenskonvention) für die Schlüsselvariable ein, wenn Ihre Ereignisaufrufe Daten an [!DNL Audience Manager] senden, die diese Syntax verwenden.

1. Wählen Sie [Vergleichsoperator](../../features/traits/trait-comparison-operators.md) aus der Dropdown-Liste **[!UICONTROL Operator]** aus. Der Vergleichsoperator wertet die Beziehung zwischen den Elementen in einem Signal aus.

   >[!NOTE]
   >
   >Der [!DNL Boolean] [!UICONTROL OR] stellt die Beziehung zwischen mehreren Signalen *innerhalb* Gruppe her und kann nicht geändert werden.

1. Klicken Sie auf **[!UICONTROL Add Rule]**. Die gespeicherte Regel wird im Arbeitsbereich „Eigenschaften“ über den Dateneingabefeldern angezeigt.

### Beispiel {#example-trait-rule}

Im folgenden Beispiel hat ein Benutzer eine neue Eigenschaftsregel basierend auf der Produkt-ID erstellt. Um diese Regel zu erstellen, hat der Benutzer den Schlüssel bereitgestellt, der mit einem Equals-Operator (`productkey`) mit dem Wert `==` verknüpft `2093`.

![](assets/tb_sample_rule1.png)

Durch Klicken auf **[!UICONTROL Add Rule]** wird die Eigenschaft gespeichert und in den [!UICONTROL Expression Builder] Workspace verschoben.

![](assets/tb_sample_rule2.png)

## Erstellen einer neuen Regelgruppe {#create-rule-group}

In diesem Verfahren wird das Erstellen einer neuen Regelgruppe beschrieben.

<!-- t_tb_new_rule_group.xml -->

Ihr Merkmal muss mindestens zwei Regeln enthalten, bevor Sie eine neue Regelgruppe erstellen können.

1. Bewegen Sie den Cursor über die Regel, die Sie verschieben möchten, um sie zu markieren.
1. Bewegen Sie den Mauszeiger über den hervorgehobenen Regelrahmen.

   Dadurch wird die Regel automatisch von ihrer aktuellen Gruppe getrennt und in eine neue Gruppe verschoben.

   >[!NOTE]
   >
   >Ziehen Sie eine Regel zurück in die ursprüngliche Gruppe, wenn Sie sie unbeabsichtigt verschieben.

1. Wählen Sie einen [!DNL Boolean] Operator ([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) aus dem Dropdown-Menü aus, um die Beziehung zwischen den Regelgruppen festzulegen.

## Regeln zwischen Gruppen verschieben {#move-rules-between-groups}

Um eine Regel zu verschieben, klicken Sie darauf und ziehen Sie sie in eine andere Gruppe.

## Bearbeiten einer Eigenschaft {#edit-trait}

Dieses Verfahren beschreibt, wie man eine Eigenschaft bearbeitet.

<!-- t_tb_edit.xml -->

1. Bewegen Sie im [!UICONTROL Traits]-Dashboard den Mauszeiger über die Spalte **[!UICONTROL Actions]** für die Eigenschaft, die Sie bearbeiten möchten. Dadurch werden die Symbole für das Eigenschaftenmanagement angezeigt.
1. Klicken Sie auf den Stift, um die Eigenschaft zu bearbeiten.

   ![](assets/tb_edit_trait.png)

## Löschen einer Eigenschaftsregel {#delete-trait}

In diesem Verfahren wird beschrieben, wie Sie eine Eigenschaftsregel löschen.

<!-- t_tb_delete_rule.xml -->

1. Bewegen Sie im [!UICONTROL Traits]-Dashboard den Mauszeiger über die [!UICONTROL Actions] Spalten für die Eigenschaft, die Sie bearbeiten möchten, und klicken Sie auf das Stiftsymbol. Dadurch werden die Symbole für das Eigenschaftenmanagement angezeigt.
1. Erweitern Sie den Abschnitt [!UICONTROL Trait Expression] .
1. Bewegen Sie den Mauszeiger über die Regel, die Sie löschen möchten, und klicken Sie auf das X-Symbol. Die Regel wird sofort gelöscht.

>[!MORELIKETHIS]
>
>* [Erstellen Sie eine neue Regelgruppe](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Regeln zwischen Gruppen verschieben](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Erstellen einer Eigenschaftsregel](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Löschen einer Eigenschaftsregel](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Regeln zwischen Gruppen verschieben](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

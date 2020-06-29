---
description: In diesem Artikel werden die Benennungskonventionen beschrieben, die von der Schlüsselvariablen in einem Schlüssel-Wert-Paar verwendet werden.
seo-description: In diesem Artikel werden die Benennungskonventionen beschrieben, die von der Schlüsselvariablen in einem Schlüssel-Wert-Paar verwendet werden.
seo-title: Namensanforderungen für Schlüsselvariablen
solution: Audience Manager
title: Namensanforderungen für Schlüsselvariablen
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---


# Namensanforderungen für Schlüsselvariablen {#name-requirements-for-key-variables}

In diesem Artikel werden die Benennungskonventionen beschrieben, die von der Schlüsselvariablen in einem Schlüssel-Wert-Paar verwendet werden.

## Namensanforderungen für Schlüssel

<!-- c_tb_key_name_requirements.xml -->

Der Name [!UICONTROL Expression Builder]einer Schlüsselvariablen in einem Schlüsselwertpaar kann aus einer beliebigen Anzahl von Ziffern gefolgt von 1 (oder mehr) Buchstaben, einem Bindestrich, einem Unterstrich und weiteren Ziffern bestehen.

* Gültige Schlüsselnamen: `price123`, `123price`, `price-123`, `c_price123`.

* Ungültige Schlüsselnamen: `123`, `price!123`.

## Präfix der Schlüsselvariablen mit `c_`

Das `c_` Präfix ist *immer* erforderlich, wenn die Parameter, die Daten über eine Ereignis-Aufruf-URL senden, diese Syntax verwenden.
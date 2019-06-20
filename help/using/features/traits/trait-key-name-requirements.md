---
description: In diesem Artikel werden die Benennungskonventionen beschrieben, die von der Schlüsselvariable in einem Schlüssel-Wert-Paar verwendet werden.
seo-description: In diesem Artikel werden die Benennungskonventionen beschrieben, die von der Schlüsselvariable in einem Schlüssel-Wert-Paar verwendet werden.
seo-title: Namensanforderungen für Schlüsselvariablen
solution: Audience Manager
title: Namensanforderungen für Schlüsselvariablen
uuid: fa 72 e 732-895 d -4 cf 6-bea 0-66 b 404 c 2 b 059
translation-type: tm+mt
source-git-commit: bdbc2525a13eb04898b0a844ba478cde07e83252

---


# Namensanforderungen für Schlüsselvariablen {#name-requirements-for-key-variables}

In diesem Artikel werden die Benennungskonventionen beschrieben, die von der Schlüsselvariable in einem Schlüssel-Wert-Paar verwendet werden.

## Namensanforderungen für Schlüssel

<!-- c_tb_key_name_requirements.xml -->

Der [!UICONTROL Expression Builder]Name einer Schlüsselvariable in einem Schlüssel-Wert-Paar kann aus einer beliebigen Anzahl von Ziffern gefolgt von 1 (oder mehr) Buchstaben, einem Bindestrich, einem Unterstrich und weiteren Ziffern bestehen.

* Gültige Schlüsselnamen: `price123``123price``price-123``c_price123`.

* Ungültige Schlüsselnamen: `123``price!123`.

## Präfix-Key-Variablen mit `c_`

Das `c_` Präfix ist *immer* erforderlich, wenn die Parameter, die Daten für eine Ereignisaufruf-URL senden, diese Syntax verwenden.
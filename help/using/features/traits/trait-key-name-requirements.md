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


# Name Requirements for Key Variables {#name-requirements-for-key-variables}

In diesem Artikel werden die Benennungskonventionen beschrieben, die von der Schlüsselvariable in einem Schlüssel-Wert-Paar verwendet werden.

## Namensanforderungen für Schlüssel

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], the name of a key variable in a key-value pair can consist of any number of digits followed by 1 (or more) letters, a dash, an underscore, and additional digits.

* Valid key names: `price123`, `123price`, `price-123`, `c_price123`.

* Invalid key names: `123`, `price!123`.

## Prefixing Key Variables with `c_`

The `c_` prefix is *always* required if the parameters that send in data on an event call URL use that syntax.
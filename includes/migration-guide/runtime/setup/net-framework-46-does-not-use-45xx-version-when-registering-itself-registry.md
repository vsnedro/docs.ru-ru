---
ms.openlocfilehash: a9011514c7c4393ec44de2c7fae88768cdccf435
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496479"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a>.NET Framework 4.6 не использует версию 4.5.x.x для собственной регистрации в реестре

#### <a name="details"></a>Подробнее

Ключ версии, установленный в реестре (<code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) для платформы .NET Framework 4.6, ожидаемо начинается с "4.6", а не с "4.5". Приложения, которые используют эти разделы реестра для определения установленных на компьютере версий .NET Framework, следует обновить таким образом, чтобы понимать, что 4.6 — это новая возможная версия, совместимая с предыдущими выпусками 4.5.x.

#### <a name="suggestion"></a>Предложение

Обновите приложения, проверяющие установку версию .NET Framework 4.5 в соответствующих разделах реестра, так, чтобы они принимали версию 4.6.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.6|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->

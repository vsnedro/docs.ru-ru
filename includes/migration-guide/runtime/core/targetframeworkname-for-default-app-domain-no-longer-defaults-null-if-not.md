---
ms.openlocfilehash: 4e685722271a8079e727ea9c2e0e501f68b30fc9
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496962"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>TargetFrameworkName для домена приложения по умолчанию больше не принимает значение NULL по умолчанию, если оно не задано

#### <a name="details"></a>Подробнее

Свойство <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> имело ранее значение NULL в домене приложения по умолчанию, если оно не было задано явно. Начиная с версии 4.6, свойство <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> для домена приложения по умолчанию будет иметь значение по умолчанию, полученное из свойства TargetFrameworkAttribute (если оно доступно). Домены приложений не по умолчанию будут по-прежнему наследовать свойство <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> от домена приложения по умолчанию (который не будет по умолчанию иметь значение NULL в 4.6), если оно явно не переопределено.

#### <a name="suggestion"></a>Предложение

Следует обновить код так, чтобы он не зависел от <xref:System.AppDomainSetup.TargetFrameworkName>, принимающего п умолчанию значение NULL. Если требуется, чтобы свойство продолжало принимать значение NULL, ему можно явно присвоить это значение.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.6|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.AppDomainSetup.TargetFrameworkName`

-->

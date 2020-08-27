---
ms.openlocfilehash: ccd056f23d26e6cce4cc691542784792bffe9fc6
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558191"
---
### <a name="environmentosversion-returns-the-correct-operating-system-version"></a>Environment.OSVersion возвращает правильную версию операционной системы

<xref:System.Environment.OSVersion?displayProperty=nameWithType> возвращает фактическую версию операционной системы (ОС), а не, например, ту ОС, которая выбрана для совместимости приложений.

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET <xref:System.Environment.OSVersion?displayProperty=nameWithType> возвращает версию ОС, которая может быть неверной, если приложение работает в режиме совместимости Windows. Дополнительные сведения см. в [примечаниях к функции GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).

Начиная с .NET 5.0 <xref:System.Environment.OSVersion?displayProperty=nameWithType> возвращает фактическую версию операционной системы.

#### <a name="reason-for-change"></a>Причина изменения

Пользователи этого свойства предполагают, что оно будет возвращать фактическую версию операционной системы. Большинство приложений .NET не указывают поддерживаемую версию в манифесте приложения и поэтому получают поддерживаемую по умолчанию версию из узла dotnet. В результате оболочка совместимости редко применяется для работающего приложения. Когда Windows выпускает новую версию, а более старый узел dotnet по-прежнему используется, эти приложения могут получить неверную версию ОС. Возврат фактической версии более соответствует ожиданиям разработчиков этого API.

#### <a name="version-introduced"></a>Представленная версия

5.0

#### <a name="recommended-action"></a>Рекомендованное действие

Проверьте и протестируйте код, который использует <xref:System.Environment.OSVersion?displayProperty=nameWithType>, чтобы убедиться, что он ведет себя должным образом.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Environment.OSVersion`

-->

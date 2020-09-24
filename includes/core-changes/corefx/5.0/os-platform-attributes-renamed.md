---
ms.openlocfilehash: 8c739d8f355ffa6a6e09cbe4c531b188acede5bd
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720311"
---
### <a name="osplatform-attributes-renamed-or-removed"></a>Атрибуты OSPlatform переименованы или удалены

Следующие атрибуты, появившиеся в предварительной версии 8 .NET 5.0, были удалены или переименованы: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute` и `ObsoletedInOSPlatformAttribute`.

#### <a name="change-description"></a>Описание изменений

В предварительной версии 8 .NET 5.0 в пространстве имен <xref:System.Runtime.Versioning> появились следующие атрибуты:

- `MinimumOSPlatformAttribute`
- `RemovedInOSPlatformAttribute`
- `ObsoletedInOSPlatformAttribute`

Если в предварительной версии 8 .NET 5.0 проект предназначен для использования в конкретной ОС .NET 5 с помощью [моникера целевой платформы](../../../../docs/standard/frameworks.md), например `net5.0-windows`, сборка добавляет атрибут `System.Runtime.Versioning.MinimumOSPlatformAttribute` уровня сборки.

В .NET 5.0 RC1 атрибут `ObsoletedInOSPlatformAttribute` был удален, а атрибуты `MinimumOSPlatformAttribute` и `RemovedInOSPlatformAttribute` переименованы следующим образом.

| Имя предварительной версии 8 | Имя RC1 и более поздних версий |
| - | - |
| `MinimumOSPlatformAttribute` | <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> |
| `RemovedInOSPlatformAttribute` | <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> |

Если в .NET 5.0 RC1 и более поздних версиях проект предназначен для использования в конкретной ОС .NET 5 с помощью [моникера целевой платформы](../../../../docs/standard/frameworks.md), например `net5.0-windows`, сборка добавляет атрибут <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> уровня сборки.

#### <a name="reason-for-change"></a>Причина изменения

В предварительной версии 8 .NET 5.0 в <xref:System.Runtime.Versioning> появились атрибуты для указания поддерживаемых платформ для API-интерфейсов. [Анализатор совместимости платформ](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) использует эти атрибуты для создания предупреждений сборки, когда API-интерфейсы, зависящие от платформы, работают на платформах, их не поддерживающих.

В .NET 5.0 RC1 в анализатор совместимости платформ была добавлена дополнительная возможность исключения платформы. Эта функция позволяет помечать API-интерфейсы как полностью не поддерживаемые на платформах ОС. Она предлагает изменить атрибуты или использовать более подходящие имена. `ObsoletedInOSPlatformAttribute` был удален, так как он больше не требуется.

#### <a name="version-introduced"></a>Представленная версия

5.0 (RC1)

#### <a name="recommended-action"></a>Рекомендованное действие

При изменении целевой платформы проекта с предварительной версии 8 .NET 5.0 на .NET 5.0 RC1 могут возникать ошибки сборки или времени выполнения. Например, переименование `MinimumOSPlatformAttribute`, скорее всего, приведет к появлению ошибок, поскольку атрибут применяется к сборкам для конкретных платформ во время сборки, а старые артефакты сборки по-прежнему ссылаются на старое имя API.

Примеры ошибок во время сборки:

- **Ошибка CS0246. Не удалось найти тип или имя пространства имен "MinimumOSPlatformAttribute" (возможно, отсутствует директива using или ссылка на сборку).**
- **Ошибка CS0246. Не удалось найти тип или имя пространства имен "RemovedInOSPlatformAttribute" (возможно, отсутствует директива using или ссылка на сборку).**
- **Ошибка CS0246. Не удалось найти тип или имя пространства имен "ObsoletedInOSPlatformAttribute" (возможно, отсутствует директива using или ссылка на сборку).**

Пример ошибки во время выполнения:

**Необработанное исключение. System.TypeLoadException: Не удалось загрузить тип "System.Runtime.Versioning.MinimumOSPlatformAttribute"из сборки "System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a".**

Чтобы устранить эти ошибки, выполните следующие действия.

- Обновите все ссылки `MinimumOSPlatformAttribute` до <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.
- Обновите все ссылки `RemovedInOSPlatformAttribute` до <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.
- Удалите все ссылки на `ObsoletedInOSPlatformAttribute`.
- Перестройте проект (или выполните очистку и сборку), чтобы удалить старые артефакты сборки.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- `System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `System.Runtime.Versioning.RemovedInOSPlatformAttribute`

<!--

#### Affected APIs

- `T:System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `T:System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `T:System.Runtime.Versioning.RemovedInOSPlatformAttribute`

-->

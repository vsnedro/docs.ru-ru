---
title: Критические изменения во взаимодействии
description: Предоставляет перечень критических изменений во взаимодействии между .NET Core и .NET 5.0 и более поздних версий.
ms.date: 06/23/2020
ms.openlocfilehash: a38fb1837e565be33f8ae1119480c8f1ae848ab0
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438040"
---
# <a name="interop-breaking-changes"></a>Критические изменения во взаимодействии

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленная версия |
| - | :-: |
| [Приведение вызываемой оболочки времени выполнения к интерфейсу `InterfaceIsIInspectable` вызывает исключение PlatformNotSupportedException](#casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception) | 5.0 |
| [Отсутствует проверка суффикса A/W на платформах, отличных от Windows](#no-aw-suffix-probing-on-non-windows-platforms) | 5.0 |
| [Из .NET удалена встроенная поддержка WinRT](#built-in-support-for-winrt-is-removed-from-net) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [casting-rcw-to-inspectable-interface-throws-exception](../../../includes/core-changes/interop/5.0/casting-rcw-to-inspectable-interface-throws-exception.md)]

***

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***

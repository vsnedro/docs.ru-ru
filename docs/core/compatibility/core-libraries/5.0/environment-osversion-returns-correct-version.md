---
title: Критическое изменение. Environment.OSVersion возвращает правильную версию операционной системы
description: Сведения о критическом изменении .NET 5.0 в основных библиотеках .NET, где Environment.OSVersion возвращает фактическую версию операционной системы, а не, например, ОС, выбранную для совместимости приложений.
ms.date: 11/01/2020
ms.openlocfilehash: b78ca1c7be50f76b99b5558a976d8f00e2f560c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760287"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a>Environment.OSVersion возвращает правильную версию операционной системы

<xref:System.Environment.OSVersion?displayProperty=nameWithType> возвращает фактическую версию операционной системы (ОС), а не, например, ту ОС, которая выбрана для совместимости приложений.

## <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET <xref:System.Environment.OSVersion?displayProperty=nameWithType> возвращает версию ОС, которая может быть неверной, если приложение работает в режиме совместимости Windows. Дополнительные сведения см. в [примечаниях к функции GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).

Начиная с .NET 5.0 <xref:System.Environment.OSVersion?displayProperty=nameWithType> возвращает фактическую версию операционной системы.

## <a name="reason-for-change"></a>Причина изменения

Пользователи этого свойства предполагают, что оно будет возвращать фактическую версию операционной системы. Большинство приложений .NET не указывают поддерживаемую версию в манифесте приложения и поэтому получают поддерживаемую по умолчанию версию из узла dotnet. В результате оболочка совместимости редко применяется для работающего приложения. Когда Windows выпускает новую версию, а более старый узел dotnet по-прежнему используется, эти приложения могут получить неверную версию ОС. Возврат фактической версии более соответствует ожиданиям разработчиков этого API.

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="recommended-action"></a>Рекомендованное действие

Проверьте и протестируйте код, который использует <xref:System.Environment.OSVersion?displayProperty=nameWithType>, чтобы убедиться, что он ведет себя должным образом.

## <a name="affected-apis"></a>Затронутые API

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->

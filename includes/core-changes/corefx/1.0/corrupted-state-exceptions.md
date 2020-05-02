---
ms.openlocfilehash: 394f2daebad7b6af94bee4d7876796e87fe8ab19
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135634"
---
### <a name="handling-corrupted-state-exceptions-is-not-supported"></a>Обработка исключений поврежденного состояния не поддерживается

Обработка исключений поврежденного состояния в .NET Core не поддерживается.

#### <a name="change-description"></a>Описание изменений

Ранее исключения поврежденного состояния процесса могли быть перехвачены и обработаны обработчиками исключений управляемого кода, например с помощью инструкции [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) в C#.

Начиная с .NET Core 1.0 исключения поврежденного состояния процесса не могут обрабатываться управляемым кодом. Среда CLR не доставляет исключения поврежденного состояния процесса в управляемый код.

#### <a name="version-introduced"></a>Представленная версия

1.0

#### <a name="recommended-action"></a>Рекомендованное действие

Старайтесь исключить потребность в обработке исключений поврежденного состояния процесса, устраняя ситуации, которые вызывают подобные исключения. Если обработка исключений поврежденного состояния процесса совершенно необходима, напишите обработчик исключений в коде C или C++.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>
- [Элемент legacyCorruptedStateExceptionsPolicy](~/docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)

<!--

#### Affected APIs

- `T:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute`

-->

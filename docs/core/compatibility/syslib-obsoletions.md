---
title: Устаревшие компоненты в .NET 5 и более поздних версий
description: Сведения об API-интерфейсах, которые помечены как устаревшие в .NET 5.0 и более поздних версий и приводят к созданию предупреждений компилятора SYSLIB.
ms.date: 10/20/2020
ms.openlocfilehash: 13f5fb10cfe693ed621b3f45fc22e024875890c8
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333139"
---
# <a name="obsolete-features-in-net-5"></a>Устаревшие компоненты в .NET 5 и более поздних версий

Начиная с версии .NET 5.0, некоторые помеченные устаревшими API используют два новых свойства для <xref:System.ObsoleteAttribute>.

- Свойство <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> указывает компилятору создавать предупреждения сборки с помощью пользовательского идентификатора диагностики. Пользовательский идентификатор позволяет отключать предупреждения об устаревших элементах отдельно друг от друга. В случае с устаревшими элементами в .NET 5 и более поздних версий пользовательский идентификатор диагностики имеет формат `SYSLIBxxxx`.

- Свойство <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> указывает компилятору включить URL для получения дополнительных сведений об устаревшем элементе.

Если вы получаете предупреждения или ошибки сборки из-за использования устаревшего API, следуйте указаниям для идентификатора диагностики в разделе [Справочник](#reference). Предупреждения или ошибки об этих устаревших элементах *нельзя* отключить с помощью [стандартного идентификатора диагностики (CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md) для устаревших типов или членов. Используйте вместо него пользовательский идентификатор диагностики `SYSLIBxxxx`. Дополнительные сведения см. в разделе [Отключение предупреждений](#suppress-warnings).

## <a name="reference"></a>Справочник

В следующей таблице представлен индекс устаревших элементов `SYSLIBxxxx` в .NET 5 и более поздних версий.

| ИД диагностики | Описание |
| - | - |
| [SYSLIB0001](syslib0001.md) | Кодировка UTF-7 небезопасна и не должна использоваться. Вместо нее рекомендуется использовать UTF-8. |
| [SYSLIB0002](syslib0002.md) | <xref:System.Security.Permissions.PrincipalPermissionAttribute> не учитывается средой выполнения и не должен использоваться. |
| [SYSLIB0003](syslib0003.md) | Управление доступом для кода (CAS) не поддерживается или не учитывается средой выполнения. |
| [SYSLIB0004](syslib0004.md) | Функция области ограниченного выполнения (CER) не поддерживается. |
| [SYSLIB0005](syslib0005.md) | Глобальный кэш сборок не поддерживается. |
| [SYSLIB0006](syslib0006.md) | <xref:System.Threading.Thread.Abort?displayProperty=nameWithType> не поддерживается и вызывает <xref:System.PlatformNotSupportedException>. |
| [SYSLIB0007](syslib0007.md) | Реализации этого алгоритма шифрования по умолчанию не поддерживается. |
| [SYSLIB0008](syslib0008.md) | API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> не поддерживается и вызывает <xref:System.PlatformNotSupportedException>. |
| [SYSLIB0009](syslib0009.md) | Методы <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> и <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> не поддерживаются и вызывают <xref:System.PlatformNotSupportedException>. |
| [SYSLIB0010](syslib0010.md) | Некоторые API удаленного взаимодействия не поддерживаются и вызывают <xref:System.PlatformNotSupportedException>. |
| [SYSLIB0011](syslib0011.md) | Сериализация <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> устарела и не должна использоваться. |
| [SYSLIB0012](syslib0012.md) | <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> и <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> включены только для обеспечения совместимости с .NET Framework. Взамен рекомендуется использовать <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>. |

## <a name="suppress-warnings"></a>Отключение предупреждений

Если вам необходимо использовать устаревшие API, а диагностика `SYSLIBxxxx` не возвращает ошибку, можно отключить предупреждение в коде или в файле проекта.

В коде:

```csharp
// Disable the warning.
#pragma warning disable SYSLIB0001
// Code that uses obsolete API.
...
// Re-enable the warning.
#pragma warning restore SYSLIB0001
```

Файл проекта:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
   <TargetFramework>net5.0</TargetFramework>
   <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
   <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
  </PropertyGroup>
</Project>
```

> [!NOTE]
> Таким образом отключается только конкретное предупреждение об устаревшем элементе. Любые другие предупреждения, в том числе и об устаревших элементах, не отключаются.

---
title: Критическое изменение. Blazor WebAssembly не поддерживает интерфейсы API System.Security.Cryptography
description: Сведения о критическом изменении в .NET 5.0, где интерфейсы API шифрования выдают исключение при запуске в браузере.
ms.date: 09/16/2020
ms.openlocfilehash: ec10fa777e91f641b5582378830536a0cfa8dd72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759650"
---
# <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a>Blazor WebAssembly не поддерживает интерфейсы API System.Security.Cryptography

API <xref:System.Security.Cryptography> выдают исключение <xref:System.PlatformNotSupportedException> при выполнении в браузере.

## <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET большинство API <xref:System.Security.Cryptography> были недоступны приложениям Blazor WebAssembly. Начиная с .NET 5.0, приложения Blazor WebAssembly предназначены для использования в полной контактной зоне API .NET 5, но из-за ограничений песочницы браузера поддерживаются не все API .NET 5. В .NET 5.0 и более поздних версиях неподдерживаемые API <xref:System.Security.Cryptography> выдают исключение <xref:System.PlatformNotSupportedException> при выполнении в WebAssembly.

> [!TIP]
> [Анализатор совместимости платформ](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) помечает все вызовы затронутых API при сборке проекта, который поддерживает платформу браузера. Этот анализатор выполняется по умолчанию в приложениях .NET 5.0 и более поздних версий.

## <a name="reason-for-change"></a>Причина изменения

Корпорация Майкрософт не может предоставить OpenSSL как зависимость в конфигурации Blazor WebAssembly. Мы пытались решить эту проблему, выполнив интеграцию с API `SubtleCrypto` браузера. К сожалению, это требует кардинального изменения API, что усложняет интеграцию.

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="recommended-action"></a>Рекомендованное действие

В настоящее время мы не можем предложить решение.

## <a name="affected-apis"></a>Затронутые API

Все API <xref:System.Security.Cryptography?displayProperty=fullName> за исключением следующих:

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

### Affected APIs

- `T:System.Security.Cryptography`

### Category

- ASP.NET Core
- Cryptography

-->

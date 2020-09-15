---
ms.openlocfilehash: 946e71f2f466664c8f9fcf4811288ce693a872eb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616292"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>Контрольные суммы рабочего процесса XAML для символов изменены с SHA1 на SHA256

#### <a name="details"></a>Подробнее

Для поддержки отладки в Visual Studio среда выполнения рабочего процесса создает контрольную сумму для файла XAML рабочего процесса, используя алгоритм хэширования. В .NET Framework 4.6.2 и более ранних версий для хэширования контрольной суммы рабочего процесса использовался алгоритм MD5, что приводило к проблемам в системах с поддержкой стандарта FIPS. Начиная с .NET Framework 4.7 алгоритм по умолчанию изменен на SHA-1. Начиная с .NET Framework 4.8 алгоритм по умолчанию изменен на SHA256.

#### <a name="suggestion"></a>Предложение

Если код не может загрузить экземпляры рабочих процессов или найти подходящие символы из-за ошибки контрольной суммы, попробуйте установить для параметра `AppContext` "Switch.System.Activities.UseSHA1HashForDebuggerSymbols" значение `true`. В коде:

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseSHA1HashForDebuggerSymbols", true);
```

Или в конфигурации:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true" />
  </runtime>
</configuration>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.8         |
| Type    | Изменение целевой платформы |

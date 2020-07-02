---
ms.openlocfilehash: 72d48d1daa85b6891c122f2fcc5279642253b926
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614839"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a>Контрольные суммы рабочего процесса переведены с MD5 на SHA1

#### <a name="details"></a>Подробнее

Для поддержки отладки в Visual Studio среда выполнения рабочего процесса создает контрольную сумму для экземпляра рабочего процесса, используя алгоритм хэширования. В .NET Framework 4.6.2 и более ранних версий для хэширования контрольной суммы рабочего процесса использовался алгоритм MD5, что приводило к проблемам в системах с поддержкой стандарта FIPS. Начиная с .NET Framework 4.7 используется алгоритм SHA-1. Если в коде материализованы эти контрольные суммы, они будут несовместимы.

#### <a name="suggestion"></a>Предложение

Если код не может загрузить экземпляры рабочих процессов из-за ошибки контрольной суммы, попробуйте установить для параметра &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; переключателя `AppContext` значение true. В коде:

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseMD5ForWFDebugger", true);
```

Или в конфигурации:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseMD5ForWFDebugger=true" />
  </runtime>
</configuration>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.7         |
| Type    | Изменение целевой платформы |

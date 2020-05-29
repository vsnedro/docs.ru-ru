---
title: Параметры конфигурации потоков
description: Сведения о параметрах времени выполнения, определяющих использование потоков для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 1c7c16993a07ef95223481791153b75ab2f61533
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761932"
---
# <a name="run-time-configuration-options-for-threading"></a>Параметры конфигурации времени выполнения для потоков

## <a name="cpu-groups"></a>Группы ЦП

- Определяет, выполняется ли автоматическое распределение потоков между группами ЦП.
- Если этот параметр не задан, потоки не распределяются между группами ЦП. Это эквивалентно присвоению значения `0`.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | Н/Д | Н/Д |
| **Переменная среды** | `COMPlus_Thread_UseAllCpuGroups` | `0` — отключено<br/>`1` — включено |

## <a name="minimum-threads"></a>Минимальное число потоков

- Указывает минимальное число потоков для рабочего пула потоков.
- Соответствует методу <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MinThreads` | Целочисленное значение, представляющее минимальное число потоков. |
| **Свойство MSBuild** | `ThreadPoolMinThreads` | Целочисленное значение, представляющее минимальное число потоков. |
| **Переменная среды** | Н/Д | Н/Д |

### <a name="examples"></a>Примеры

Файл *runtimeconfig.json*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

Файл проекта:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a>Максимальное число потоков

- Указывает максимальное число потоков для рабочего пула потоков.
- Соответствует методу <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MaxThreads` | Целочисленное значение, представляющее максимальное число потоков. |
| **Свойство MSBuild** | `ThreadPoolMaxThreads` | Целочисленное значение, представляющее максимальное число потоков. |
| **Переменная среды** | Н/Д | Н/Д |

### <a name="examples"></a>Примеры

Файл *runtimeconfig.json*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

Файл проекта:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```

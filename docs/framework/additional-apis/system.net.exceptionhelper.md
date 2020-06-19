---
title: Класс Ексцептионхелпер (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ExceptionHelper
- System.Net.ExceptionHelper.WebPermissionUnrestricted
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 14a6172f7a0321ba9b2dd1744799017271c4332c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990518"
---
# <a name="exceptionhelper-class"></a>Класс Ексцептионхелпер

Предоставляет исключения со стандартизованными сообщениями об ошибках. Этот класс не может быть унаследован.

```csharp
internal static class ExceptionHelper
```

> [!WARNING]
> Этот класс является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.

## <a name="webpermissionunrestricted-field"></a>Поле Вебпермиссионунрестриктед

Указывает, что приложение может подключаться к ресурсам Интернета.

```csharp
internal static readonly WebPermission WebPermissionUnrestricted
```

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)

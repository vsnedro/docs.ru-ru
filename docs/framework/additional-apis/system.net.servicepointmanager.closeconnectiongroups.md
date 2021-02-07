---
description: 'Дополнительные сведения о методе: ServicePointManager. Клосеконнектионграупс'
title: ServicePointManager. Клосеконнектионграупс, метод (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.CloseConnectionGroups
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 8cd1a1f0f4dbdaeaee117e6a7ae4219680363a6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699562"
---
# <a name="servicepointmanagercloseconnectiongroups-method"></a>ServicePointManager. Клосеконнектионграупс, метод

Выполняет перебор всех точек обслуживания и закрывает группы соединений с указанным именем.

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> Этот метод является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="parameters"></a>Параметры

`connectionGroupName` <xref:System.String>

Имя группы соединений, которую нужно закрыть.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)

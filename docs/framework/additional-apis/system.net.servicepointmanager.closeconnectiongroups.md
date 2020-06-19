---
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
ms.openlocfilehash: aae9a389ae35e249d43c9dc830a68ec32cf4afef
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990498"
---
# <a name="servicepointmanagercloseconnectiongroups-method"></a><span data-ttu-id="60101-102">ServicePointManager. Клосеконнектионграупс, метод</span><span class="sxs-lookup"><span data-stu-id="60101-102">ServicePointManager.CloseConnectionGroups method</span></span>

<span data-ttu-id="60101-103">Выполняет перебор всех точек обслуживания и закрывает группы соединений с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="60101-103">Iterates through all service points and closes connection groups that have the specified name.</span></span>

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> <span data-ttu-id="60101-104">Этот метод является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="60101-104">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="60101-105">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="60101-105">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="60101-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="60101-106">Parameters</span></span>

<span data-ttu-id="60101-107">`connectionGroupName` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="60101-107">`connectionGroupName` <xref:System.String></span></span>

<span data-ttu-id="60101-108">Имя группы соединений, которую нужно закрыть.</span><span class="sxs-lookup"><span data-stu-id="60101-108">The name of the connection group to close.</span></span>

## <a name="requirements"></a><span data-ttu-id="60101-109">Требования</span><span class="sxs-lookup"><span data-stu-id="60101-109">Requirements</span></span>

<span data-ttu-id="60101-110">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="60101-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="60101-111">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="60101-111">**Assembly:** System (in System.dll)</span></span>

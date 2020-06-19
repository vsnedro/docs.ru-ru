---
title: Поле ServicePointManager. s_ServicePointTable
description: Прочитайте о поле ServicePointManager. s_ServicePointTable в .NET. Это поле хэш-таблицы содержит активные HTTP-соединения (Сервицепоинтс) в домене приложения.
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 9462ae10125dd37706f786a1f2cef78e62fbabcc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989549"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="50add-104">ServicePointManager. s \_ Сервицепоинттабле поле</span><span class="sxs-lookup"><span data-stu-id="50add-104">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="50add-105">`ServicePointManager.s_ServicePointTable`значение типа <xref:System.Collections.Hashtable> , содержащее список активных HTTP-соединений <xref:System.Net.ServicePoint> в <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="50add-105">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="50add-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50add-106">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="50add-107">`ServicePointManager.s_ServicePointTable`Поле является закрытым и не предназначено для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="50add-107">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="50add-108">Корпорация Майкрософт не поддерживает использование этого поля в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="50add-108">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="50add-109">Требования</span><span class="sxs-lookup"><span data-stu-id="50add-109">Requirements</span></span>

<span data-ttu-id="50add-110">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="50add-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="50add-111">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="50add-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="50add-112">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="50add-112">**.NET Framework versions:** Available since 2.0.</span></span>

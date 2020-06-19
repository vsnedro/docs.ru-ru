---
title: Поле Connection. m_WriteList
description: Получение сведений о поле Connection. m_WriteList в .NET. Это поле ArrayList содержит объекты HttpWebRequest, которые помещаются в очередь для отправки по протоколу HTTP.
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
ms.openlocfilehash: a627cb062036e3ab098c2d6e97f9a77ebfa75a33
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989600"
---
# <a name="connectionm_writelist-field"></a><span data-ttu-id="82471-104">Поле Connection. m \_ врителист</span><span class="sxs-lookup"><span data-stu-id="82471-104">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="82471-105">`Connection.m_WriteList`— Это объект, находящихся в <xref:System.Collections.ArrayList> <xref:System.Net.HttpWebRequest> очереди на отправку по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="82471-105">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="82471-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82471-106">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="82471-107">`Connection.m_WriteList`Поле является закрытым и не предназначено для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="82471-107">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="82471-108">Корпорация Майкрософт не поддерживает использование этого поля в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="82471-108">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="82471-109">Требования</span><span class="sxs-lookup"><span data-stu-id="82471-109">Requirements</span></span>

<span data-ttu-id="82471-110">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="82471-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="82471-111">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="82471-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="82471-112">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="82471-112">**.NET Framework versions:** Available since 2.0.</span></span>

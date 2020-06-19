---
title: Класс Connection (System.Net)
description: Сведения о классе Connection в .NET. Этот класс выполняет синтаксический анализ ответов сервера, запросов очереди и конвейерных запросов. Он находится в пространстве имен System.NET.
ms.date: 05/01/2017
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Connection
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 6f0b8902-f31c-4ab9-a8c9-de43228995ec
ms.openlocfilehash: cb28724ed782fc5395dc74e9c59249ebdea44ddf
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989829"
---
# <a name="connection-class"></a><span data-ttu-id="47a4d-105">Класс Connection</span><span class="sxs-lookup"><span data-stu-id="47a4d-105">Connection Class</span></span>

<span data-ttu-id="47a4d-106">`Connection`Класс анализирует ответы сервера, запросы очереди и конвейерные запросы.</span><span class="sxs-lookup"><span data-stu-id="47a4d-106">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="47a4d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47a4d-107">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="47a4d-108">`Connection`Класс является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="47a4d-108">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="47a4d-109">Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="47a4d-109">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="47a4d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="47a4d-110">Requirements</span></span>

<span data-ttu-id="47a4d-111">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="47a4d-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="47a4d-112">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="47a4d-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="47a4d-113">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="47a4d-113">**.NET Framework versions:** Available since 2.0.</span></span>

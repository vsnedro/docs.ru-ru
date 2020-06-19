---
title: Класс ConnectionGroup
description: Ознакомьтесь с классом Коннектионграуп, который группирует соединения в контексте ServicePoint и используется для сохранения контекста сетевых ресурсов в .NET.
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 25c08217-fdeb-44b9-9cd6-1b4955d6e602
ms.openlocfilehash: 7121713b26880f2490b40d59d92d431a567519b3
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989813"
---
# <a name="connectiongroup-class"></a><span data-ttu-id="31aec-103">Класс ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="31aec-103">ConnectionGroup Class</span></span>

<span data-ttu-id="31aec-104">`ConnectionGroup`Класс группирует список соединений в <xref:System.Net.ServicePoint> контексте и используется для сохранения контекста сетевых ресурсов (например, для прокси-серверов и отдельных клиентов).</span><span class="sxs-lookup"><span data-stu-id="31aec-104">The `ConnectionGroup` class groups a list of connections within the <xref:System.Net.ServicePoint> context and is used to maintain context for network resources (for example, proxies and separate clients).</span></span>

## <a name="syntax"></a><span data-ttu-id="31aec-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31aec-105">Syntax</span></span>
  
```csharp  
internal class ConnectionGroup
```

> [!WARNING]
> <span data-ttu-id="31aec-106">`ConnectionGroup`Класс является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="31aec-106">The `ConnectionGroup` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="31aec-107">Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="31aec-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="31aec-108">Требования</span><span class="sxs-lookup"><span data-stu-id="31aec-108">Requirements</span></span>

<span data-ttu-id="31aec-109">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="31aec-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="31aec-110">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="31aec-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="31aec-111">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="31aec-111">**.NET Framework versions:** Available since 2.0.</span></span>

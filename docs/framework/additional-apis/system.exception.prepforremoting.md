---
title: Метод Exception. Препфорремотинг (система)
description: Изучите метод Exception. Препфорремотинг в .NET. Метод добавляет в сообщение серверную трассировку стека, прежде чем исключение будет повторно создано на стороне клиента.
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 9ceb73499ae3bb308975e6db5b961bfe40165ba3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105255"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="676c5-104">Метод Exception.PrepForRemoting</span><span class="sxs-lookup"><span data-stu-id="676c5-104">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="676c5-105">Сохраняет трассировку стека на стороне сервера, добавляя ее к сообщению, прежде чем исключение будет повторно создано на сайте вызова клиента.</span><span class="sxs-lookup"><span data-stu-id="676c5-105">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="676c5-106">Возвращает</span><span class="sxs-lookup"><span data-stu-id="676c5-106">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="676c5-107">Данный экземпляр <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="676c5-107">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="676c5-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="676c5-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="676c5-109">`Exception.PrepForRemoting`Метод является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="676c5-109">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="676c5-110">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="676c5-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="676c5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="676c5-111">Requirements</span></span>

<span data-ttu-id="676c5-112">**Пространство имен:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="676c5-112">**Namespace:** <xref:System></span></span>

<span data-ttu-id="676c5-113">**Сборка:** mscorlib.dll (в mscorlib.dll)</span><span class="sxs-lookup"><span data-stu-id="676c5-113">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="676c5-114">**.NET Framework версии:** Доступно с 1,0.</span><span class="sxs-lookup"><span data-stu-id="676c5-114">**.NET Framework versions:** Available since 1.0.</span></span>

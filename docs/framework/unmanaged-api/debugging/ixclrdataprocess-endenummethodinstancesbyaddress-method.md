---
title: 'Метод Иксклрдатапроцесс:: Енденуммесодинстанцесбяддресс'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5960d08ccfc09010a20d28a22c2e2f3f5b339c7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420831"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="2e290-102">Метод Иксклрдатапроцесс:: Енденуммесодинстанцесбяддресс</span><span class="sxs-lookup"><span data-stu-id="2e290-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="2e290-103">Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2e290-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2e290-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e290-104">Syntax</span></span>

```cpp
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="2e290-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e290-105">Parameters</span></span>

`handle`\
<span data-ttu-id="2e290-106">заполняет Описатель для перечисления экземпляров методов.</span><span class="sxs-lookup"><span data-stu-id="2e290-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e290-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2e290-107">Remarks</span></span>

<span data-ttu-id="2e290-108">Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует 30-му слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="2e290-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 30th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e290-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2e290-109">Requirements</span></span>

<span data-ttu-id="2e290-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e290-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2e290-111">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="2e290-111">**Header:** None</span></span>  
<span data-ttu-id="2e290-112">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="2e290-112">**Library:** None</span></span>  
<span data-ttu-id="2e290-113">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2e290-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2e290-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="2e290-114">See also</span></span>

- [<span data-ttu-id="2e290-115">Перечисление Клрдатасаурцетипе</span><span class="sxs-lookup"><span data-stu-id="2e290-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="2e290-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="2e290-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="2e290-117">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="2e290-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

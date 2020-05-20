---
title: 'Метод Иксклрдатапроцесс:: Енуммесодинстанцебяддресс'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 142099ae5cf9637cc28e8c82aabcd831cc8f0f52
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420803"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="68e73-102">Метод Иксклрдатапроцесс:: Енуммесодинстанцебяддресс</span><span class="sxs-lookup"><span data-stu-id="68e73-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="68e73-103">Перечисляет экземпляры методов этого процесса, начиная с смещения адреса.</span><span class="sxs-lookup"><span data-stu-id="68e73-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="68e73-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68e73-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="68e73-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="68e73-105">Parameters</span></span>

`handle`\
<span data-ttu-id="68e73-106">окне Описатель для перечисления экземпляров методов.</span><span class="sxs-lookup"><span data-stu-id="68e73-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="68e73-107">заполняет Экземпляр перечисленного метода.</span><span class="sxs-lookup"><span data-stu-id="68e73-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="68e73-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="68e73-108">Remarks</span></span>

<span data-ttu-id="68e73-109">Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует слоту 29 таблицы виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="68e73-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="68e73-110">Требования</span><span class="sxs-lookup"><span data-stu-id="68e73-110">Requirements</span></span>

<span data-ttu-id="68e73-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68e73-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="68e73-112">**Заголовок:** Нет **библиотеки:** нет **.NET Framework версий:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="68e73-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="68e73-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="68e73-113">See also</span></span>

- [<span data-ttu-id="68e73-114">Перечисление Клрдатасаурцетипе</span><span class="sxs-lookup"><span data-stu-id="68e73-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="68e73-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="68e73-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="68e73-116">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="68e73-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

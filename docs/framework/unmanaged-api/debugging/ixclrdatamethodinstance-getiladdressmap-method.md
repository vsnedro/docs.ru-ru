---
title: 'Метод Иксклрдатамесодинстанце:: Жетиладдрессмап'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7c4dcf59ce159434d5012120043f5bb548d49731
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396820"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="55a30-102">Метод Иксклрдатамесодинстанце:: Жетиладдрессмап</span><span class="sxs-lookup"><span data-stu-id="55a30-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="55a30-103">Возвращает IL для сопоставления сведений о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="55a30-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="55a30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55a30-104">Syntax</span></span>

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="55a30-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55a30-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="55a30-106">окне Длина указанного массива сопоставлений.</span><span class="sxs-lookup"><span data-stu-id="55a30-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="55a30-107">заполняет Количество записей карт, необходимых методу.</span><span class="sxs-lookup"><span data-stu-id="55a30-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="55a30-108">[out, size_is (Маплен)] Массив для хранения записей сопоставлений.</span><span class="sxs-lookup"><span data-stu-id="55a30-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="55a30-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="55a30-109">Remarks</span></span>

<span data-ttu-id="55a30-110">Предоставленный метод является частью `IXCLRDataMethodInstance` интерфейса и соответствует 15-слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="55a30-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 15th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="55a30-111">Требования</span><span class="sxs-lookup"><span data-stu-id="55a30-111">Requirements</span></span>

<span data-ttu-id="55a30-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55a30-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="55a30-113">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="55a30-113">**Header:** None</span></span>  
<span data-ttu-id="55a30-114">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="55a30-114">**Library:** None</span></span>  
<span data-ttu-id="55a30-115">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="55a30-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="55a30-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="55a30-116">See also</span></span>

- [<span data-ttu-id="55a30-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="55a30-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="55a30-118">Интерфейс IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="55a30-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)

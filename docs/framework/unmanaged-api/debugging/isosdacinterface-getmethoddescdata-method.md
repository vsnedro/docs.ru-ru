---
title: 'Метод ИсосдаЦинтерфаце:: Жетмесоддескдата'
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 105149d0abf312c33a8498e7428e3a8b23d6ae7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421024"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="69974-102">Метод ИсосдаЦинтерфаце:: Жетмесоддескдата</span><span class="sxs-lookup"><span data-stu-id="69974-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="69974-103">Возвращает данные для заданного указателя MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="69974-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="69974-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69974-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="69974-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69974-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="69974-106">окне Адрес MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="69974-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="69974-107">окне IP-адрес метода.</span><span class="sxs-lookup"><span data-stu-id="69974-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="69974-108">заполняет Данные, связанные с MethodDesc, возвращаются из внутренних API-интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="69974-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="69974-109">заполняет Число восстановленных версий rejit.</span><span class="sxs-lookup"><span data-stu-id="69974-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="69974-110">заполняет Данные, связанные с возвращенными версиями rejit, возвращенные из внутренних API.</span><span class="sxs-lookup"><span data-stu-id="69974-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="69974-111">заполняет Число байтов, необходимое для хранения данных, связанных с возвращенными версиями ReJit.</span><span class="sxs-lookup"><span data-stu-id="69974-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="69974-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="69974-112">Remarks</span></span>

<span data-ttu-id="69974-113">Предоставленный метод является частью `ISOSDacInterface` интерфейса и соответствует 21-сегменту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="69974-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 21st slot of the virtual method table.</span></span> <span data-ttu-id="69974-114">Чтобы иметь возможность использовать их, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) необходимо определить как 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="69974-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="69974-115">Требования</span><span class="sxs-lookup"><span data-stu-id="69974-115">Requirements</span></span>

<span data-ttu-id="69974-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69974-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="69974-117">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="69974-117">**Header:** None</span></span>  
<span data-ttu-id="69974-118">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="69974-118">**Library:** None</span></span>  
<span data-ttu-id="69974-119">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="69974-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="69974-120">См. также статью</span><span class="sxs-lookup"><span data-stu-id="69974-120">See also</span></span>

- [<span data-ttu-id="69974-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="69974-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="69974-122">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="69974-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)

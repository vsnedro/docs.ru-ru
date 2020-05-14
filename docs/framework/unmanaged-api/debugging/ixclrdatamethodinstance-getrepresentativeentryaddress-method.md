---
title: 'Метод Иксклрдатамесодинстанце:: Жетрепресентативинтряддресс'
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: d9f9e16d243c0f3b45ac24776caea5bb9c32dcc1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395755"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="0c9ac-102">Метод Иксклрдатамесодинстанце:: Жетрепресентативинтряддресс</span><span class="sxs-lookup"><span data-stu-id="0c9ac-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="0c9ac-103">Возвращает наиболее репрезентативный адрес точки входа для собственной компиляции всех возможных точек входа для метода.</span><span class="sxs-lookup"><span data-stu-id="0c9ac-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0c9ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c9ac-104">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="0c9ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c9ac-105">Parameters</span></span>

`addr`\
<span data-ttu-id="0c9ac-106">заполняет Адрес наиболее репрезентативной собственной точки входа для метода.</span><span class="sxs-lookup"><span data-stu-id="0c9ac-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c9ac-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0c9ac-107">Remarks</span></span>

<span data-ttu-id="0c9ac-108">Предоставленный метод является частью [ `IXCLRDataMethodInstance` интерфейса](ixclrdatamethodinstance-interface.md) и соответствует слоту 20 таблицы виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="0c9ac-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 20th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="0c9ac-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0c9ac-109">Requirements</span></span>

<span data-ttu-id="0c9ac-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c9ac-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0c9ac-111">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="0c9ac-111">**Header:** None</span></span>  
<span data-ttu-id="0c9ac-112">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="0c9ac-112">**Library:** None</span></span>  
<span data-ttu-id="0c9ac-113">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0c9ac-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0c9ac-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="0c9ac-114">See also</span></span>

- [<span data-ttu-id="0c9ac-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="0c9ac-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="0c9ac-116">Интерфейс IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="0c9ac-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)

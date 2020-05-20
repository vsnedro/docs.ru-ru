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
ms.openlocfilehash: d546cda5c68732e75550a3de286089f7df261c91
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420907"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="f1a72-102">Метод Иксклрдатамесодинстанце:: Жетрепресентативинтряддресс</span><span class="sxs-lookup"><span data-stu-id="f1a72-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="f1a72-103">Возвращает наиболее репрезентативный адрес точки входа для собственной компиляции всех возможных точек входа для метода.</span><span class="sxs-lookup"><span data-stu-id="f1a72-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f1a72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1a72-104">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="f1a72-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1a72-105">Parameters</span></span>

`addr`\
<span data-ttu-id="f1a72-106">заполняет Адрес наиболее репрезентативной собственной точки входа для метода.</span><span class="sxs-lookup"><span data-stu-id="f1a72-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1a72-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f1a72-107">Remarks</span></span>

<span data-ttu-id="f1a72-108">Предоставленный метод является частью [ `IXCLRDataMethodInstance` интерфейса](ixclrdatamethodinstance-interface.md) и соответствует слоту 20 таблицы виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="f1a72-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 20th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1a72-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f1a72-109">Requirements</span></span>

<span data-ttu-id="f1a72-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1a72-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f1a72-111">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="f1a72-111">**Header:** None</span></span>  
<span data-ttu-id="f1a72-112">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="f1a72-112">**Library:** None</span></span>  
<span data-ttu-id="f1a72-113">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f1a72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f1a72-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f1a72-114">See also</span></span>

- [<span data-ttu-id="f1a72-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="f1a72-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="f1a72-116">Интерфейс IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="f1a72-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)

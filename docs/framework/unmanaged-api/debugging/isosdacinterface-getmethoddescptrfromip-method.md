---
title: 'Метод ИсосдаЦинтерфаце:: Жетмесоддескптрфромип'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c3de9e5ffe23a13c126343c6f74f042bf1239609
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421011"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="292ca-102">Метод ИсосдаЦинтерфаце:: Жетмесоддескптрфромип</span><span class="sxs-lookup"><span data-stu-id="292ca-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="292ca-103">Получает указатель MethodDesc, соответствующий методу, содержащему указанный адрес собственной инструкции.</span><span class="sxs-lookup"><span data-stu-id="292ca-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="292ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="292ca-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="292ca-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="292ca-105">Parameters</span></span>

`ip`\
<span data-ttu-id="292ca-106">окне Адрес в методе во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="292ca-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="292ca-107">заполняет Адрес `MethodDesc` для конкретного метода.</span><span class="sxs-lookup"><span data-stu-id="292ca-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="292ca-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="292ca-108">Remarks</span></span>

<span data-ttu-id="292ca-109">Предоставленный метод является частью [ `ISOSDacInterface` интерфейса](isosdacinterface-interface.md) и соответствует слоту 22 таблицы виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="292ca-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="292ca-110">Требования</span><span class="sxs-lookup"><span data-stu-id="292ca-110">Requirements</span></span>

<span data-ttu-id="292ca-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="292ca-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="292ca-112">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="292ca-112">**Header:** None</span></span>  
<span data-ttu-id="292ca-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="292ca-113">**Library:** None</span></span>  
<span data-ttu-id="292ca-114">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="292ca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="292ca-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="292ca-115">See also</span></span>

- [<span data-ttu-id="292ca-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="292ca-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="292ca-117">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="292ca-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)

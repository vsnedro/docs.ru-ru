---
title: 'Метод Иксклрдатапроцесс:: Жетрунтименамебяддресс'
ms.date: 4/27/2020
api.name:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: tommcdon
ms.author: tommcdon
ms.openlocfilehash: 6648bdafe6e5cdd402bcfa02a148c57f0f1e209e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275570"
---
# <a name="ixclrdataprocessgetruntimenamebyaddress-method"></a><span data-ttu-id="6e849-102">Метод Иксклрдатапроцесс:: Жетрунтименамебяддресс</span><span class="sxs-lookup"><span data-stu-id="6e849-102">IXCLRDataProcess::GetRuntimeNameByAddress Method</span></span>

<span data-ttu-id="6e849-103">Возвращает имя для заданного адреса.</span><span class="sxs-lookup"><span data-stu-id="6e849-103">Gets a name for the given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6e849-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e849-104">Syntax</span></span>

```cpp
HRESULT GetRuntimeNameByAddress(
    [in] CLRDATA_ADDRESS address,
    [in] ULONG32 flags,
    [in] ULONG32 bufLen,
    [out] ULONG32 *nameLen,
    [out, size_is(bufLen)] WCHAR nameBuf[],
    [out] CLRDATA_ADDRESS* displacement
);
```

## <a name="parameters"></a><span data-ttu-id="6e849-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e849-105">Parameters</span></span>

`address`\
<span data-ttu-id="6e849-106">окне `CLRDATA_ADDRESS` Значение, представляющее адрес кода.</span><span class="sxs-lookup"><span data-stu-id="6e849-106">[in] A `CLRDATA_ADDRESS` value that represents a code address.</span></span>

`flags`\
<span data-ttu-id="6e849-107">окне Задайте значение "0".</span><span class="sxs-lookup"><span data-stu-id="6e849-107">[in] Set to '0'.</span></span>

`bufLen`\
<span data-ttu-id="6e849-108">окне Длина буфера.</span><span class="sxs-lookup"><span data-stu-id="6e849-108">[in] The length of the buffer.</span></span>

`namLen`\
<span data-ttu-id="6e849-109">заполняет Указатель на число возвращаемых символов.</span><span class="sxs-lookup"><span data-stu-id="6e849-109">[out] A pointer to the number of characters returned.</span></span>

`namBuf`\
<span data-ttu-id="6e849-110">[out, size_is ( `bufLen` )] входной буфер длины `bufLen` , в которой хранится имя среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6e849-110">[out, size_is(`bufLen`)] The input buffer of length `bufLen` that stores the runtime name.</span></span>

`displacement`\
<span data-ttu-id="6e849-111">заполняет `CLRDATA_ADDRESS` Указатель на смещение кода возвращаемого символа.</span><span class="sxs-lookup"><span data-stu-id="6e849-111">[out] A `CLRDATA_ADDRESS` pointer to the code offset of the returned symbol.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e849-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="6e849-112">Remarks</span></span>

<span data-ttu-id="6e849-113">Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует шестнадцатому слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="6e849-113">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 16th slot of the virtual-method table.</span></span>

> [!NOTE]
> <span data-ttu-id="6e849-114">Если размер буфера не достаточен для имени, этот метод возвращает `S_FALSE` и задает `nameLen` требуемую длину буфера.</span><span class="sxs-lookup"><span data-stu-id="6e849-114">If the buffer is not large enough for the name, this method returns `S_FALSE` and sets `nameLen` to the required buffer length.</span></span>

## <a name="requirements"></a><span data-ttu-id="6e849-115">Требования</span><span class="sxs-lookup"><span data-stu-id="6e849-115">Requirements</span></span>

<span data-ttu-id="6e849-116">**Платформы:** См. [требования к системе](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="6e849-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="6e849-117">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="6e849-117">**Header:** None\</span></span>
<span data-ttu-id="6e849-118">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="6e849-118">**Library:** None\</span></span>
<span data-ttu-id="6e849-119">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6e849-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6e849-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6e849-120">See also</span></span>

- [<span data-ttu-id="6e849-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="6e849-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="6e849-122">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="6e849-122">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

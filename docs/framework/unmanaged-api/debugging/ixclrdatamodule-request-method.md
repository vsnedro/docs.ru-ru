---
title: 'Метод Иксклрдатамодуле:: Request'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 44ee4fc7fc2368b65f6f2fffe6ac239beddc6293
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395269"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="a6f41-102">Метод Иксклрдатамодуле:: Request</span><span class="sxs-lookup"><span data-stu-id="a6f41-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="a6f41-103">Запросы на заполнение буфера данными модуля.</span><span class="sxs-lookup"><span data-stu-id="a6f41-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a6f41-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6f41-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="a6f41-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6f41-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="a6f41-106">окне Тип запроса для отправки.</span><span class="sxs-lookup"><span data-stu-id="a6f41-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="a6f41-107">[in] размер входного буфера, который должен быть передан.</span><span class="sxs-lookup"><span data-stu-id="a6f41-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="a6f41-108">[in, size_is (Инбуфферсизе)] Указатель буфера для необработанных данных, отправляемых в запросе.</span><span class="sxs-lookup"><span data-stu-id="a6f41-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="a6f41-109">окне Размер выходного буфера.</span><span class="sxs-lookup"><span data-stu-id="a6f41-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="a6f41-110">[out, size_is (Аутбуфферсизе)] Указатель буфера, используемый для хранения ответа на запрос.</span><span class="sxs-lookup"><span data-stu-id="a6f41-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6f41-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a6f41-111">Remarks</span></span>

<span data-ttu-id="a6f41-112">Предоставленный метод является частью `IXCLRDataModule` интерфейса и соответствует слоту 37th таблицы виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="a6f41-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 37th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a6f41-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a6f41-113">Requirements</span></span>

<span data-ttu-id="a6f41-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6f41-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="a6f41-115">**Заголовок:** Нет **библиотеки:** нет **.NET Framework версий:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a6f41-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a6f41-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="a6f41-116">See also</span></span>

- [<span data-ttu-id="a6f41-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="a6f41-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="a6f41-118">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="a6f41-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

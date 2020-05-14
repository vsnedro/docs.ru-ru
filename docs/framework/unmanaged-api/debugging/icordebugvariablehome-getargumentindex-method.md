---
title: 'Метод ICorDebugVariableHome:: Жетаргументиндекс'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
ms.openlocfilehash: 27a676fd1d2d7903943e44f8a7201b88af4fba89
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396997"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="c75bb-102">Метод ICorDebugVariableHome:: Жетаргументиндекс</span><span class="sxs-lookup"><span data-stu-id="c75bb-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="c75bb-103">Возвращает индекс аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="c75bb-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="c75bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c75bb-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="c75bb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c75bb-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="c75bb-106">заполняет Указатель на индекс аргумента.</span><span class="sxs-lookup"><span data-stu-id="c75bb-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="c75bb-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c75bb-107">Return Value</span></span>

<span data-ttu-id="c75bb-108">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="c75bb-108">The method returns the following values.</span></span>

|<span data-ttu-id="c75bb-109">Значение</span><span class="sxs-lookup"><span data-stu-id="c75bb-109">Value</span></span>|<span data-ttu-id="c75bb-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c75bb-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="c75bb-111">Вызов метода вернул допустимый индекс аргумента.</span><span class="sxs-lookup"><span data-stu-id="c75bb-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="c75bb-112">Текущий экземпляр [ICorDebugVariableHome](icordebugvariablehome-interface.md) представляет локальную переменную.</span><span class="sxs-lookup"><span data-stu-id="c75bb-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c75bb-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="c75bb-113">Remarks</span></span>

<span data-ttu-id="c75bb-114">Индекс аргумента можно использовать для получения метаданных для этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="c75bb-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="c75bb-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c75bb-115">Requirements</span></span>

<span data-ttu-id="c75bb-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c75bb-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c75bb-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c75bb-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="c75bb-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c75bb-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c75bb-119">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c75bb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c75bb-120">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c75bb-120">See also</span></span>

- [<span data-ttu-id="c75bb-121">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="c75bb-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)

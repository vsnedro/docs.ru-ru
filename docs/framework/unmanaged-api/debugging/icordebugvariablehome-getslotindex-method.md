---
title: 'Метод ICorDebugVariableHome:: GetSlotIndex'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
ms.openlocfilehash: 4b071bd8e9d96084848c1553385eec5f8beca624
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711732"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="50fb7-102">Метод ICorDebugVariableHome:: GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="50fb7-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>

<span data-ttu-id="50fb7-103">Возвращает управляемый индекс в виде слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="50fb7-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50fb7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50fb7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50fb7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50fb7-105">Parameters</span></span>  

 `pSlotIndex`  
 <span data-ttu-id="50fb7-106">заполняет Указатель на индекс в виде слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="50fb7-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50fb7-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="50fb7-107">Return Value</span></span>  

 <span data-ttu-id="50fb7-108">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="50fb7-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="50fb7-109">Значение</span><span class="sxs-lookup"><span data-stu-id="50fb7-109">Value</span></span>|<span data-ttu-id="50fb7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="50fb7-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="50fb7-111">Вызов метода вернул значение индекса слота в `pSlotIndex` .</span><span class="sxs-lookup"><span data-stu-id="50fb7-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="50fb7-112">Текущий экземпляр [ICorDebugVariableHome](icordebugvariablehome-interface.md) представляет аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="50fb7-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50fb7-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="50fb7-113">Remarks</span></span>  

 <span data-ttu-id="50fb7-114">Чтобы получить метаданные для этой локальной переменной, можно использовать индекс Slot.</span><span class="sxs-lookup"><span data-stu-id="50fb7-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50fb7-115">Требования</span><span class="sxs-lookup"><span data-stu-id="50fb7-115">Requirements</span></span>  

 <span data-ttu-id="50fb7-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50fb7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50fb7-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50fb7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50fb7-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50fb7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50fb7-119">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50fb7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50fb7-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="50fb7-120">See also</span></span>

- [<span data-ttu-id="50fb7-121">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="50fb7-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)

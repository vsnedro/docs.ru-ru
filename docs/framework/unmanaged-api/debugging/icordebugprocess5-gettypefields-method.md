---
title: Метод ICorDebugProcess5::GetTypeFields
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
ms.openlocfilehash: a2c7f7b722abac6acf71d3b64276862441695a5f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212793"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="26627-102">Метод ICorDebugProcess5::GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="26627-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="26627-103">Предоставляет сведения о полях, принадлежащих типу.</span><span class="sxs-lookup"><span data-stu-id="26627-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26627-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26627-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26627-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="26627-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="26627-106">окне Идентификатор типа, сведения о поле которого извлекаются.</span><span class="sxs-lookup"><span data-stu-id="26627-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="26627-107">окне Число объектов [COR_FIELD](cor-field-structure.md) , сведения о полях которых нужно получить.</span><span class="sxs-lookup"><span data-stu-id="26627-107">[in] The number of [COR_FIELD](cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="26627-108">заполняет Массив объектов [COR_FIELD](cor-field-structure.md) , которые предоставляют сведения о полях, принадлежащих типу.</span><span class="sxs-lookup"><span data-stu-id="26627-108">[out] An array of [COR_FIELD](cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="26627-109">заполняет Указатель на число объектов [COR_FIELD](cor-field-structure.md) , включаемых в `fields` .</span><span class="sxs-lookup"><span data-stu-id="26627-109">[out] A pointer to the number of [COR_FIELD](cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26627-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="26627-110">Remarks</span></span>  
 <span data-ttu-id="26627-111">`celt`Параметр, указывающий количество полей, сведения о полях которых использует метод для заполнения `fields` , должно соответствовать значению `COR_TYPE_LAYOUT::numFields` поля.</span><span class="sxs-lookup"><span data-stu-id="26627-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26627-112">Требования</span><span class="sxs-lookup"><span data-stu-id="26627-112">Requirements</span></span>  
 <span data-ttu-id="26627-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26627-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26627-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26627-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26627-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26627-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26627-116">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26627-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26627-117">См. также</span><span class="sxs-lookup"><span data-stu-id="26627-117">See also</span></span>

- [<span data-ttu-id="26627-118">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="26627-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="26627-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="26627-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

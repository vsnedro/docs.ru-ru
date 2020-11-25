---
title: Структура COR_TYPE_LAYOUT
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
ms.openlocfilehash: f33c8f5cf218979404063342d9b1cc5123839f83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726331"
---
# <a name="cor_type_layout-structure"></a><span data-ttu-id="4b760-102">Структура COR_TYPE_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="4b760-102">COR_TYPE_LAYOUT Structure</span></span>

<span data-ttu-id="4b760-103">Предоставляет сведения о расположении объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="4b760-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b760-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b760-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="4b760-105">Члены</span><span class="sxs-lookup"><span data-stu-id="4b760-105">Members</span></span>  
  
|<span data-ttu-id="4b760-106">Член</span><span class="sxs-lookup"><span data-stu-id="4b760-106">Member</span></span>|<span data-ttu-id="4b760-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4b760-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="4b760-108">Идентификатор родительского типа для этого типа.</span><span class="sxs-lookup"><span data-stu-id="4b760-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="4b760-109">Это будет идентификатор типа NULL (токен1 = 0, токен2 = 0), если идентификатор типа соответствует <xref:System.Object?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4b760-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="4b760-110">Базовый размер объекта этого типа.</span><span class="sxs-lookup"><span data-stu-id="4b760-110">The base size of an object of this type.</span></span> <span data-ttu-id="4b760-111">Это общий размер для объектов, не имеющих переменного размера.</span><span class="sxs-lookup"><span data-stu-id="4b760-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="4b760-112">Число полей, включаемых в объекты этого типа.</span><span class="sxs-lookup"><span data-stu-id="4b760-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="4b760-113">Если этот тип упакован, начальное смещение полей объекта.</span><span class="sxs-lookup"><span data-stu-id="4b760-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="4b760-114">Это поле допустимо только для типов значений, таких как примитивы и структуры.</span><span class="sxs-lookup"><span data-stu-id="4b760-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="4b760-115">Корелементтипе, к которому принадлежит этот тип.</span><span class="sxs-lookup"><span data-stu-id="4b760-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b760-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4b760-116">Remarks</span></span>  

 <span data-ttu-id="4b760-117">Если `numFields` значение больше нуля, можно вызвать метод [метод ICorDebugProcess5:: жеттипефиелдс](icordebugprocess5-gettypefields-method.md) для получения сведений о полях этого типа.</span><span class="sxs-lookup"><span data-stu-id="4b760-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="4b760-118">Если `type` имеет значение `ELEMENT_TYPE_STRING` , `ELEMENT_TYPE_ARRAY` или `ELEMENT_TYPE_SZARRAY` , то размер объектов этого типа является переменным, и можно передать структуру [COR_TYPEID](cor-typeid-structure.md) в метод [метод ICorDebugProcess5:: жетаррайлайаут](icordebugprocess5-getarraylayout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4b760-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b760-119">Требования</span><span class="sxs-lookup"><span data-stu-id="4b760-119">Requirements</span></span>  

 <span data-ttu-id="4b760-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b760-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b760-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b760-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b760-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b760-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b760-123">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b760-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b760-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4b760-124">See also</span></span>

- [<span data-ttu-id="4b760-125">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="4b760-125">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="4b760-126">Отладка</span><span class="sxs-lookup"><span data-stu-id="4b760-126">Debugging</span></span>](index.md)

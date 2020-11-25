---
title: Интерфейс ICorDebugType2
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
ms.openlocfilehash: 0d5fffe4350cc1f58acf588f288db3bdb7e213d0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725672"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="e8dbb-102">Интерфейс ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="e8dbb-102">ICorDebugType2 Interface</span></span>

<span data-ttu-id="e8dbb-103">Расширяет интерфейс ICorDebugType для получения идентификатора типа базового типа или сложного (определяемого пользователем) типа.</span><span class="sxs-lookup"><span data-stu-id="e8dbb-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8dbb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e8dbb-104">Methods</span></span>  
  
|<span data-ttu-id="e8dbb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e8dbb-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="e8dbb-106">Метод GetTypeID</span><span class="sxs-lookup"><span data-stu-id="e8dbb-106">GetTypeID Method</span></span>](icordebugtype2-gettypeid-method.md)|<span data-ttu-id="e8dbb-107">Возвращает [COR_TYPEID](cor-typeid-structure.md) для этого типа.</span><span class="sxs-lookup"><span data-stu-id="e8dbb-107">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8dbb-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e8dbb-108">Remarks</span></span>  

 <span data-ttu-id="e8dbb-109">Этот интерфейс является логическим расширением интерфейса ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="e8dbb-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8dbb-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="e8dbb-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8dbb-111">Пример</span><span class="sxs-lookup"><span data-stu-id="e8dbb-111">Example</span></span>  

 <span data-ttu-id="e8dbb-112">В следующем фрагменте кода показано использование метода [ICorDebugType2:: typeid](icordebugtype2-gettypeid-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e8dbb-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="e8dbb-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e8dbb-113">Requirements</span></span>  

 <span data-ttu-id="e8dbb-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8dbb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8dbb-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8dbb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8dbb-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8dbb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8dbb-117">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8dbb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8dbb-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e8dbb-118">See also</span></span>

- [<span data-ttu-id="e8dbb-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e8dbb-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

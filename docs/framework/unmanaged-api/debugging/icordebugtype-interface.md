---
title: Интерфейс ICorDebugType
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
ms.openlocfilehash: 5e88652ff75223e30e6abc454f1e1af91494c7b2
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396694"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="9ceff-102">Интерфейс ICorDebugType</span><span class="sxs-lookup"><span data-stu-id="9ceff-102">ICorDebugType Interface</span></span>
<span data-ttu-id="9ceff-103">Представляет тип — базовый или сложный (то есть определяемый пользователем).</span><span class="sxs-lookup"><span data-stu-id="9ceff-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="9ceff-104">Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="9ceff-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ceff-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9ceff-105">Methods</span></span>  
  
|<span data-ttu-id="9ceff-106">Метод</span><span class="sxs-lookup"><span data-stu-id="9ceff-106">Method</span></span>|<span data-ttu-id="9ceff-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9ceff-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ceff-108">Метод EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="9ceff-108">EnumerateTypeParameters Method</span></span>](icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="9ceff-109">Возвращает указатель интерфейса на ICorDebugTypeEnum, который ссылается на универсальные <xref:System.Type> Параметры класса, на который ссылается this `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="9ceff-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="9ceff-110">Метод GetBase</span><span class="sxs-lookup"><span data-stu-id="9ceff-110">GetBase Method</span></span>](icordebugtype-getbase-method.md)|<span data-ttu-id="9ceff-111">Возвращает указатель интерфейса на объект `ICorDebugType` , который ссылается на базовый класс класса, на который ссылается этот класс `ICorDebugType` , если он существует.</span><span class="sxs-lookup"><span data-stu-id="9ceff-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="9ceff-112">Метод GetClass</span><span class="sxs-lookup"><span data-stu-id="9ceff-112">GetClass Method</span></span>](icordebugtype-getclass-method.md)|<span data-ttu-id="9ceff-113">Возвращает указатель интерфейса на объект ICorDebugClass, который ссылается на типизированный конструктор этого объекта `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="9ceff-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="9ceff-114">Метод GetFirstTypeParameter</span><span class="sxs-lookup"><span data-stu-id="9ceff-114">GetFirstTypeParameter Method</span></span>](icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="9ceff-115">Возвращает указатель интерфейса на объект `ICorDebugType` , который ссылается на первый универсальный <xref:System.Type> параметр для конструктора класса, на который ссылается this `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="9ceff-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="9ceff-116">Метод GetRank</span><span class="sxs-lookup"><span data-stu-id="9ceff-116">GetRank Method</span></span>](icordebugtype-getrank-method.md)|<span data-ttu-id="9ceff-117">Возвращает число измерений в типе массива.</span><span class="sxs-lookup"><span data-stu-id="9ceff-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="9ceff-118">Метод GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="9ceff-118">GetStaticFieldValue Method</span></span>](icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="9ceff-119">Возвращает указатель интерфейса на объект ICorDebugValue, содержащий значение статического поля, на которое ссылается заданный токен поля в указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="9ceff-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="9ceff-120">Метод GetType</span><span class="sxs-lookup"><span data-stu-id="9ceff-120">GetType Method</span></span>](icordebugtype-gettype-method.md)|<span data-ttu-id="9ceff-121">Возвращает значение Корелементтипе, описывающее собственный тип среды CLR, <xref:System.Type> на который ссылается this `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="9ceff-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ceff-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ceff-122">Remarks</span></span>  
 <span data-ttu-id="9ceff-123">Если тип является универсальным, `ICorDebugClass` представляет тип, не являющийся экземпляром.</span><span class="sxs-lookup"><span data-stu-id="9ceff-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="9ceff-124">`ICorDebugType`Интерфейс представляет экземпляр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="9ceff-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="9ceff-125">Например, таблица Hashtable \< K, V> будет представлена в `ICorDebugClass` , тогда как Hashtable \< Int32, String> будет представлена `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="9ceff-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="9ceff-126">Типы, не являющиеся универсальными, представлены как, так `ICorDebugClass` и `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="9ceff-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="9ceff-127">Последний интерфейс появился в .NET Framework версии 2,0 для обработки создания экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="9ceff-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ceff-128">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="9ceff-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ceff-129">Требования</span><span class="sxs-lookup"><span data-stu-id="9ceff-129">Requirements</span></span>  
 <span data-ttu-id="9ceff-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ceff-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ceff-131">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ceff-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ceff-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ceff-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ceff-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ceff-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ceff-134">См. также статью</span><span class="sxs-lookup"><span data-stu-id="9ceff-134">See also</span></span>

- [<span data-ttu-id="9ceff-135">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9ceff-135">Debugging Interfaces</span></span>](debugging-interfaces.md)

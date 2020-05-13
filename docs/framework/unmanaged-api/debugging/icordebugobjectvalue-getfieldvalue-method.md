---
title: Метод ICorDebugObjectValue::GetFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 660bc13e8109994f59444c0adebbc97f54de0b43
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207594"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="e3a07-102">Метод ICorDebugObjectValue::GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="e3a07-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="e3a07-103">Возвращает значение указанного поля указанного класса для данного значения объекта.</span><span class="sxs-lookup"><span data-stu-id="e3a07-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3a07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3a07-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3a07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3a07-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="e3a07-106">окне Указатель на объект "ICorDebugClass", представляющий класс, для которого необходимо получить значение поля.</span><span class="sxs-lookup"><span data-stu-id="e3a07-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="e3a07-107">окне `mdFieldDef`Токен, ссылающийся на метаданные, описывающие поле.</span><span class="sxs-lookup"><span data-stu-id="e3a07-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e3a07-108">заполняет Указатель на объект "ICorDebugValue", представляющий значение указанного поля.</span><span class="sxs-lookup"><span data-stu-id="e3a07-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3a07-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e3a07-109">Remarks</span></span>  
 <span data-ttu-id="e3a07-110">Класс, указанный в `pClass` параметре, должен находиться в иерархии класса значения объекта, а поле должно быть полем этого класса.</span><span class="sxs-lookup"><span data-stu-id="e3a07-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="e3a07-111">`GetFieldValue`Метод по-прежнему будет выполняться для универсальных объектов и универсальных классов.</span><span class="sxs-lookup"><span data-stu-id="e3a07-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="e3a07-112">Например, если Мидиктионари \< V> наследуется из \< строки словаря, V>, а значение объекта имеет тип мидиктионари \< Int32>, передача `ICorDebugClass` объекта для словаря \< K, V> успешно получит поле \< строки словаря,> Int32.</span><span class="sxs-lookup"><span data-stu-id="e3a07-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3a07-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e3a07-113">Requirements</span></span>  
 <span data-ttu-id="e3a07-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3a07-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3a07-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3a07-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3a07-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3a07-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3a07-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3a07-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a07-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e3a07-118">See also</span></span>

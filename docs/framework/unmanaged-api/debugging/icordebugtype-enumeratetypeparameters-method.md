---
title: Метод ICorDebugType::EnumerateTypeParameters
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
ms.openlocfilehash: dc6bf4f02c49788e640c6e230f864e3ca8e71b0d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380005"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="0af3c-102">Метод ICorDebugType::EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="0af3c-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="0af3c-103">Возвращает указатель интерфейса на ICorDebugTypeEnum, содержащий <xref:System.Type> Параметры класса, на который ссылается этот объект ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="0af3c-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0af3c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0af3c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0af3c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0af3c-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="0af3c-106">заполняет Указатель на адрес объекта `ICorDebugTypeEnum` , который содержит параметры типа.</span><span class="sxs-lookup"><span data-stu-id="0af3c-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0af3c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0af3c-107">Remarks</span></span>  
 <span data-ttu-id="0af3c-108">Можно использовать, `EnumerateTypeParameters` Если значение корелементтипе, возвращаемое методом [ICorDebugType:: GetType](icordebugtype-gettype-method.md) , равно ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR или ELEMENT_TYPE_FNPTR.</span><span class="sxs-lookup"><span data-stu-id="0af3c-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="0af3c-109">Количество параметров и их порядок зависит от типа:</span><span class="sxs-lookup"><span data-stu-id="0af3c-109">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="0af3c-110">ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE: количество параметров типа, содержащихся в, `ICorDebugTypeEnum` которые возвращает этот метод, будет зависеть от числа формальных параметров типа для соответствующего класса.</span><span class="sxs-lookup"><span data-stu-id="0af3c-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="0af3c-111">Например, если тип — `class Dict<String,int32>` , то `EnumerateTypeParameters` возвратит объект `ICorDebugTypeEnum` , содержащий объекты, представляющие `String` и `int32` в последовательности.</span><span class="sxs-lookup"><span data-stu-id="0af3c-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="0af3c-112">ELEMENT_TYPE_FNPTR: количество параметров типа, содержащихся в, `ICorDebugTypeEnum` будет больше, чем число аргументов, принимаемых функцией.</span><span class="sxs-lookup"><span data-stu-id="0af3c-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="0af3c-113">Первый параметр типа, содержащийся в, `ICorDebugTypeEnum` является типом возвращаемого значения для функции, а последующие параметры типа — параметрами функции.</span><span class="sxs-lookup"><span data-stu-id="0af3c-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="0af3c-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF или ELEMENT_TYPE_PTR: будет возвращен один параметр типа.</span><span class="sxs-lookup"><span data-stu-id="0af3c-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="0af3c-115">Например, если тип является массивом типа, таким как `int32[]` , `EnumerateTypeParameters` возвращает объект `ICorDebugTypeEnum` , содержащий объект, представляющий `int32` .</span><span class="sxs-lookup"><span data-stu-id="0af3c-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0af3c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="0af3c-116">Requirements</span></span>  
 <span data-ttu-id="0af3c-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0af3c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0af3c-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0af3c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0af3c-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0af3c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0af3c-120">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0af3c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

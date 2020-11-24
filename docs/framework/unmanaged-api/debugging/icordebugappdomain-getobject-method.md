---
title: Метод ICorDebugAppDomain::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
ms.openlocfilehash: a163667ea7eca1ed817d642efdb8fc4efa2a0651
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676066"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="bfd79-102">Метод ICorDebugAppDomain::GetObject</span><span class="sxs-lookup"><span data-stu-id="bfd79-102">ICorDebugAppDomain::GetObject Method</span></span>

<span data-ttu-id="bfd79-103">Возвращает указатель интерфейса на домен приложения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="bfd79-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfd79-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfd79-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfd79-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bfd79-105">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="bfd79-106">заполняет Указатель на адрес объекта интерфейса ICorDebugValue, который представляет домен приложения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="bfd79-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfd79-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bfd79-107">Return Value</span></span>  

 <span data-ttu-id="bfd79-108">Если управляемый <xref:System.AppDomain?displayProperty=nameWithType> объект не был создан для этого домена приложения, метод возвращает `S_FALSE` и помещает `NULL` в `*ppObject` .</span><span class="sxs-lookup"><span data-stu-id="bfd79-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfd79-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="bfd79-109">Remarks</span></span>  

 <span data-ttu-id="bfd79-110">Каждый домен приложения в процессе может иметь управляемый <xref:System.AppDomain?displayProperty=nameWithType> объект в среде выполнения, который представляет его.</span><span class="sxs-lookup"><span data-stu-id="bfd79-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="bfd79-111">Эта функция получает объект интерфейса ICorDebugValue, соответствующий этому управляемому <xref:System.AppDomain?displayProperty=nameWithType> объекту.</span><span class="sxs-lookup"><span data-stu-id="bfd79-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfd79-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bfd79-112">Requirements</span></span>  

 <span data-ttu-id="bfd79-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfd79-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfd79-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfd79-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfd79-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfd79-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfd79-116">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfd79-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

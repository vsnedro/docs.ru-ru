---
title: Метод ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 9d195c61d95f084c7b6b40d2c81623fd81cd94cf
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206358"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="28d98-102">Метод ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="28d98-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="28d98-103">Предоставляет информацию о функциях, экспортируемых в ходе выполнения, для пошагового перемещения по управляемому коду.</span><span class="sxs-lookup"><span data-stu-id="28d98-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28d98-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28d98-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28d98-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="28d98-105">Parameters</span></span>  
 <span data-ttu-id="28d98-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="28d98-106">pszExportName</span></span>  
 <span data-ttu-id="28d98-107">[входной] Имя функции экспорта во время выполнения, записываемой в таблице экспорта PE.</span><span class="sxs-lookup"><span data-stu-id="28d98-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="28d98-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="28d98-108">invokeKind</span></span>  
 <span data-ttu-id="28d98-109">заполняет Указатель на член перечисления [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) , описывающий, как экспортируемая функция будет вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="28d98-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="28d98-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="28d98-110">invokePurpose</span></span>  
 <span data-ttu-id="28d98-111">заполняет Указатель на член перечисления [кордебугкодеинвокепурпосе](cordebugcodeinvokepurpose-enumeration.md) , описывающий, почему экспортируемая функция будет вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="28d98-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28d98-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="28d98-112">Return Value</span></span>  
 <span data-ttu-id="28d98-113">Метод может возвращать значения, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="28d98-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="28d98-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="28d98-114">Return value</span></span>|<span data-ttu-id="28d98-115">Описание</span><span class="sxs-lookup"><span data-stu-id="28d98-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="28d98-116">Успешный вызов метода.</span><span class="sxs-lookup"><span data-stu-id="28d98-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="28d98-117">`pInvokeKind`или `pInvokePurpose` имеет **значение NULL**.</span><span class="sxs-lookup"><span data-stu-id="28d98-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="28d98-118">Другие ошибочные значения `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="28d98-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="28d98-119">По мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="28d98-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28d98-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="28d98-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28d98-121">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="28d98-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28d98-122">Требования</span><span class="sxs-lookup"><span data-stu-id="28d98-122">Requirements</span></span>  
 <span data-ttu-id="28d98-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28d98-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28d98-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28d98-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28d98-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28d98-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28d98-126">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28d98-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d98-127">См. также</span><span class="sxs-lookup"><span data-stu-id="28d98-127">See also</span></span>

- [<span data-ttu-id="28d98-128">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="28d98-128">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="28d98-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="28d98-129">Debugging Interfaces</span></span>](debugging-interfaces.md)

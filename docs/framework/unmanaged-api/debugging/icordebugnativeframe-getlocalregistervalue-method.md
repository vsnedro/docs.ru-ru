---
title: Метод ICorDebugNativeFrame::GetLocalRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
ms.openlocfilehash: a90bba4a4dc9ca92ccdc4af1636d194f92fd7373
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695729"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="180ce-102">Метод ICorDebugNativeFrame::GetLocalRegisterValue</span><span class="sxs-lookup"><span data-stu-id="180ce-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>

<span data-ttu-id="180ce-103">Возвращает значение аргумента или локальной переменной, хранящейся в указанном регистре для этого собственного кадра.</span><span class="sxs-lookup"><span data-stu-id="180ce-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="180ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="180ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="180ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="180ce-105">Parameters</span></span>  

 `reg`  
 <span data-ttu-id="180ce-106">окне Значение перечисления "CorDebugRegister", указывающее регистр, содержащий значение.</span><span class="sxs-lookup"><span data-stu-id="180ce-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="180ce-107">окне Целое число, указывающее размер подписи двоичных метаданных, на которую ссылается `pvSigBlob` параметр.</span><span class="sxs-lookup"><span data-stu-id="180ce-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="180ce-108">окне `PCCOR_SIGNATURE` Значение, которое указывает на сигнатуру двоичных метаданных для типа значения.</span><span class="sxs-lookup"><span data-stu-id="180ce-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="180ce-109">заполняет Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение, хранящееся в указанном регистре.</span><span class="sxs-lookup"><span data-stu-id="180ce-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="180ce-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="180ce-110">Remarks</span></span>  

 <span data-ttu-id="180ce-111">`GetLocalRegisterValue`Метод можно использовать либо в машинном кадре, либо в кадре JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="180ce-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="180ce-112">Требования</span><span class="sxs-lookup"><span data-stu-id="180ce-112">Requirements</span></span>  

 <span data-ttu-id="180ce-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="180ce-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="180ce-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="180ce-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="180ce-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="180ce-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="180ce-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="180ce-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="180ce-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="180ce-117">See also</span></span>

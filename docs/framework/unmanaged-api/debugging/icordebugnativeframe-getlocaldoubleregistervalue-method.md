---
title: Метод ICorDebugNativeFrame::GetLocalDoubleRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
ms.openlocfilehash: 10f06fb04099ef947711bc7c5641e5a7f1fa36b7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695717"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="1adb1-102">Метод ICorDebugNativeFrame::GetLocalDoubleRegisterValue</span><span class="sxs-lookup"><span data-stu-id="1adb1-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>

<span data-ttu-id="1adb1-103">Возвращает значение аргумента или локальной переменной, которая хранится в двух указанных регистрах для этого собственного кадра.</span><span class="sxs-lookup"><span data-stu-id="1adb1-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1adb1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1adb1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1adb1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1adb1-105">Parameters</span></span>  

 `highWordReg`  
 <span data-ttu-id="1adb1-106">окне Значение перечисления "CorDebugRegister", указывающее регистр, содержащий старшее слово значения.</span><span class="sxs-lookup"><span data-stu-id="1adb1-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="1adb1-107">окне Значение `CorDebugRegister` перечисления, указывающее регистр, содержащий нижнее слово значения.</span><span class="sxs-lookup"><span data-stu-id="1adb1-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="1adb1-108">окне Целое число, указывающее размер подписи двоичных метаданных, на которую ссылается `pvSigBlob` параметр.</span><span class="sxs-lookup"><span data-stu-id="1adb1-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="1adb1-109">окне `PCCOR_SIGNATURE` Значение, которое указывает на сигнатуру двоичных метаданных для типа значения.</span><span class="sxs-lookup"><span data-stu-id="1adb1-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="1adb1-110">заполняет Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение, хранящееся в указанных регистрах.</span><span class="sxs-lookup"><span data-stu-id="1adb1-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1adb1-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1adb1-111">Remarks</span></span>  

 <span data-ttu-id="1adb1-112">`GetLocalDoubleRegisterValue`Метод можно использовать либо в машинном кадре, либо в кадре JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="1adb1-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1adb1-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1adb1-113">Requirements</span></span>  

 <span data-ttu-id="1adb1-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1adb1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1adb1-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1adb1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1adb1-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1adb1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1adb1-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1adb1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1adb1-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1adb1-118">See also</span></span>

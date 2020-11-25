---
title: Метод ICorDebugNativeFrame::GetLocalRegisterMemoryValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type:
- apiref
ms.openlocfilehash: 4b77ad2f31f10bd14ce7d8242a584da737428344
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709314"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="4a5d8-102">Метод ICorDebugNativeFrame::GetLocalRegisterMemoryValue</span><span class="sxs-lookup"><span data-stu-id="4a5d8-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>

<span data-ttu-id="4a5d8-103">Возвращает значение аргумента или локальной переменной, из которых младшее слово и верхнее слово хранятся в расположении в памяти и указанном регистре соответственно для этого кадра машинного кода.</span><span class="sxs-lookup"><span data-stu-id="4a5d8-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a5d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a5d8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a5d8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4a5d8-105">Parameters</span></span>  

 `highWordReg`  
 <span data-ttu-id="4a5d8-106">окне Значение перечисления "CorDebugRegister", указывающее регистр, содержащий старшее слово значения.</span><span class="sxs-lookup"><span data-stu-id="4a5d8-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="4a5d8-107">окне `CORDB_ADDRESS` Значение типа, указывающее место в памяти, содержащее нижнее слово значения.</span><span class="sxs-lookup"><span data-stu-id="4a5d8-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="4a5d8-108">окне Целое число, указывающее размер подписи двоичных метаданных, на которую ссылается `pvSigBlob` параметр.</span><span class="sxs-lookup"><span data-stu-id="4a5d8-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="4a5d8-109">окне `PCCOR_SIGNATURE` Значение, которое указывает на сигнатуру двоичных метаданных для типа значения.</span><span class="sxs-lookup"><span data-stu-id="4a5d8-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4a5d8-110">заполняет Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение, хранящееся в указанном регистре и расположении в памяти.</span><span class="sxs-lookup"><span data-stu-id="4a5d8-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a5d8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4a5d8-111">Requirements</span></span>  

 <span data-ttu-id="4a5d8-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a5d8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a5d8-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a5d8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a5d8-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a5d8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a5d8-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a5d8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a5d8-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4a5d8-116">See also</span></span>

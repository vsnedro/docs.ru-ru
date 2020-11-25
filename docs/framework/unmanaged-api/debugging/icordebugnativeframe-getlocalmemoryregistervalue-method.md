---
title: Метод ICorDebugNativeFrame::GetLocalMemoryRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
ms.openlocfilehash: 15485ac94ed9074baacc4fd2662a04bdcefcf1e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709327"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="b0f4f-102">Метод ICorDebugNativeFrame::GetLocalMemoryRegisterValue</span><span class="sxs-lookup"><span data-stu-id="b0f4f-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>

<span data-ttu-id="b0f4f-103">Возвращает значение аргумента или локальной переменной, из которых младшее слово и верхнее слово хранятся в указанном регистре и расположении в памяти соответственно для этого кадра машинного кода.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0f4f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0f4f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0f4f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0f4f-105">Parameters</span></span>  

 `highWordAddress`  
 <span data-ttu-id="b0f4f-106">окне `CORDB_ADDRESS` Значение типа, указывающее место в памяти, содержащее верхнее слово значения.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="b0f4f-107">окне Значение перечисления "CorDebugRegister", указывающее регистр, содержащий нижнее слово значения.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="b0f4f-108">окне Целое число, указывающее размер подписи двоичных метаданных, на которую ссылается `pvSigBlob` параметр.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="b0f4f-109">окне `PCCOR_SIGNATURE` Значение, которое указывает на сигнатуру двоичных метаданных для типа значения.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b0f4f-110">заполняет Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение, хранящееся в указанном регистре и расположении в памяти.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0f4f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b0f4f-111">Requirements</span></span>  

 <span data-ttu-id="b0f4f-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0f4f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0f4f-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0f4f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0f4f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0f4f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0f4f-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0f4f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0f4f-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b0f4f-116">See also</span></span>

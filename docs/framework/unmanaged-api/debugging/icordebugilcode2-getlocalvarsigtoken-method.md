---
title: Метод ICorDebugILCode2::GetLocalVarSigToken
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
ms.openlocfilehash: 3b9c2f0e20488826aca202b3ef454104964b8bb9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210349"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="c6712-102">Метод ICorDebugILCode2::GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="c6712-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="c6712-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="c6712-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c6712-104">Получает маркер метаданных для подписи локальной переменной, предназначенной для представленной этим экземпляром функции.</span><span class="sxs-lookup"><span data-stu-id="c6712-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6712-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6712-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6712-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6712-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="c6712-107">[из] Указатель на маркер `mdSignature` для подписи локальной переменной, предназначенной для этой функции, или `mdSignatureNil`, если подпись отсутствует (т. е. если функция не имеет локальных переменных).</span><span class="sxs-lookup"><span data-stu-id="c6712-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6712-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c6712-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6712-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c6712-109">Requirements</span></span>  
 <span data-ttu-id="c6712-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6712-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6712-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6712-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6712-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6712-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6712-113">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6712-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6712-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c6712-114">See also</span></span>

- [<span data-ttu-id="c6712-115">Интерфейс ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="c6712-115">ICorDebugILCode2 Interface</span></span>](icordebugilcode2-interface.md)
- [<span data-ttu-id="c6712-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c6712-116">Debugging Interfaces</span></span>](debugging-interfaces.md)

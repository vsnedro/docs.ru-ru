---
title: Метод ICorDebugMergedAssemblyRecord::GetPublicKey
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: e89ecca25edb0d7eae3a7e65f9585d71ad4ace4d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710601"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="f670b-102">Метод ICorDebugMergedAssemblyRecord::GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="f670b-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>

<span data-ttu-id="f670b-103">Возвращает открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="f670b-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f670b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f670b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,
   [out] ULONG32 *pcbPublicKey,
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f670b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f670b-105">Parameters</span></span>  

 `cbPublicKey`  
 <span data-ttu-id="f670b-106">[in] Максимальное число байтов в массиве `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="f670b-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="f670b-107">[out] Указатель на фактическое число байтов, записанных в массив `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="f670b-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="f670b-108">[out] Указатель на массив байтов, содержащий открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="f670b-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f670b-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f670b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f670b-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="f670b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f670b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f670b-111">Requirements</span></span>  

 <span data-ttu-id="f670b-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f670b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f670b-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f670b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f670b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f670b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f670b-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f670b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f670b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f670b-116">See also</span></span>

- [<span data-ttu-id="f670b-117">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="f670b-117">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="f670b-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f670b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

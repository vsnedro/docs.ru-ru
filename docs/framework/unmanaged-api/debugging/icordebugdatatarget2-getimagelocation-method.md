---
title: Метод ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: 185b6a4979491a323f6eb15ab08a06f87fabc8d3
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976464"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="c2c93-102">Метод ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="c2c93-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="c2c93-103">Возвращает путь для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="c2c93-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2c93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2c93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2c93-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2c93-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="c2c93-106">окне Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="c2c93-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c2c93-107">[входной] Число символов в буфере, которые должен получить путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="c2c93-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c2c93-108">[выходной] Указатель на число символов, записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="c2c93-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="c2c93-109">[выходной] Путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="c2c93-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2c93-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2c93-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2c93-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="c2c93-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2c93-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c2c93-112">Requirements</span></span>  
 <span data-ttu-id="c2c93-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2c93-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2c93-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2c93-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2c93-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2c93-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2c93-116">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2c93-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2c93-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c2c93-117">See also</span></span>

- [<span data-ttu-id="c2c93-118">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="c2c93-118">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="c2c93-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c2c93-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

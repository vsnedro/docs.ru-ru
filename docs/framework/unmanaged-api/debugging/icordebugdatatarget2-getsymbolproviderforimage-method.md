---
title: Метод ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 5a5ccaeb36dcda82c0189026e19c6a7c023f3e1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713773"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="c85d3-102">Метод ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="c85d3-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>

<span data-ttu-id="c85d3-103">Возвращает поставщика символов для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="c85d3-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c85d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c85d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c85d3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c85d3-105">Parameters</span></span>  

 `imageBaseAddress`  
 <span data-ttu-id="c85d3-106">окне Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="c85d3-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="c85d3-107">заполняет Указатель на адрес объекта [метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c85d3-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c85d3-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c85d3-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c85d3-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="c85d3-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c85d3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c85d3-110">Requirements</span></span>  

 <span data-ttu-id="c85d3-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c85d3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c85d3-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c85d3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c85d3-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c85d3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c85d3-114">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c85d3-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c85d3-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c85d3-115">See also</span></span>

- [<span data-ttu-id="c85d3-116">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="c85d3-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="c85d3-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c85d3-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

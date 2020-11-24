---
title: Метод ICorDebugSymbolProvider2::GetFrameProps
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
ms.openlocfilehash: ba1fd104c35b6e6dfdfd771f71eb19f8d532a1d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672015"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="afcb1-102">Метод ICorDebugSymbolProvider2::GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="afcb1-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>

<span data-ttu-id="afcb1-103">Возвращает начальный относительный виртуальный адрес метода и родительского фрейма для указанного относительного виртуального адреса кода.</span><span class="sxs-lookup"><span data-stu-id="afcb1-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afcb1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afcb1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afcb1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="afcb1-105">Parameters</span></span>  

 `codeRva`  
 <span data-ttu-id="afcb1-106">[in] Относительный виртуальный адрес кода.</span><span class="sxs-lookup"><span data-stu-id="afcb1-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="afcb1-107">[out] Указатель на начальный относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="afcb1-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="afcb1-108">[out] Указатель на начальный относительный виртуальный адрес фрейма.</span><span class="sxs-lookup"><span data-stu-id="afcb1-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afcb1-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="afcb1-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afcb1-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="afcb1-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afcb1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="afcb1-111">Requirements</span></span>  

 <span data-ttu-id="afcb1-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afcb1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afcb1-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afcb1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afcb1-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afcb1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afcb1-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afcb1-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afcb1-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="afcb1-116">See also</span></span>

- [<span data-ttu-id="afcb1-117">Интерфейс ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="afcb1-117">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="afcb1-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="afcb1-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

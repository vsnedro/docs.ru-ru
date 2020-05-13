---
title: Метод ICorDebugMergedAssemblyRecord::GetVersion
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: cad71080c86e92beb318722db86011b09ce02e91
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207629"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="214b0-102">Метод ICorDebugMergedAssemblyRecord::GetVersion</span><span class="sxs-lookup"><span data-stu-id="214b0-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="214b0-103">Возвращает сведения о версии сборки.</span><span class="sxs-lookup"><span data-stu-id="214b0-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="214b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="214b0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="214b0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="214b0-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="214b0-106">[out] Указатель на основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="214b0-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="214b0-107">[out] Указатель на дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="214b0-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="214b0-108">[out] Указатель на номер сборки.</span><span class="sxs-lookup"><span data-stu-id="214b0-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="214b0-109">[out] Указатель на номер редакции.</span><span class="sxs-lookup"><span data-stu-id="214b0-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="214b0-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="214b0-110">Remarks</span></span>  
 <span data-ttu-id="214b0-111">Сведения о версии сборки см в разделе, посвященном классу <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="214b0-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="214b0-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="214b0-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="214b0-113">Требования</span><span class="sxs-lookup"><span data-stu-id="214b0-113">Requirements</span></span>  
 <span data-ttu-id="214b0-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="214b0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="214b0-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="214b0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="214b0-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="214b0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="214b0-117">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="214b0-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="214b0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="214b0-118">See also</span></span>

- [<span data-ttu-id="214b0-119">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="214b0-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="214b0-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="214b0-120">Debugging Interfaces</span></span>](debugging-interfaces.md)

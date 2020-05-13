---
title: Метод ICorDebugSymbolProvider::GetMergedAssemblyRecords
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: b7d26fa80a7a8ebe7b4606b914c8cd09c52df1e4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379622"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="5e789-102">Метод ICorDebugSymbolProvider::GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="5e789-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="5e789-103">Возвращает символьные записи для всех объединенных сборок.</span><span class="sxs-lookup"><span data-stu-id="5e789-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e789-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e789-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e789-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e789-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="5e789-106">[in] Количество запрошенных символьных записей.</span><span class="sxs-lookup"><span data-stu-id="5e789-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="5e789-107">[out] Указатель на число  символьных записей, полученных при помощи метода.</span><span class="sxs-lookup"><span data-stu-id="5e789-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="5e789-108">Указатель на массив объектов [икордебугмержедассемблирекорд](icordebugmergedassemblyrecord-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5e789-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e789-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="5e789-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e789-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="5e789-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e789-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5e789-111">Requirements</span></span>  
 <span data-ttu-id="5e789-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e789-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e789-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e789-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e789-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e789-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e789-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e789-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e789-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5e789-116">See also</span></span>

- [<span data-ttu-id="5e789-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="5e789-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="5e789-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5e789-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

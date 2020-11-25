---
title: Метод ICorDebugSymbolProvider::GetMergedAssemblyRecords
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: 10bbcf2e6a536eeb4ab8141c10c177a53faa1c95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730881"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="75ef7-102">Метод ICorDebugSymbolProvider::GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="75ef7-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>

<span data-ttu-id="75ef7-103">Возвращает символьные записи для всех объединенных сборок.</span><span class="sxs-lookup"><span data-stu-id="75ef7-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75ef7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75ef7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75ef7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="75ef7-105">Parameters</span></span>  

 `cRequestedRecords`  
 <span data-ttu-id="75ef7-106">[in] Количество запрошенных символьных записей.</span><span class="sxs-lookup"><span data-stu-id="75ef7-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="75ef7-107">[out] Указатель на число  символьных записей, полученных при помощи метода.</span><span class="sxs-lookup"><span data-stu-id="75ef7-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="75ef7-108">Указатель на массив объектов [икордебугмержедассемблирекорд](icordebugmergedassemblyrecord-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="75ef7-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75ef7-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="75ef7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75ef7-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="75ef7-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75ef7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="75ef7-111">Requirements</span></span>  

 <span data-ttu-id="75ef7-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75ef7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75ef7-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75ef7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75ef7-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75ef7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75ef7-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75ef7-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ef7-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="75ef7-116">See also</span></span>

- [<span data-ttu-id="75ef7-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="75ef7-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="75ef7-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="75ef7-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

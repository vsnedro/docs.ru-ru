---
title: Метод IAssemblyCache::QueryAssemblyInfo
ms.date: 03/30/2017
api_name:
- IAssemblyCache.QueryAssemblyInfo
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type:
- apiref
ms.openlocfilehash: f764be9b80a8d4dcb15791d406412ece9e7e7c87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670931"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="dc87e-102">Метод IAssemblyCache::QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="dc87e-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>

<span data-ttu-id="dc87e-103">Возвращает запрошенные данные о указанной сборке.</span><span class="sxs-lookup"><span data-stu-id="dc87e-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc87e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc87e-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc87e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dc87e-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="dc87e-106">окне Флаги, определенные в Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="dc87e-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="dc87e-107">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="dc87e-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="dc87e-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="dc87e-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
- <span data-ttu-id="dc87e-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="dc87e-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="dc87e-110">окне Имя сборки, для которой будут получены данные.</span><span class="sxs-lookup"><span data-stu-id="dc87e-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="dc87e-111">[вход, выход] Структура [ASSEMBLY_INFO](assembly-info-structure.md) , содержащая данные о сборке.</span><span class="sxs-lookup"><span data-stu-id="dc87e-111">[in, out] An [ASSEMBLY_INFO](assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc87e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="dc87e-112">Requirements</span></span>  

 <span data-ttu-id="dc87e-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc87e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc87e-114">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="dc87e-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="dc87e-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc87e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc87e-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dc87e-116">See also</span></span>

- [<span data-ttu-id="dc87e-117">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="dc87e-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)

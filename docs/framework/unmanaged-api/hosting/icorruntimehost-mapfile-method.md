---
title: Метод ICorRuntimeHost::MapFile
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
ms.openlocfilehash: 60e1d5d49f6f8c6fec060d8751e94410986aa3fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671386"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="44fe5-102">Метод ICorRuntimeHost::MapFile</span><span class="sxs-lookup"><span data-stu-id="44fe5-102">ICorRuntimeHost::MapFile Method</span></span>

<span data-ttu-id="44fe5-103">Сопоставляет указанный файл с памятью.</span><span class="sxs-lookup"><span data-stu-id="44fe5-103">Maps the specified file into memory.</span></span> <span data-ttu-id="44fe5-104">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="44fe5-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44fe5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44fe5-105">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44fe5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="44fe5-106">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="44fe5-107">окне Описатель файла для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="44fe5-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="44fe5-108">заполняет Начальный адрес памяти, с которого начинается сопоставление файла.</span><span class="sxs-lookup"><span data-stu-id="44fe5-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44fe5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="44fe5-109">Requirements</span></span>  

 <span data-ttu-id="44fe5-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44fe5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44fe5-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="44fe5-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44fe5-112">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="44fe5-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44fe5-113">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="44fe5-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44fe5-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="44fe5-114">See also</span></span>

- [<span data-ttu-id="44fe5-115">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="44fe5-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)

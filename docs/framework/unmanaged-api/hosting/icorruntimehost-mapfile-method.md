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
ms.openlocfilehash: 3b1a0cd9a1dfba6f33a20416f2a10c967f871a06
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762673"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="62863-102">Метод ICorRuntimeHost::MapFile</span><span class="sxs-lookup"><span data-stu-id="62863-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="62863-103">Сопоставляет указанный файл с памятью.</span><span class="sxs-lookup"><span data-stu-id="62863-103">Maps the specified file into memory.</span></span> <span data-ttu-id="62863-104">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="62863-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62863-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62863-105">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62863-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="62863-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="62863-107">окне Описатель файла для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="62863-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="62863-108">заполняет Начальный адрес памяти, с которого начинается сопоставление файла.</span><span class="sxs-lookup"><span data-stu-id="62863-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62863-109">Требования</span><span class="sxs-lookup"><span data-stu-id="62863-109">Requirements</span></span>  
 <span data-ttu-id="62863-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62863-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62863-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="62863-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62863-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62863-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62863-113">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="62863-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62863-114">См. также</span><span class="sxs-lookup"><span data-stu-id="62863-114">See also</span></span>

- [<span data-ttu-id="62863-115">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="62863-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)

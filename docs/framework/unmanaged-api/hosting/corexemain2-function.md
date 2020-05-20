---
title: Функция _CorExeMain2
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
ms.openlocfilehash: 8202fe4ec3ae6ef96440f203c5aea6db84744a72
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616589"
---
# <a name="_corexemain2-function"></a><span data-ttu-id="8e5d1-102">Функция _CorExeMain2</span><span class="sxs-lookup"><span data-stu-id="8e5d1-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="8e5d1-103">Выполняет точку входа в указанном коде, сопоставленном с памятью.</span><span class="sxs-lookup"><span data-stu-id="8e5d1-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="8e5d1-104">Эта функция вызывается загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8e5d1-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e5d1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e5d1-105">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e5d1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8e5d1-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="8e5d1-107">окне Указатель на код, сопоставленный с памятью.</span><span class="sxs-lookup"><span data-stu-id="8e5d1-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="8e5d1-108">окне Количество элементов, которые `pUnmappedPE` могут храниться.</span><span class="sxs-lookup"><span data-stu-id="8e5d1-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="8e5d1-109">окне Указатель на имя исполняемого образа.</span><span class="sxs-lookup"><span data-stu-id="8e5d1-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="8e5d1-110">окне Имя файла загрузчика.</span><span class="sxs-lookup"><span data-stu-id="8e5d1-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="8e5d1-111">окне Параметры командной строки, если они есть.</span><span class="sxs-lookup"><span data-stu-id="8e5d1-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e5d1-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8e5d1-112">Requirements</span></span>  
 <span data-ttu-id="8e5d1-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e5d1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e5d1-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="8e5d1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e5d1-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8e5d1-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8e5d1-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e5d1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5d1-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="8e5d1-117">See also</span></span>

- [<span data-ttu-id="8e5d1-118">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="8e5d1-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)

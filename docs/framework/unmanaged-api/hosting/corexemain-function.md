---
title: Функция _CorExeMain
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
ms.openlocfilehash: 935ac478fb966315e81fdcc004761038b28e3178
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616597"
---
# <a name="_corexemain-function"></a><span data-ttu-id="f784c-102">Функция _CorExeMain</span><span class="sxs-lookup"><span data-stu-id="f784c-102">_CorExeMain Function</span></span>
<span data-ttu-id="f784c-103">Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR исполняемой сборки и начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="f784c-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f784c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f784c-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f784c-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="f784c-105">Remarks</span></span>  
 <span data-ttu-id="f784c-106">Эта функция вызывается загрузчиком в процессах, созданных из управляемых исполняемых сборок.</span><span class="sxs-lookup"><span data-stu-id="f784c-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="f784c-107">Для сборок DLL загрузчик вызывает функцию [_CorDllMain](cordllmain-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f784c-107">For DLL assemblies, the loader calls the [_CorDllMain](cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="f784c-108">Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле изображения.</span><span class="sxs-lookup"><span data-stu-id="f784c-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="f784c-109">В Windows 98, Windows ME, Windows NT и Windows 2000 `_CorExeMain` функция вызывается непрямо через исправление в загрузчике операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f784c-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="f784c-110">Во всех остальных версиях Windows он вызывается непосредственно загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f784c-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="f784c-111">Дополнительные сведения см. в подразделе "Примечания" статьи [_CorValidateImage](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f784c-111">For additional information, see the Remarks section in the [_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f784c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f784c-112">Requirements</span></span>  
 <span data-ttu-id="f784c-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f784c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f784c-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f784c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f784c-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f784c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f784c-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f784c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f784c-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f784c-117">See also</span></span>

- [<span data-ttu-id="f784c-118">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="f784c-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)

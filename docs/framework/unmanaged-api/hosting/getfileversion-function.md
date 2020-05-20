---
title: Функция GetFileVersion
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
ms.openlocfilehash: 2dd004a44b20d48dafc72711ac23abcb55739224
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617204"
---
# <a name="getfileversion-function"></a><span data-ttu-id="43702-102">Функция GetFileVersion</span><span class="sxs-lookup"><span data-stu-id="43702-102">GetFileVersion Function</span></span>
<span data-ttu-id="43702-103">Возвращает сведения о версии среды CLR указанного файла, используя указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="43702-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="43702-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="43702-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43702-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43702-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43702-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="43702-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="43702-107">окне Путь к файлу, который необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="43702-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="43702-108">[вход, выход] Буфер, выделенный для возвращаемой информации о версии.</span><span class="sxs-lookup"><span data-stu-id="43702-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="43702-109">окне Размер (в расширенных символах) `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="43702-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="43702-110">заполняет Размер возвращаемого объекта (в байтах) `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="43702-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43702-111">Требования</span><span class="sxs-lookup"><span data-stu-id="43702-111">Requirements</span></span>  
 <span data-ttu-id="43702-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43702-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43702-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="43702-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43702-114">**.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43702-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43702-115">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="43702-115">See also</span></span>

- [<span data-ttu-id="43702-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="43702-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

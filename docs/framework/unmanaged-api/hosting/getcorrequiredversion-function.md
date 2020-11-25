---
title: Функция GetCORRequiredVersion
ms.date: 03/30/2017
api_name:
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
ms.openlocfilehash: 9590d19f4e5f5890af53a108492bd1b6d130fb72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704504"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="a1979-102">Функция GetCORRequiredVersion</span><span class="sxs-lookup"><span data-stu-id="a1979-102">GetCORRequiredVersion Function</span></span>

<span data-ttu-id="a1979-103">Возвращает требуемый номер версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a1979-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="a1979-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a1979-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1979-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1979-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1979-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a1979-106">Parameters</span></span>  

 `pbuffer`  
 <span data-ttu-id="a1979-107">заполняет Буфер, содержащий строку, указывающую номер версии.</span><span class="sxs-lookup"><span data-stu-id="a1979-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="a1979-108">окне Размер буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="a1979-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="a1979-109">заполняет Число байтов, возвращенных в буфере.</span><span class="sxs-lookup"><span data-stu-id="a1979-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1979-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a1979-110">Requirements</span></span>  

 <span data-ttu-id="a1979-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1979-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1979-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a1979-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1979-113">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1979-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1979-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1979-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1979-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a1979-115">See also</span></span>

- [<span data-ttu-id="a1979-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="a1979-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

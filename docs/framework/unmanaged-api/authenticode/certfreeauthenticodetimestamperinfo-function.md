---
title: Функция CertFreeAuthenticodeTimestamperInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
ms.openlocfilehash: 1ef71b14faf66c179030dff2a7d953e27463c1f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674168"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="971e7-102">Функция CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="971e7-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>

<span data-ttu-id="971e7-103">Освобождает ресурсы, выделенные для структуры [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="971e7-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="971e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="971e7-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="971e7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="971e7-105">Parameters</span></span>  

 `pTimestamperInfo`  
 <span data-ttu-id="971e7-106">[в, из] Информация об отметке времени выпуска.</span><span class="sxs-lookup"><span data-stu-id="971e7-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="971e7-107">См. структуру [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="971e7-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="971e7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="971e7-108">Return Value</span></span>  

 <span data-ttu-id="971e7-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="971e7-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="971e7-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="971e7-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="971e7-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="971e7-111">See also</span></span>

- [<span data-ttu-id="971e7-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="971e7-112">Authenticode</span></span>](index.md)

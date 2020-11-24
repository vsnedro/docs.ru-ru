---
title: Функция CertFreeAuthenticodeSignerInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
ms.openlocfilehash: dc6bb5a137a50ec07f89f292e5d9beac4349c3c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674181"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="3aa1c-102">Функция CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="3aa1c-102">CertFreeAuthenticodeSignerInfo Function</span></span>

<span data-ttu-id="3aa1c-103">Освобождает ресурсы, выделенные для структуры [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="3aa1c-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aa1c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3aa1c-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3aa1c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3aa1c-105">Parameters</span></span>  

 `pSignerInfo`  
 <span data-ttu-id="3aa1c-106">[в, из] Информация о подписавшем, которую необходимо указывать.</span><span class="sxs-lookup"><span data-stu-id="3aa1c-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="3aa1c-107">См. структуру [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="3aa1c-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3aa1c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3aa1c-108">Return Value</span></span>  

 <span data-ttu-id="3aa1c-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="3aa1c-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="3aa1c-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3aa1c-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa1c-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3aa1c-111">See also</span></span>

- [<span data-ttu-id="3aa1c-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="3aa1c-112">Authenticode</span></span>](index.md)

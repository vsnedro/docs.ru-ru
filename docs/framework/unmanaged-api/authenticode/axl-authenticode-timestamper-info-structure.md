---
title: Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
ms.openlocfilehash: b6852519da6cf4e12669aa2efa24862053adbc03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674246"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="6ffbd-102">Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="6ffbd-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>

<span data-ttu-id="6ffbd-103">Определяет информацию об отметке времени Authenticode.</span><span class="sxs-lookup"><span data-stu-id="6ffbd-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ffbd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ffbd-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="6ffbd-105">Члены</span><span class="sxs-lookup"><span data-stu-id="6ffbd-105">Members</span></span>  
  
|<span data-ttu-id="6ffbd-106">Член</span><span class="sxs-lookup"><span data-stu-id="6ffbd-106">Member</span></span>|<span data-ttu-id="6ffbd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6ffbd-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="6ffbd-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="6ffbd-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="6ffbd-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="6ffbd-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="6ffbd-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="6ffbd-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="6ffbd-111">Время отметки времени.</span><span class="sxs-lookup"><span data-stu-id="6ffbd-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="6ffbd-112">Контекст цепочки отметки времени.</span><span class="sxs-lookup"><span data-stu-id="6ffbd-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="6ffbd-113">См. структуру [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="6ffbd-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ffbd-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6ffbd-114">See also</span></span>

- [<span data-ttu-id="6ffbd-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="6ffbd-115">Authenticode</span></span>](index.md)

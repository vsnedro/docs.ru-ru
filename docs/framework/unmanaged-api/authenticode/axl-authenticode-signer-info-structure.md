---
title: Структура AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 1bb6df4aa82f8dfc367083732af2065aba9d07b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679992"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="edc02-102">Структура AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="edc02-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>

<span data-ttu-id="edc02-103">Определяет информацию о подписавшем Authenticode.</span><span class="sxs-lookup"><span data-stu-id="edc02-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edc02-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="edc02-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="edc02-105">Члены</span><span class="sxs-lookup"><span data-stu-id="edc02-105">Members</span></span>  
  
|<span data-ttu-id="edc02-106">Член</span><span class="sxs-lookup"><span data-stu-id="edc02-106">Member</span></span>|<span data-ttu-id="edc02-107">Описание</span><span class="sxs-lookup"><span data-stu-id="edc02-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="edc02-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="edc02-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="edc02-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="edc02-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="edc02-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="edc02-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="edc02-111">Хэш-код.</span><span class="sxs-lookup"><span data-stu-id="edc02-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="edc02-112">Описание.</span><span class="sxs-lookup"><span data-stu-id="edc02-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="edc02-113">URL-адрес описания.</span><span class="sxs-lookup"><span data-stu-id="edc02-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="edc02-114">Контекст цепочки подписавшего.</span><span class="sxs-lookup"><span data-stu-id="edc02-114">The chain context of the signer.</span></span> <span data-ttu-id="edc02-115">См. структуру [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="edc02-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="edc02-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="edc02-116">See also</span></span>

- [<span data-ttu-id="edc02-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="edc02-117">Authenticode</span></span>](index.md)

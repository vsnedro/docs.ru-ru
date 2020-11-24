---
title: Функция _AxlGetIssuerPublicKeyHash
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
ms.openlocfilehash: 49674e43109108e41b135cecbec061ad61e14865
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679966"
---
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="fb66e-102">\_Функция Акслжетиссуерпубликкэйхаш</span><span class="sxs-lookup"><span data-stu-id="fb66e-102">\_AxlGetIssuerPublicKeyHash Function</span></span>

<span data-ttu-id="fb66e-103">Получает хэш SHA-1 открытого ключа, связанного с закрытым ключом, который используется для подписания указанного сертификата.</span><span class="sxs-lookup"><span data-stu-id="fb66e-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb66e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb66e-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb66e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb66e-105">Parameters</span></span>  

 `pChainContext`  
 <span data-ttu-id="fb66e-106">[в] Большой двоичный объект открытого ключа CSP.</span><span class="sxs-lookup"><span data-stu-id="fb66e-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="fb66e-107">См. структуру [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="fb66e-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="fb66e-108">[из] Указатель на WCHAR \* для получения шестнадцатеричного кодированного маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="fb66e-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb66e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fb66e-109">Return Value</span></span>  

 <span data-ttu-id="fb66e-110">`S_OK`, если функция выполняется успешно. В противном случае — `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="fb66e-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb66e-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fb66e-111">See also</span></span>

- [<span data-ttu-id="fb66e-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="fb66e-112">Authenticode</span></span>](index.md)

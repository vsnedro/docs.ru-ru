---
title: Функция _AxlRSAKeyValueToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
ms.openlocfilehash: 5c1e2bfc7fd55e807af68744e28faa473daea772
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674220"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="70d47-102">\_Функция Акслрсакэйвалуетопубликкэйтокен</span><span class="sxs-lookup"><span data-stu-id="70d47-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="70d47-103">Преобразует модули и экспоненту в строгое имя маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="70d47-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d47-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70d47-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70d47-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="70d47-105">Parameters</span></span>  

 `pModulusBlob`  
 <span data-ttu-id="70d47-106">окне Большой двоичный объект модуля в кодировке Base64 (из \<Modulus> элемента).</span><span class="sxs-lookup"><span data-stu-id="70d47-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="70d47-107">См. структуру [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="70d47-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="70d47-108">окне Большой двоичный объект экспоненты в кодировке Base64 (из \<Exponent> элемента).</span><span class="sxs-lookup"><span data-stu-id="70d47-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="70d47-109">См. структуру [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="70d47-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="70d47-110">[из] Указатель на WCHAR \* для получения шестнадцатеричного кодированного маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="70d47-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70d47-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="70d47-111">Return Value</span></span>  

 <span data-ttu-id="70d47-112">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="70d47-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="70d47-113">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="70d47-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d47-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="70d47-114">See also</span></span>

- [<span data-ttu-id="70d47-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="70d47-115">Authenticode</span></span>](index.md)

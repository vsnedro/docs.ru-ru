---
title: Метод ICLRStrongName::StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: c727d4524bc40ab90eee90faf16788140a73ad9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677665"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="5ccb4-102">Метод ICLRStrongName::StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="5ccb4-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>

<span data-ttu-id="5ccb4-103">Возвращает маркер, представляющий открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="5ccb4-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="5ccb4-104">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="5ccb4-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ccb4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ccb4-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ccb4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ccb4-106">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="5ccb4-107">окне Структура типа [публиккэйблоб](../strong-naming/publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемую для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="5ccb4-107">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="5ccb4-108">окне Размер (в байтах) `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="5ccb4-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="5ccb4-109">заполняет Маркер строгого имени, соответствующий переданному ключу `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="5ccb4-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="5ccb4-110">Среда CLR выделяет память, в которую возвращается маркер.</span><span class="sxs-lookup"><span data-stu-id="5ccb4-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="5ccb4-111">Вызывающий объект должен освободить эту память с помощью метода [метод iclrstrongname:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5ccb4-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="5ccb4-112">заполняет Размер возвращенного маркера строгого имени в байтах.</span><span class="sxs-lookup"><span data-stu-id="5ccb4-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ccb4-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5ccb4-113">Return Value</span></span>  

 <span data-ttu-id="5ccb4-114">`S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="5ccb4-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ccb4-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5ccb4-115">Remarks</span></span>  

 <span data-ttu-id="5ccb4-116">Маркер строгого имени — это сокращенная форма открытого ключа, используемая для экономии места при хранении ключевых сведений в метаданных.</span><span class="sxs-lookup"><span data-stu-id="5ccb4-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="5ccb4-117">В частности, маркеры строгого имени используются в ссылках на сборки для ссылки на зависимую сборку.</span><span class="sxs-lookup"><span data-stu-id="5ccb4-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ccb4-118">Требования</span><span class="sxs-lookup"><span data-stu-id="5ccb4-118">Requirements</span></span>  

 <span data-ttu-id="5ccb4-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ccb4-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ccb4-120">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="5ccb4-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5ccb4-121">**Библиотека:** Включается в качестве ресурса в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5ccb4-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="5ccb4-122">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ccb4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ccb4-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5ccb4-123">See also</span></span>

- [<span data-ttu-id="5ccb4-124">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="5ccb4-124">StrongNameGetPublicKey Method</span></span>](iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="5ccb4-125">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="5ccb4-125">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="5ccb4-126">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5ccb4-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

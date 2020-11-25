---
title: Функция StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
ms.openlocfilehash: 89556cf0e1ef65c35278a526e10fc791063ea2c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708352"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="6c0c1-102">Функция StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="6c0c1-102">StrongNameTokenFromPublicKey Function</span></span>

<span data-ttu-id="6c0c1-103">Получает маркер, представляющий открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-103">Gets a token representing a public key.</span></span> <span data-ttu-id="6c0c1-104">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="6c0c1-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-105">This function has been deprecated.</span></span> <span data-ttu-id="6c0c1-106">Используйте вместо этого метод [метод iclrstrongname:: StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6c0c1-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c0c1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c0c1-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c0c1-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c0c1-108">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="6c0c1-109">окне Структура типа [публиккэйблоб](publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемую для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="6c0c1-110">окне Размер (в байтах) `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="6c0c1-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="6c0c1-111">заполняет Маркер строгого имени, соответствующий переданному ключу `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="6c0c1-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="6c0c1-112">Среда CLR выделяет память, в которую возвращается маркер.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="6c0c1-113">Вызывающий объект должен освободить эту память с помощью функции [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="6c0c1-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="6c0c1-114">заполняет Размер возвращенного маркера строгого имени в байтах.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c0c1-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6c0c1-115">Return Value</span></span>  

 <span data-ttu-id="6c0c1-116">`true` При успешном завершении; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="6c0c1-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c0c1-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6c0c1-117">Remarks</span></span>  

 <span data-ttu-id="6c0c1-118">Маркер строгого имени — это сокращенная форма открытого ключа, используемая для экономии места при хранении ключевых сведений в метаданных.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="6c0c1-119">В частности, маркеры строгого имени используются в ссылках на сборки для ссылки на зависимую сборку.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="6c0c1-120">Если `StrongNameTokenFromPublicKey` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c0c1-121">Требования</span><span class="sxs-lookup"><span data-stu-id="6c0c1-121">Requirements</span></span>  

 <span data-ttu-id="6c0c1-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c0c1-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c0c1-123">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="6c0c1-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6c0c1-124">**Библиотека:** Включается в качестве ресурса в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6c0c1-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="6c0c1-125">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c0c1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c0c1-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6c0c1-126">See also</span></span>

- [<span data-ttu-id="6c0c1-127">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="6c0c1-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="6c0c1-128">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="6c0c1-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="6c0c1-129">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="6c0c1-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)

---
title: Функция StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
ms.openlocfilehash: 6a2b3afe66f1eaa358c5f80de50f14ceb730048b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708482"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="3c3cd-102">Функция StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="3c3cd-102">StrongNameSignatureSize Function</span></span>

<span data-ttu-id="3c3cd-103">Возвращает размер подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="3c3cd-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="3c3cd-104">`StrongNameSignatureSize` обычно используется компиляторами для определения объема пространства, резервируемого в файле при создании сборки с отложенной подписью.</span><span class="sxs-lookup"><span data-stu-id="3c3cd-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="3c3cd-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="3c3cd-105">This function has been deprecated.</span></span> <span data-ttu-id="3c3cd-106">Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3c3cd-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c3cd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c3cd-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="3c3cd-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c3cd-108">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="3c3cd-109">окне Структура типа [публиккэйблоб](publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемую для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="3c3cd-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="3c3cd-110">окне Размер (в байтах) `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="3c3cd-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="3c3cd-111">окне Число байтов, необходимое для хранения подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="3c3cd-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c3cd-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3c3cd-112">Return Value</span></span>  

 <span data-ttu-id="3c3cd-113">`true` При успешном завершении; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="3c3cd-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c3cd-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3c3cd-114">Remarks</span></span>  

 <span data-ttu-id="3c3cd-115">Если `StrongNameSignatureSize` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="3c3cd-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c3cd-116">Требования</span><span class="sxs-lookup"><span data-stu-id="3c3cd-116">Requirements</span></span>  

 <span data-ttu-id="3c3cd-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c3cd-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c3cd-118">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="3c3cd-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3c3cd-119">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c3cd-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c3cd-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c3cd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c3cd-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3c3cd-121">See also</span></span>

- [<span data-ttu-id="3c3cd-122">Метод StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="3c3cd-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="3c3cd-123">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="3c3cd-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

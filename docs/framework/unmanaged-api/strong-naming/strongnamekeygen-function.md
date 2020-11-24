---
title: Функция StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
ms.openlocfilehash: 4844701784a3e6a1008a5deb2bdff3b3ba47aa7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691413"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="aa942-102">Функция StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="aa942-102">StrongNameKeyGen Function</span></span>

<span data-ttu-id="aa942-103">Создает пару открытого и закрытого ключей для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="aa942-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="aa942-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="aa942-104">This function has been deprecated.</span></span> <span data-ttu-id="aa942-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) .</span><span class="sxs-lookup"><span data-stu-id="aa942-105">Use the [ICLRStrongName::StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa942-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa942-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa942-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa942-107">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="aa942-108">окне Запрошенное имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="aa942-108">[in] The requested key container name.</span></span> <span data-ttu-id="aa942-109">`wszKeyContainer` должен быть непустой строкой или иметь значение NULL для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="aa942-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="aa942-110">окне Указывает, следует ли оставить зарегистрированный ключ.</span><span class="sxs-lookup"><span data-stu-id="aa942-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="aa942-111">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="aa942-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="aa942-112">0x00000000 — используется, если `wszKeyContainer` параметр имеет значение null, чтобы создать имя контейнера временного ключа.</span><span class="sxs-lookup"><span data-stu-id="aa942-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="aa942-113">0x00000001 ( `SN_LEAVE_KEY` ) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="aa942-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="aa942-114">заполняет Возвращаемая пара открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="aa942-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="aa942-115">заполняет Размер (в байтах) `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="aa942-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa942-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="aa942-116">Return Value</span></span>  

 <span data-ttu-id="aa942-117">`true` При успешном завершении; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="aa942-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa942-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="aa942-118">Remarks</span></span>  

 <span data-ttu-id="aa942-119">`StrongNameKeyGen`Функция создает 1024-разрядный ключ.</span><span class="sxs-lookup"><span data-stu-id="aa942-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="aa942-120">После извлечения ключа необходимо вызвать функцию [StrongNameFreeBuffer](strongnamefreebuffer-function.md) , чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="aa942-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="aa942-121">Если `StrongNameKeyGen` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="aa942-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa942-122">Требования</span><span class="sxs-lookup"><span data-stu-id="aa942-122">Requirements</span></span>  

 <span data-ttu-id="aa942-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa942-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa942-124">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="aa942-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="aa942-125">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa942-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aa942-126">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa942-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa942-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aa942-127">See also</span></span>

- [<span data-ttu-id="aa942-128">Метод StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="aa942-128">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="aa942-129">Метод StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="aa942-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="aa942-130">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="aa942-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

---
title: Метод ICLRStrongName::StrongNameKeyGenEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
ms.openlocfilehash: fb18b7b5ac73a1f270af6fae95a23e04b17ca5f1
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763076"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="660ec-102">Метод ICLRStrongName::StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="660ec-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="660ec-103">Создает новую пару открытого и закрытого ключей с указанным размером ключа для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="660ec-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="660ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="660ec-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="660ec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="660ec-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="660ec-106">окне Запрошенное имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="660ec-106">[in] The requested key container name.</span></span> <span data-ttu-id="660ec-107">`wszKeyContainer`значение должно быть непустой строкой или null для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="660ec-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="660ec-108">окне Значение типа, указывающее, следует ли оставлять зарегистрированный ключ.</span><span class="sxs-lookup"><span data-stu-id="660ec-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="660ec-109">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="660ec-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="660ec-110">0x00000000 — используется, если `wszKeyContainer` параметр имеет значение null, чтобы создать имя контейнера временного ключа.</span><span class="sxs-lookup"><span data-stu-id="660ec-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="660ec-111">0x00000001 ( `SN_LEAVE_KEY` ) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="660ec-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="660ec-112">окне Запрошенный размер ключа в битах.</span><span class="sxs-lookup"><span data-stu-id="660ec-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="660ec-113">заполняет Возвращаемая пара открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="660ec-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="660ec-114">заполняет Размер (в байтах) `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="660ec-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="660ec-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="660ec-115">Return Value</span></span>  
 <span data-ttu-id="660ec-116">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="660ec-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="660ec-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="660ec-117">Remarks</span></span>  
 <span data-ttu-id="660ec-118">Для подписывания сборки строгим именем в .NET Framework версиях 1,0 и 1,1 требуется a `dwKeySize` из 1024 бит. в версии 2,0 добавлена поддержка для 2048-разрядных ключей.</span><span class="sxs-lookup"><span data-stu-id="660ec-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="660ec-119">После извлечения ключа необходимо вызвать метод [метод iclrstrongname:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) , чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="660ec-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="660ec-120">Требования</span><span class="sxs-lookup"><span data-stu-id="660ec-120">Requirements</span></span>  
 <span data-ttu-id="660ec-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="660ec-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="660ec-122">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="660ec-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="660ec-123">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="660ec-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="660ec-124">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="660ec-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="660ec-125">См. также</span><span class="sxs-lookup"><span data-stu-id="660ec-125">See also</span></span>

- [<span data-ttu-id="660ec-126">Метод StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="660ec-126">StrongNameKeyGen Method</span></span>](iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="660ec-127">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="660ec-127">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

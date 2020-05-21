---
title: Метод ICLRStrongName::StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
ms.openlocfilehash: db5c0dbe57607c7a3bf8b97cee734415aa934336
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763089"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="c7d03-102">Метод ICLRStrongName::StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="c7d03-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="c7d03-103">Создает пару открытого и закрытого ключей для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="c7d03-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7d03-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7d03-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7d03-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="c7d03-106">окне Запрошенное имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="c7d03-106">[in] The requested key container name.</span></span> <span data-ttu-id="c7d03-107">`wszKeyContainer`значение должно быть непустой строкой или null для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="c7d03-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c7d03-108">окне Значение типа, указывающее, следует ли оставлять зарегистрированный ключ.</span><span class="sxs-lookup"><span data-stu-id="c7d03-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="c7d03-109">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="c7d03-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="c7d03-110">0x00000000 — используется, если `wszKeyContainer` параметр имеет значение null, чтобы создать имя контейнера временного ключа.</span><span class="sxs-lookup"><span data-stu-id="c7d03-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="c7d03-111">0x00000001 ( `SN_LEAVE_KEY` ) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="c7d03-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="c7d03-112">заполняет Возвращаемая пара открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="c7d03-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="c7d03-113">заполняет Размер (в байтах) `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="c7d03-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7d03-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c7d03-114">Return Value</span></span>  
 <span data-ttu-id="c7d03-115">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="c7d03-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7d03-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c7d03-116">Remarks</span></span>  
 <span data-ttu-id="c7d03-117">Метод [метод iclrstrongname:: StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) создает ключ 1024-bit.</span><span class="sxs-lookup"><span data-stu-id="c7d03-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="c7d03-118">После извлечения ключа необходимо вызвать метод [метод iclrstrongname:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) , чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="c7d03-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7d03-119">Требования</span><span class="sxs-lookup"><span data-stu-id="c7d03-119">Requirements</span></span>  
 <span data-ttu-id="c7d03-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7d03-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7d03-121">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="c7d03-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c7d03-122">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c7d03-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7d03-123">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7d03-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7d03-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c7d03-124">See also</span></span>

- [<span data-ttu-id="c7d03-125">Метод StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="c7d03-125">StrongNameKeyGenEx Method</span></span>](iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="c7d03-126">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c7d03-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

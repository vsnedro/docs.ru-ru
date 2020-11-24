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
ms.openlocfilehash: 42a9fc1a05e97bbd893f0a2e77087e6524ad844f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674545"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="664ec-102">Метод ICLRStrongName::StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="664ec-102">ICLRStrongName::StrongNameKeyGen Method</span></span>

<span data-ttu-id="664ec-103">Создает пару открытого и закрытого ключей для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="664ec-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="664ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="664ec-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="664ec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="664ec-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="664ec-106">окне Запрошенное имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="664ec-106">[in] The requested key container name.</span></span> <span data-ttu-id="664ec-107">`wszKeyContainer` значение должно быть непустой строкой или null для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="664ec-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="664ec-108">окне Значение типа, указывающее, следует ли оставлять зарегистрированный ключ.</span><span class="sxs-lookup"><span data-stu-id="664ec-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="664ec-109">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="664ec-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="664ec-110">0x00000000 — используется, если `wszKeyContainer` параметр имеет значение null, чтобы создать имя контейнера временного ключа.</span><span class="sxs-lookup"><span data-stu-id="664ec-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="664ec-111">0x00000001 ( `SN_LEAVE_KEY` ) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="664ec-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="664ec-112">заполняет Возвращаемая пара открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="664ec-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="664ec-113">заполняет Размер (в байтах) `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="664ec-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="664ec-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="664ec-114">Return Value</span></span>  

 <span data-ttu-id="664ec-115">`S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="664ec-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="664ec-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="664ec-116">Remarks</span></span>  

 <span data-ttu-id="664ec-117">Метод [метод iclrstrongname:: StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md) создает ключ 1024-bit.</span><span class="sxs-lookup"><span data-stu-id="664ec-117">The [ICLRStrongName::StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="664ec-118">После извлечения ключа необходимо вызвать метод [метод iclrstrongname:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) , чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="664ec-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="664ec-119">Требования</span><span class="sxs-lookup"><span data-stu-id="664ec-119">Requirements</span></span>  

 <span data-ttu-id="664ec-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="664ec-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="664ec-121">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="664ec-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="664ec-122">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="664ec-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="664ec-123">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="664ec-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="664ec-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="664ec-124">See also</span></span>

- [<span data-ttu-id="664ec-125">Метод StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="664ec-125">StrongNameKeyGenEx Method</span></span>](iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="664ec-126">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="664ec-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

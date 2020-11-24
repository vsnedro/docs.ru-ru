---
title: Метод ICLRStrongName::StrongNameKeyInstall
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type:
- apiref
ms.openlocfilehash: 7e0c689dad0c288e3af3a3d64ee1bba1c44053c1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674532"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="8bb3b-102">Метод ICLRStrongName::StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="8bb3b-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>

<span data-ttu-id="8bb3b-103">Импортирует пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bb3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bb3b-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bb3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8bb3b-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="8bb3b-106">окне Имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-106">[in] The name of the key container.</span></span> <span data-ttu-id="8bb3b-107">`wszKeyContainer` значение должно быть непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="8bb3b-108">окне Пара двоичных ключей.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="8bb3b-109">окне Размер (в байтах) `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="8bb3b-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bb3b-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8bb3b-110">Return Value</span></span>  

 <span data-ttu-id="8bb3b-111">`S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="8bb3b-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bb3b-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8bb3b-112">Remarks</span></span>  

 <span data-ttu-id="8bb3b-113">Чтобы удалить контейнер ключей, используйте метод [метод iclrstrongname:: StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8bb3b-113">Use the [ICLRStrongName::StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bb3b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8bb3b-114">Requirements</span></span>  

 <span data-ttu-id="8bb3b-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bb3b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bb3b-116">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="8bb3b-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8bb3b-117">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8bb3b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8bb3b-118">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bb3b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb3b-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8bb3b-119">See also</span></span>

- [<span data-ttu-id="8bb3b-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="8bb3b-120">StrongNameKeyDelete Method</span></span>](iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="8bb3b-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="8bb3b-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

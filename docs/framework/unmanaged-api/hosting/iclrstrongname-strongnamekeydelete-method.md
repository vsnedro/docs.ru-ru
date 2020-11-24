---
title: Метод ICLRStrongName::StrongNameKeyDelete
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
ms.openlocfilehash: 46345ae570673c9c9c0c58fb6edea1464ba8dd91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671698"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="b3cd2-102">Метод ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="b3cd2-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>

<span data-ttu-id="b3cd2-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="b3cd2-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3cd2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3cd2-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3cd2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3cd2-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="b3cd2-106">окне Имя удаляемого контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="b3cd2-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3cd2-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b3cd2-107">Return Value</span></span>  

 <span data-ttu-id="b3cd2-108">`S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="b3cd2-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3cd2-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b3cd2-109">Remarks</span></span>  

 <span data-ttu-id="b3cd2-110">Используйте метод [метод iclrstrongname:: StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) для импорта пары открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="b3cd2-110">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3cd2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b3cd2-111">Requirements</span></span>  

 <span data-ttu-id="b3cd2-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3cd2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3cd2-113">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="b3cd2-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b3cd2-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3cd2-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3cd2-115">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3cd2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3cd2-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b3cd2-116">See also</span></span>

- [<span data-ttu-id="b3cd2-117">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="b3cd2-117">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="b3cd2-118">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b3cd2-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

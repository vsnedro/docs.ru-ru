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
ms.openlocfilehash: 8f6f2445d88d608d51be4e6fe1e064efbb58325d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763102"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="ccf4a-102">Метод ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="ccf4a-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="ccf4a-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="ccf4a-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccf4a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccf4a-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccf4a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ccf4a-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="ccf4a-106">окне Имя удаляемого контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="ccf4a-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccf4a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ccf4a-107">Return Value</span></span>  
 <span data-ttu-id="ccf4a-108">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="ccf4a-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccf4a-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ccf4a-109">Remarks</span></span>  
 <span data-ttu-id="ccf4a-110">Используйте метод [метод iclrstrongname:: StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) для импорта пары открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="ccf4a-110">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccf4a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ccf4a-111">Requirements</span></span>  
 <span data-ttu-id="ccf4a-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccf4a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccf4a-113">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="ccf4a-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ccf4a-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ccf4a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccf4a-115">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccf4a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf4a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ccf4a-116">See also</span></span>

- [<span data-ttu-id="ccf4a-117">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="ccf4a-117">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="ccf4a-118">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ccf4a-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

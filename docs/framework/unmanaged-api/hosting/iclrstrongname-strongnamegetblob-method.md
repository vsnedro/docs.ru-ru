---
title: Метод ICLRStrongName::StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
ms.openlocfilehash: 824dcf89bacec27ced7cc431a9646d00fb879430
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674675"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="c487b-102">Метод ICLRStrongName::StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="c487b-102">ICLRStrongName::StrongNameGetBlob Method</span></span>

<span data-ttu-id="c487b-103">Заполняет указанный буфер двоичным представлением исполняемого файла по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="c487b-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c487b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c487b-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c487b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c487b-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="c487b-106">окне Допустимый путь к исполняемому файлу для загрузки.</span><span class="sxs-lookup"><span data-stu-id="c487b-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="c487b-107">окне Буфер, в который загружается исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="c487b-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="c487b-108">[вход, выход] Запрошенный максимальный размер (в байтах) `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="c487b-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="c487b-109">При возврате фактический размер (в байтах) для `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="c487b-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c487b-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c487b-110">Return Value</span></span>  

 <span data-ttu-id="c487b-111">`S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="c487b-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c487b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c487b-112">Requirements</span></span>  

 <span data-ttu-id="c487b-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c487b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c487b-114">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="c487b-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c487b-115">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c487b-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c487b-116">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c487b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c487b-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c487b-117">See also</span></span>

- [<span data-ttu-id="c487b-118">Метод StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="c487b-118">StrongNameGetBlobFromImage Method</span></span>](iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="c487b-119">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c487b-119">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

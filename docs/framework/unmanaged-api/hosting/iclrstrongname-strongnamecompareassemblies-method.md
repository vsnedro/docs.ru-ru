---
title: Метод ICLRStrongName::StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
ms.openlocfilehash: 0087636c68d0748ad2b143de9b132278ab9d43f5
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762062"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="dcab6-102">Метод ICLRStrongName::StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="dcab6-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="dcab6-103">Определяет, отличаются ли две сборки только подписями строгого имени.</span><span class="sxs-lookup"><span data-stu-id="dcab6-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcab6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcab6-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcab6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dcab6-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="dcab6-106">окне Путь к первой сборке.</span><span class="sxs-lookup"><span data-stu-id="dcab6-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="dcab6-107">окне Путь к второй сборке.</span><span class="sxs-lookup"><span data-stu-id="dcab6-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="dcab6-108">заполняет Одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dcab6-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="dcab6-109">`SN_CMP_DIFFERENT`(0) — указывает, что сборки содержат различные данные.</span><span class="sxs-lookup"><span data-stu-id="dcab6-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="dcab6-110">`SN_CMP_IDENTICAL`(1) — указывает, что сборки точно одинаковы, включая их подписи и контрольные суммы.</span><span class="sxs-lookup"><span data-stu-id="dcab6-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="dcab6-111">`SN_CMP_SIGONLY`(2) — указывает, что сборки отличаются только сигнатурой и контрольной суммой.</span><span class="sxs-lookup"><span data-stu-id="dcab6-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dcab6-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dcab6-112">Return Value</span></span>  
 <span data-ttu-id="dcab6-113">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="dcab6-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcab6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="dcab6-114">Requirements</span></span>  
 <span data-ttu-id="dcab6-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcab6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcab6-116">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="dcab6-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="dcab6-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dcab6-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dcab6-118">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcab6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcab6-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="dcab6-119">Remarks</span></span>  
 <span data-ttu-id="dcab6-120">Подпись строгого имени сборки состоит из текстового имени, версии, языка и региональных параметров сборки, а также токена открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="dcab6-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcab6-121">См. также</span><span class="sxs-lookup"><span data-stu-id="dcab6-121">See also</span></span>

- [<span data-ttu-id="dcab6-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="dcab6-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

---
title: Метод ICLRStrongName::StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
ms.openlocfilehash: 9caeb72c57260012ae2b459950bf19d907da1d98
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671555"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="a5fb1-102">Метод ICLRStrongName::StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="a5fb1-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>

<span data-ttu-id="a5fb1-103">Возвращает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="a5fb1-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5fb1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5fb1-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5fb1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5fb1-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="a5fb1-106">окне Путь к переносимому исполняемому файлу (exe или DLL) для проверяемой сборки.</span><span class="sxs-lookup"><span data-stu-id="a5fb1-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="a5fb1-107">[входные] `true` для выполнения проверки, даже если необходимо переопределить параметры реестра; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="a5fb1-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="a5fb1-108">[out] `true` значение, если подпись строгого имени проверена; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="a5fb1-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="a5fb1-109">`pfWasVerified` также имеет значение, `false` Если проверка прошла успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="a5fb1-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5fb1-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a5fb1-110">Return Value</span></span>  

 <span data-ttu-id="a5fb1-111">`S_OK` значение, если проверка прошла успешно; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="a5fb1-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5fb1-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a5fb1-112">Remarks</span></span>  

 <span data-ttu-id="a5fb1-113">Метод [метод iclrstrongname:: StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) предоставляет такую возможность, как метод [метод iclrstrongname:: StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a5fb1-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="a5fb1-114">Однако второй входной параметр и выходной параметр для [метод iclrstrongname:: StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) имеют тип, `BOOLEAN` а не `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="a5fb1-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5fb1-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a5fb1-115">Requirements</span></span>  

 <span data-ttu-id="a5fb1-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5fb1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5fb1-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="a5fb1-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a5fb1-118">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5fb1-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5fb1-119">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5fb1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5fb1-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a5fb1-120">See also</span></span>

- [<span data-ttu-id="a5fb1-121">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="a5fb1-121">StrongNameSignatureVerification Method</span></span>](iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="a5fb1-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a5fb1-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

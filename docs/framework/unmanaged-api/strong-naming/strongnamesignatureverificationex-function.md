---
title: Функция StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
ms.openlocfilehash: 27417c379411e242c48d6d9b0c99de833f7ede8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719272"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="e390b-102">Функция StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="e390b-102">StrongNameSignatureVerificationEx Function</span></span>

<span data-ttu-id="e390b-103">Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="e390b-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="e390b-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="e390b-104">This function has been deprecated.</span></span> <span data-ttu-id="e390b-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e390b-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e390b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e390b-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e390b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e390b-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="e390b-108">окне Путь к переносимому исполняемому файлу (exe или DLL) для проверяемой сборки.</span><span class="sxs-lookup"><span data-stu-id="e390b-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="e390b-109">[входные] `true` для выполнения проверки, даже если необходимо переопределить параметры реестра; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="e390b-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="e390b-110">[out] `true` значение, если подпись строгого имени проверена; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="e390b-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="e390b-111">`pfWasVerified` также имеет значение, `false` Если проверка прошла успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="e390b-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e390b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e390b-112">Return Value</span></span>  

 <span data-ttu-id="e390b-113">`true` значение, если проверка прошла успешно; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="e390b-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e390b-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e390b-114">Remarks</span></span>  

 <span data-ttu-id="e390b-115">`StrongNameSignatureVerificationEx` предоставляет такую возможность, как функция [StrongNameSignatureVerification](strongnamesignatureverification-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e390b-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="e390b-116">Однако второй входной параметр и выходной параметр для `StrongNameSignatureVerificationEx` имеют тип, `BOOLEAN` а не `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="e390b-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e390b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="e390b-117">Requirements</span></span>  

 <span data-ttu-id="e390b-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e390b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e390b-119">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="e390b-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e390b-120">**Библиотека:** Включается в качестве ресурса в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e390b-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="e390b-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e390b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e390b-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e390b-122">See also</span></span>

- [<span data-ttu-id="e390b-123">Метод StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="e390b-123">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="e390b-124">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="e390b-124">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="e390b-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e390b-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

---
title: Функция StrongNameSignatureVerificationFromImage
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
ms.openlocfilehash: b90cc6fe99cf592f1b3fd117888462a957e4ce35
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708430"
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="5a2d4-102">Функция StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="5a2d4-102">StrongNameSignatureVerificationFromImage Function</span></span>

<span data-ttu-id="5a2d4-103">Проверяет допустимость сборки, которая уже была сопоставлена с памятью, для связанного открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="5a2d4-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-104">This function has been deprecated.</span></span> <span data-ttu-id="5a2d4-105">Используйте вместо этого метод [метод iclrstrongname:: стронгнамеверификатионфромимаже](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5a2d4-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a2d4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a2d4-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a2d4-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a2d4-107">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="5a2d4-108">окне Относительный виртуальный адрес сопоставленного манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="5a2d4-109">окне Размер сопоставленного изображения в байтах.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="5a2d4-110">окне Флаги, влияющие на поведение при проверке.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="5a2d4-111">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="5a2d4-112">`SN_INFLAG_FORCE_VER` (0x00000001) — принудительная проверка, даже если необходимо переопределить параметры реестра.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="5a2d4-113">`SN_INFLAG_INSTALL` (0x00000002) — указывает, что это первая проверка, выполняемая на этом образе.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="5a2d4-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) — указывает, что кэш будет разрешать доступ только тем пользователям, у которых есть права администратора.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="5a2d4-115">`SN_INFLAG_USER_ACCESS` (0x00000008) — указывает, что сборка будет доступна только текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="5a2d4-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) — указывает, что кэш не предоставляет никаких гарантий ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="5a2d4-117">`SN_INFLAG_RUNTIME` (0x80000000) — зарезервировано для внутренней отладки.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="5a2d4-118">заполняет Флаг для дополнительных выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="5a2d4-119">Поддерживается следующее значение:</span><span class="sxs-lookup"><span data-stu-id="5a2d4-119">The following value is supported:</span></span>  
  
- <span data-ttu-id="5a2d4-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) — это значение `false` указывает, что проверка прошла удачно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a2d4-121">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5a2d4-121">Return Value</span></span>  

 <span data-ttu-id="5a2d4-122">`true` При успешном завершении; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="5a2d4-122">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a2d4-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5a2d4-123">Remarks</span></span>  

 <span data-ttu-id="5a2d4-124">Если `StrongNameSignatureVerificationFromImage` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="5a2d4-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a2d4-125">Требования</span><span class="sxs-lookup"><span data-stu-id="5a2d4-125">Requirements</span></span>  

 <span data-ttu-id="5a2d4-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a2d4-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a2d4-127">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="5a2d4-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5a2d4-128">**Библиотека:** Включается в качестве ресурса в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5a2d4-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="5a2d4-129">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a2d4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a2d4-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5a2d4-130">See also</span></span>

- [<span data-ttu-id="5a2d4-131">Метод StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="5a2d4-131">StrongNameSignatureVerificationFromImage Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [<span data-ttu-id="5a2d4-132">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5a2d4-132">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

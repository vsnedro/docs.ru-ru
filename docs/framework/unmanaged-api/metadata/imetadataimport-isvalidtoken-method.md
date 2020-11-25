---
title: Метод IMetaDataImport::IsValidToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
ms.openlocfilehash: b4dc1e60f3d29e2671882d1900a1c49e56969601
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702866"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="08484-102">Метод IMetaDataImport::IsValidToken</span><span class="sxs-lookup"><span data-stu-id="08484-102">IMetaDataImport::IsValidToken Method</span></span>

<span data-ttu-id="08484-103">Возвращает значение, указывающее, содержится ли в заданном токене допустимая ссылка на объект кода.</span><span class="sxs-lookup"><span data-stu-id="08484-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08484-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08484-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08484-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08484-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="08484-106">окне Токен, для которого проверяется допустимость ссылки.</span><span class="sxs-lookup"><span data-stu-id="08484-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08484-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="08484-107">Return Value</span></span>  

 <span data-ttu-id="08484-108">`true` Если `tk` является допустимым токеном метаданных в текущей области.</span><span class="sxs-lookup"><span data-stu-id="08484-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="08484-109">В противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="08484-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08484-110">Требования</span><span class="sxs-lookup"><span data-stu-id="08484-110">Requirements</span></span>  

 <span data-ttu-id="08484-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08484-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08484-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="08484-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08484-113">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08484-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08484-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08484-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08484-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="08484-115">See also</span></span>

- [<span data-ttu-id="08484-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="08484-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="08484-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="08484-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

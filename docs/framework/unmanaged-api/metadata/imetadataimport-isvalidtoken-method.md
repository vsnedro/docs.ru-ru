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
ms.openlocfilehash: 9190d021b801be951d214406dde7e6d76da15608
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503445"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="3a577-102">Метод IMetaDataImport::IsValidToken</span><span class="sxs-lookup"><span data-stu-id="3a577-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="3a577-103">Возвращает значение, указывающее, содержится ли в заданном токене допустимая ссылка на объект кода.</span><span class="sxs-lookup"><span data-stu-id="3a577-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a577-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a577-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a577-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a577-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3a577-106">окне Токен, для которого проверяется допустимость ссылки.</span><span class="sxs-lookup"><span data-stu-id="3a577-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a577-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3a577-107">Return Value</span></span>  
 <span data-ttu-id="3a577-108">`true`Если `tk` является допустимым токеном метаданных в текущей области.</span><span class="sxs-lookup"><span data-stu-id="3a577-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="3a577-109">В противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="3a577-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a577-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3a577-110">Requirements</span></span>  
 <span data-ttu-id="3a577-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a577-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a577-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3a577-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a577-113">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3a577-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a577-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a577-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a577-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3a577-115">See also</span></span>

- [<span data-ttu-id="3a577-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3a577-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3a577-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3a577-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

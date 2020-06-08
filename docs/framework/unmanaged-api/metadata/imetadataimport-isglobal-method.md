---
title: Метод IMetaDataImport::IsGlobal
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
ms.openlocfilehash: d477976952d2c1875a620d1397fd43e5c5e2836f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503475"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="03d30-102">Метод IMetaDataImport::IsGlobal</span><span class="sxs-lookup"><span data-stu-id="03d30-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="03d30-103">Возвращает значение, указывающее на наличие глобальной области у поля, метода или типа, представленного заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="03d30-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03d30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03d30-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03d30-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="03d30-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="03d30-106">окне Токен метаданных, представляющий тип, поле или метод.</span><span class="sxs-lookup"><span data-stu-id="03d30-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="03d30-107">[out] 1, если объект имеет глобальную область видимости; в противном случае — 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="03d30-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03d30-108">Требования</span><span class="sxs-lookup"><span data-stu-id="03d30-108">Requirements</span></span>  
 <span data-ttu-id="03d30-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03d30-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03d30-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="03d30-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03d30-111">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="03d30-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="03d30-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03d30-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d30-113">См. также</span><span class="sxs-lookup"><span data-stu-id="03d30-113">See also</span></span>

- [<span data-ttu-id="03d30-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="03d30-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="03d30-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="03d30-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

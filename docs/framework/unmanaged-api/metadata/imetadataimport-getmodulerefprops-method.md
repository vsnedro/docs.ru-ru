---
title: Метод IMetaDataImport::GetModuleRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
ms.openlocfilehash: 606a3f2cfba05b014960842c5db77149f449193d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733130"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="eb214-102">Метод IMetaDataImport::GetModuleRefProps</span><span class="sxs-lookup"><span data-stu-id="eb214-102">IMetaDataImport::GetModuleRefProps Method</span></span>

<span data-ttu-id="eb214-103">Возвращает имя модуля, на который ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="eb214-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb214-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb214-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb214-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb214-105">Parameters</span></span>  

 `mur`  
 <span data-ttu-id="eb214-106">окне Токен метаданных ModuleRef, который ссылается на модуль для получения сведений о метаданных.</span><span class="sxs-lookup"><span data-stu-id="eb214-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="eb214-107">заполняет Буфер для хранения имени модуля.</span><span class="sxs-lookup"><span data-stu-id="eb214-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="eb214-108">окне Запрошенный размер `szName` в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="eb214-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="eb214-109">заполняет Возвращаемый размер `szName` в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="eb214-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb214-110">Требования</span><span class="sxs-lookup"><span data-stu-id="eb214-110">Requirements</span></span>  

 <span data-ttu-id="eb214-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb214-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb214-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="eb214-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb214-113">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eb214-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb214-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb214-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb214-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eb214-115">See also</span></span>

- [<span data-ttu-id="eb214-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="eb214-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="eb214-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="eb214-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

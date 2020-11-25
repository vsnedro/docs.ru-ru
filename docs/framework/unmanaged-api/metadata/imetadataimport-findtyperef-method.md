---
title: Метод IMetaDataImport::FindTypeRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
ms.openlocfilehash: 3c96a9b601824cc4001568c4656f968fad70cf39
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711290"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="c7577-102">Метод IMetaDataImport::FindTypeRef</span><span class="sxs-lookup"><span data-stu-id="c7577-102">IMetaDataImport::FindTypeRef Method</span></span>

<span data-ttu-id="c7577-103">Возвращает указатель на маркер TypeRef для <xref:System.Type> ссылки, наданной в указанной области и имеющей указанное имя.</span><span class="sxs-lookup"><span data-stu-id="c7577-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7577-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7577-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7577-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7577-105">Parameters</span></span>  

 `tkResolutionScope`  
 <span data-ttu-id="c7577-106">окне Токен ModuleRef, AssemblyRef или TypeRef, указывающий модуль, сборку или тип соответственно, в котором определена ссылка на тип.</span><span class="sxs-lookup"><span data-stu-id="c7577-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="c7577-107">окне Имя искомой ссылки на тип.</span><span class="sxs-lookup"><span data-stu-id="c7577-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="c7577-108">заполняет Указатель на соответствующий токен TypeRef.</span><span class="sxs-lookup"><span data-stu-id="c7577-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7577-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c7577-109">Requirements</span></span>  

 <span data-ttu-id="c7577-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7577-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7577-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c7577-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7577-112">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7577-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7577-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7577-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7577-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c7577-114">See also</span></span>

- [<span data-ttu-id="c7577-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c7577-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c7577-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c7577-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

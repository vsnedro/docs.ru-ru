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
ms.openlocfilehash: 545fe1e1d9e641d2225ad92c11453558dc4b97d1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491502"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="4c525-102">Метод IMetaDataImport::FindTypeRef</span><span class="sxs-lookup"><span data-stu-id="4c525-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="4c525-103">Возвращает указатель на маркер TypeRef для <xref:System.Type> ссылки, наданной в указанной области и имеющей указанное имя.</span><span class="sxs-lookup"><span data-stu-id="4c525-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c525-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c525-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c525-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c525-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="4c525-106">окне Токен ModuleRef, AssemblyRef или TypeRef, указывающий модуль, сборку или тип соответственно, в котором определена ссылка на тип.</span><span class="sxs-lookup"><span data-stu-id="4c525-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="4c525-107">окне Имя искомой ссылки на тип.</span><span class="sxs-lookup"><span data-stu-id="4c525-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="4c525-108">заполняет Указатель на соответствующий токен TypeRef.</span><span class="sxs-lookup"><span data-stu-id="4c525-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c525-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4c525-109">Requirements</span></span>  
 <span data-ttu-id="4c525-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c525-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c525-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="4c525-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4c525-112">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4c525-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4c525-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c525-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c525-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4c525-114">See also</span></span>

- [<span data-ttu-id="4c525-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4c525-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4c525-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4c525-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

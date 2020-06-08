---
title: Метод IMetaDataImport::GetTypeRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
ms.openlocfilehash: 273922e00c3e5319d5a03652cc77b69f4479ea67
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503527"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="b5e5d-102">Метод IMetaDataImport::GetTypeRefProps</span><span class="sxs-lookup"><span data-stu-id="b5e5d-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="b5e5d-103">Возвращает метаданные, связанные с <xref:System.Type> объектом, на который ссылается указанный токен TypeRef.</span><span class="sxs-lookup"><span data-stu-id="b5e5d-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5e5d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5e5d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5e5d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5e5d-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="b5e5d-106">окне Токен TypeRef, представляющий тип, для которого возвращаются метаданные.</span><span class="sxs-lookup"><span data-stu-id="b5e5d-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="b5e5d-107">заполняет Указатель на область, в которой создана ссылка.</span><span class="sxs-lookup"><span data-stu-id="b5e5d-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="b5e5d-108">Это значение является токеном AssemblyRef или ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="b5e5d-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="b5e5d-109">заполняет Буфер, содержащий имя типа.</span><span class="sxs-lookup"><span data-stu-id="b5e5d-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b5e5d-110">окне Запрошенный размер в расширенных символах `szName` .</span><span class="sxs-lookup"><span data-stu-id="b5e5d-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="b5e5d-111">заполняет Возвращаемый размер в расширенных символах `szName` .</span><span class="sxs-lookup"><span data-stu-id="b5e5d-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5e5d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b5e5d-112">Requirements</span></span>  
 <span data-ttu-id="b5e5d-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5e5d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5e5d-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b5e5d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5e5d-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b5e5d-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5e5d-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5e5d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e5d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b5e5d-117">See also</span></span>

- [<span data-ttu-id="b5e5d-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b5e5d-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="b5e5d-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b5e5d-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

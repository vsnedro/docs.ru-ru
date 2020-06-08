---
title: Метод IMetaDataImport::GetNestedClassProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
ms.openlocfilehash: 82cf5e14520f0e677c2d274cf013d8a0020e8fa2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503540"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="543b0-102">Метод IMetaDataImport::GetNestedClassProps</span><span class="sxs-lookup"><span data-stu-id="543b0-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="543b0-103">Возвращает маркер TypeDef для родителя <xref:System.Type> указанного вложенного типа.</span><span class="sxs-lookup"><span data-stu-id="543b0-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="543b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="543b0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="543b0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="543b0-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="543b0-106">окне Токен TypeDef, представляющий объект, <xref:System.Type> для которого возвращается маркер родительского класса.</span><span class="sxs-lookup"><span data-stu-id="543b0-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="543b0-107">заполняет Указатель на маркер TypeDef для <xref:System.Type> , `tdNestedClass` вложенный в.</span><span class="sxs-lookup"><span data-stu-id="543b0-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="543b0-108">Требования</span><span class="sxs-lookup"><span data-stu-id="543b0-108">Requirements</span></span>  
 <span data-ttu-id="543b0-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="543b0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="543b0-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="543b0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="543b0-111">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="543b0-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="543b0-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="543b0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="543b0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="543b0-113">See also</span></span>

- [<span data-ttu-id="543b0-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="543b0-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="543b0-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="543b0-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

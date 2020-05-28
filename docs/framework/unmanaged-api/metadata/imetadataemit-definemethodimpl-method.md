---
title: Метод IMetaDataEmit::DefineMethodImpl
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
ms.openlocfilehash: 5ed5afbbf49b6680d00e78b6af3d45c6f0a7229d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004495"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="02917-102">Метод IMetaDataEmit::DefineMethodImpl</span><span class="sxs-lookup"><span data-stu-id="02917-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="02917-103">Создает определение для реализации метода, унаследованного от интерфейса, и возвращает маркер для этого определения реализации метода.</span><span class="sxs-lookup"><span data-stu-id="02917-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02917-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02917-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02917-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="02917-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="02917-106">окне `mdTypedef`Токен реализующего класса.</span><span class="sxs-lookup"><span data-stu-id="02917-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="02917-107">окне `mdMethodDef`Токен или `mdMemberRef` тела кода.</span><span class="sxs-lookup"><span data-stu-id="02917-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="02917-108">окне `mdMethodDef`Токен или `mdMemberRef` реализуемого метода интерфейса.</span><span class="sxs-lookup"><span data-stu-id="02917-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02917-109">Требования</span><span class="sxs-lookup"><span data-stu-id="02917-109">Requirements</span></span>  
 <span data-ttu-id="02917-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02917-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02917-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="02917-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02917-112">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="02917-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02917-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02917-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02917-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="02917-114">See also</span></span>

- [<span data-ttu-id="02917-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="02917-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="02917-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="02917-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

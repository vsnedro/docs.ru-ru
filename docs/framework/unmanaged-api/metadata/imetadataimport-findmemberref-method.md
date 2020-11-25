---
title: Метод IMetaDataImport::FindMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: 0ba25c981cc389baf06ecca0db543d48ac60317b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711407"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="bf40e-102">Метод IMetaDataImport::FindMemberRef</span><span class="sxs-lookup"><span data-stu-id="bf40e-102">IMetaDataImport::FindMemberRef Method</span></span>

<span data-ttu-id="bf40e-103">Возвращает указатель на токен MemberRef для ссылки на элемент, заключенный в заданный объект с <xref:System.Type> указанным именем и сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="bf40e-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf40e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf40e-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf40e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf40e-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="bf40e-106">окне Токен TypeRef для класса или интерфейса, который заключает в себя ссылку на элемент для поиска.</span><span class="sxs-lookup"><span data-stu-id="bf40e-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="bf40e-107">Если это значение равно `mdTokenNil` , поиск выполняется для глобальной переменной или ссылки на глобальную функцию.</span><span class="sxs-lookup"><span data-stu-id="bf40e-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="bf40e-108">окне Имя искомой ссылки на член.</span><span class="sxs-lookup"><span data-stu-id="bf40e-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="bf40e-109">окне Указатель на сигнатуру двоичных метаданных ссылки на элемент.</span><span class="sxs-lookup"><span data-stu-id="bf40e-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="bf40e-110">окне Размер в байтах для `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="bf40e-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="bf40e-111">заполняет Указатель на соответствующий токен MemberRef.</span><span class="sxs-lookup"><span data-stu-id="bf40e-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf40e-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="bf40e-112">Remarks</span></span>  

 <span data-ttu-id="bf40e-113">Элемент указывается с помощью включающего класса или интерфейса ( `td` ), его имени ( `szName` ) и (при необходимости) его сигнатуры ( `pvSigBlob` ).</span><span class="sxs-lookup"><span data-stu-id="bf40e-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="bf40e-114">Подпись, передаваемая в `FindMemberRef` , должна быть создана в текущей области, так как сигнатуры привязаны к определенной области.</span><span class="sxs-lookup"><span data-stu-id="bf40e-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="bf40e-115">Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения.</span><span class="sxs-lookup"><span data-stu-id="bf40e-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="bf40e-116">Токен является индексом локальной таблицы TypeDef.</span><span class="sxs-lookup"><span data-stu-id="bf40e-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="bf40e-117">Нельзя построить подпись времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для `FindMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="bf40e-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="bf40e-118">`FindMemberRef` находит только ссылки на элементы, которые были определены непосредственно в классе или интерфейсе; Он не находит унаследованные ссылки на члены.</span><span class="sxs-lookup"><span data-stu-id="bf40e-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf40e-119">Требования</span><span class="sxs-lookup"><span data-stu-id="bf40e-119">Requirements</span></span>  

 <span data-ttu-id="bf40e-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf40e-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf40e-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="bf40e-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf40e-122">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf40e-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf40e-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf40e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf40e-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bf40e-124">See also</span></span>

- [<span data-ttu-id="bf40e-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bf40e-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="bf40e-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bf40e-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

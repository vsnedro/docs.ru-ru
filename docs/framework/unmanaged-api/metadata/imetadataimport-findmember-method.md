---
title: Метод IMetaDataImport::FindMember
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: fce4f3875fbdb110134d6b7f684eff40821f6bdd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503683"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="be2ef-102">Метод IMetaDataImport::FindMember</span><span class="sxs-lookup"><span data-stu-id="be2ef-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="be2ef-103">Возвращает указатель на токен Мембердеф для поля или метода, заключенного в заданный объект с <xref:System.Type> указанным именем и сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="be2ef-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be2ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be2ef-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be2ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="be2ef-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="be2ef-106">окне Токен TypeDef для класса или интерфейса, который заключает элемент для поиска.</span><span class="sxs-lookup"><span data-stu-id="be2ef-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="be2ef-107">Если это значение равно `mdTokenNil` , поиск выполняется для глобальной переменной или глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="be2ef-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="be2ef-108">окне Имя искомого элемента.</span><span class="sxs-lookup"><span data-stu-id="be2ef-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="be2ef-109">окне Указатель на сигнатуру двоичных метаданных элемента.</span><span class="sxs-lookup"><span data-stu-id="be2ef-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="be2ef-110">окне Размер в байтах для `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="be2ef-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="be2ef-111">заполняет Указатель на соответствующий токен Мембердеф.</span><span class="sxs-lookup"><span data-stu-id="be2ef-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be2ef-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="be2ef-112">Remarks</span></span>  
 <span data-ttu-id="be2ef-113">Элемент указывается с помощью включающего класса или интерфейса ( `td` ), его имени ( `szName` ) и (при необходимости) его сигнатуры ( `pvSigBlob` ).</span><span class="sxs-lookup"><span data-stu-id="be2ef-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="be2ef-114">В классе или интерфейсе может быть несколько членов с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="be2ef-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="be2ef-115">В этом случае передайте сигнатуру члена, чтобы найти уникальное совпадение.</span><span class="sxs-lookup"><span data-stu-id="be2ef-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="be2ef-116">Подпись, передаваемая в `FindMember` , должна быть создана в текущей области, так как сигнатуры привязаны к определенной области.</span><span class="sxs-lookup"><span data-stu-id="be2ef-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="be2ef-117">Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения.</span><span class="sxs-lookup"><span data-stu-id="be2ef-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="be2ef-118">Токен является индексом локальной таблицы TypeDef.</span><span class="sxs-lookup"><span data-stu-id="be2ef-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="be2ef-119">Нельзя построить сигнатуру времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для входных данных `FindMember` .</span><span class="sxs-lookup"><span data-stu-id="be2ef-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="be2ef-120">`FindMember`находит только элементы, которые были определены непосредственно в классе или интерфейсе; Он не находит наследуемых членов.</span><span class="sxs-lookup"><span data-stu-id="be2ef-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be2ef-121">`FindMember`— Это вспомогательный метод.</span><span class="sxs-lookup"><span data-stu-id="be2ef-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="be2ef-122">Он вызывает метод [IMetaDataImport:: FindMethod](imetadataimport-findmethod-method.md); Если этот вызов не находит совпадения, `FindMember` то вызывает метод [IMetaDataImport:: финдфиелд](imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="be2ef-122">It calls [IMetaDataImport::FindMethod](imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be2ef-123">Требования</span><span class="sxs-lookup"><span data-stu-id="be2ef-123">Requirements</span></span>  
 <span data-ttu-id="be2ef-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be2ef-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be2ef-125">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="be2ef-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be2ef-126">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="be2ef-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="be2ef-127">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be2ef-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be2ef-128">См. также</span><span class="sxs-lookup"><span data-stu-id="be2ef-128">See also</span></span>

- [<span data-ttu-id="be2ef-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="be2ef-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="be2ef-130">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="be2ef-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

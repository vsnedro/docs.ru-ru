---
title: Метод IMetaDataImport::FindField
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
ms.openlocfilehash: 9b42f0f7c8e2878ee3ec140344f51517a24247c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729867"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="75ac2-102">Метод IMetaDataImport::FindField</span><span class="sxs-lookup"><span data-stu-id="75ac2-102">IMetaDataImport::FindField Method</span></span>

<span data-ttu-id="75ac2-103">Возвращает указатель на токен FieldDef для поля, заключенного в заданный объект с <xref:System.Type> указанным именем и сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="75ac2-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75ac2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75ac2-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75ac2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="75ac2-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="75ac2-106">окне Маркер TypeDef для класса или интерфейса, который заключает поле для поиска.</span><span class="sxs-lookup"><span data-stu-id="75ac2-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="75ac2-107">Если это значение равно `mdTokenNil` , поиск выполняется для глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="75ac2-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="75ac2-108">окне Имя искомого поля.</span><span class="sxs-lookup"><span data-stu-id="75ac2-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="75ac2-109">окне Указатель на сигнатуру двоичных метаданных поля.</span><span class="sxs-lookup"><span data-stu-id="75ac2-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="75ac2-110">окне Размер в байтах для `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="75ac2-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="75ac2-111">заполняет Указатель на соответствующий токен FieldDef.</span><span class="sxs-lookup"><span data-stu-id="75ac2-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75ac2-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="75ac2-112">Remarks</span></span>  

 <span data-ttu-id="75ac2-113">Поле указывается с помощью включающего его класса или интерфейса ( `td` ), имени ( `szName` ) и (при необходимости) его сигнатуры ( `pvSigBlob` ).</span><span class="sxs-lookup"><span data-stu-id="75ac2-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="75ac2-114">Подпись, передаваемая в `FindField` , должна быть создана в текущей области, так как сигнатуры привязаны к определенной области.</span><span class="sxs-lookup"><span data-stu-id="75ac2-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="75ac2-115">Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения.</span><span class="sxs-lookup"><span data-stu-id="75ac2-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="75ac2-116">(Токен является индексом локальной таблицы TypeDef).</span><span class="sxs-lookup"><span data-stu-id="75ac2-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="75ac2-117">Нельзя построить подпись времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для `FindField` .</span><span class="sxs-lookup"><span data-stu-id="75ac2-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="75ac2-118">`FindField` находит только поля, которые были определены непосредственно в классе или интерфейсе; наследуемые поля не находятся.</span><span class="sxs-lookup"><span data-stu-id="75ac2-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75ac2-119">Требования</span><span class="sxs-lookup"><span data-stu-id="75ac2-119">Requirements</span></span>  

 <span data-ttu-id="75ac2-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75ac2-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75ac2-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="75ac2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75ac2-122">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="75ac2-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75ac2-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75ac2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ac2-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="75ac2-124">See also</span></span>

- [<span data-ttu-id="75ac2-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="75ac2-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="75ac2-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="75ac2-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

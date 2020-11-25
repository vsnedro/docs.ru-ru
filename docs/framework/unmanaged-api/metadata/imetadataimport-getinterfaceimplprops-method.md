---
title: Метод IMetaDataImport::GetInterfaceImplProps
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
ms.openlocfilehash: e81816ce2194c2c1862cb997ad2c6e5baf301231
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704010"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="7d2ac-102">Метод IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="7d2ac-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>

<span data-ttu-id="7d2ac-103">Возвращает указатель на маркеры метаданных для <xref:System.Type> , который реализует указанный метод, и для интерфейса, объявляющего этот метод.</span><span class="sxs-lookup"><span data-stu-id="7d2ac-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="7d2ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d2ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d2ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d2ac-105">Parameters</span></span>  

 `iiImpl`  
 <span data-ttu-id="7d2ac-106">окне Токен метаданных, представляющий метод, для которого необходимо вернуть маркеры класса и интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7d2ac-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="7d2ac-107">заполняет Маркер метаданных, представляющий класс, реализующий метод.</span><span class="sxs-lookup"><span data-stu-id="7d2ac-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="7d2ac-108">заполняет Токен метаданных, представляющий интерфейс, определяющий реализованный метод.</span><span class="sxs-lookup"><span data-stu-id="7d2ac-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="7d2ac-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7d2ac-109">Remarks</span></span>

 <span data-ttu-id="7d2ac-110">Получить значение для можно `iImpl` путем вызова метода [енуминтерфацеимплс](imetadataimport-enuminterfaceimpls-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7d2ac-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="7d2ac-111">Например, предположим, что класс имеет `mdTypeDef` значение маркера 0x02000007 и реализует три интерфейса, типы которых имеют токены:</span><span class="sxs-lookup"><span data-stu-id="7d2ac-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="7d2ac-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="7d2ac-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="7d2ac-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="7d2ac-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="7d2ac-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="7d2ac-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="7d2ac-115">По сути, эта информация хранится в таблице реализации интерфейса следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7d2ac-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="7d2ac-116">Номер строки</span><span class="sxs-lookup"><span data-stu-id="7d2ac-116">Row number</span></span> | <span data-ttu-id="7d2ac-117">Токен класса</span><span class="sxs-lookup"><span data-stu-id="7d2ac-117">Class token</span></span> | <span data-ttu-id="7d2ac-118">Токен интерфейса</span><span class="sxs-lookup"><span data-stu-id="7d2ac-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="7d2ac-119">4</span><span class="sxs-lookup"><span data-stu-id="7d2ac-119">4</span></span>          |             |                 |
| <span data-ttu-id="7d2ac-120">5</span><span class="sxs-lookup"><span data-stu-id="7d2ac-120">5</span></span>          | <span data-ttu-id="7d2ac-121">02000007</span><span class="sxs-lookup"><span data-stu-id="7d2ac-121">02000007</span></span>    | <span data-ttu-id="7d2ac-122">02000003</span><span class="sxs-lookup"><span data-stu-id="7d2ac-122">02000003</span></span>        |
| <span data-ttu-id="7d2ac-123">6</span><span class="sxs-lookup"><span data-stu-id="7d2ac-123">6</span></span>          | <span data-ttu-id="7d2ac-124">02000007</span><span class="sxs-lookup"><span data-stu-id="7d2ac-124">02000007</span></span>    | <span data-ttu-id="7d2ac-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="7d2ac-125">0100000A</span></span>        |
| <span data-ttu-id="7d2ac-126">7</span><span class="sxs-lookup"><span data-stu-id="7d2ac-126">7</span></span>          |             |                 |
| <span data-ttu-id="7d2ac-127">8</span><span class="sxs-lookup"><span data-stu-id="7d2ac-127">8</span></span>          | <span data-ttu-id="7d2ac-128">02000007</span><span class="sxs-lookup"><span data-stu-id="7d2ac-128">02000007</span></span>    | <span data-ttu-id="7d2ac-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="7d2ac-129">0200001C</span></span>        |

<span data-ttu-id="7d2ac-130">Помните, что маркер является 4-байтовым значением:</span><span class="sxs-lookup"><span data-stu-id="7d2ac-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="7d2ac-131">3 младших байта содержат номер строки или RID.</span><span class="sxs-lookup"><span data-stu-id="7d2ac-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="7d2ac-132">Верхний байт содержит тип токена — 0x09 для `mdtInterfaceImpl` .</span><span class="sxs-lookup"><span data-stu-id="7d2ac-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="7d2ac-133">`GetInterfaceImplProps` Возвращает информацию, удерживаемую в строке, токен которой вы задаете в `iImpl` аргументе.</span><span class="sxs-lookup"><span data-stu-id="7d2ac-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="7d2ac-134">Требования</span><span class="sxs-lookup"><span data-stu-id="7d2ac-134">Requirements</span></span>  

 <span data-ttu-id="7d2ac-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d2ac-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d2ac-136">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="7d2ac-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d2ac-137">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d2ac-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d2ac-138">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d2ac-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d2ac-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7d2ac-139">See also</span></span>

- [<span data-ttu-id="7d2ac-140">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7d2ac-140">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="7d2ac-141">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="7d2ac-141">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

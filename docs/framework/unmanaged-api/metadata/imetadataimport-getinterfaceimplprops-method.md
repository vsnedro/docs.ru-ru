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
ms.openlocfilehash: 1c9d9647084aa729817eeeb17ee3f5cd320c0d29
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491253"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="30148-102">Метод IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="30148-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="30148-103">Возвращает указатель на маркеры метаданных для <xref:System.Type> , который реализует указанный метод, и для интерфейса, объявляющего этот метод.</span><span class="sxs-lookup"><span data-stu-id="30148-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="30148-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30148-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30148-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30148-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="30148-106">окне Токен метаданных, представляющий метод, для которого необходимо вернуть маркеры класса и интерфейса.</span><span class="sxs-lookup"><span data-stu-id="30148-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="30148-107">заполняет Маркер метаданных, представляющий класс, реализующий метод.</span><span class="sxs-lookup"><span data-stu-id="30148-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="30148-108">заполняет Токен метаданных, представляющий интерфейс, определяющий реализованный метод.</span><span class="sxs-lookup"><span data-stu-id="30148-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="30148-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="30148-109">Remarks</span></span>

 <span data-ttu-id="30148-110">Получить значение для можно `iImpl` путем вызова метода [енуминтерфацеимплс](imetadataimport-enuminterfaceimpls-method.md) .</span><span class="sxs-lookup"><span data-stu-id="30148-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="30148-111">Например, предположим, что класс имеет `mdTypeDef` значение маркера 0x02000007 и реализует три интерфейса, типы которых имеют токены:</span><span class="sxs-lookup"><span data-stu-id="30148-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="30148-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="30148-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="30148-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="30148-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="30148-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="30148-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="30148-115">По сути, эта информация хранится в таблице реализации интерфейса следующим образом:</span><span class="sxs-lookup"><span data-stu-id="30148-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="30148-116">Номер строки</span><span class="sxs-lookup"><span data-stu-id="30148-116">Row number</span></span> | <span data-ttu-id="30148-117">Токен класса</span><span class="sxs-lookup"><span data-stu-id="30148-117">Class token</span></span> | <span data-ttu-id="30148-118">Токен интерфейса</span><span class="sxs-lookup"><span data-stu-id="30148-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="30148-119">4</span><span class="sxs-lookup"><span data-stu-id="30148-119">4</span></span>          |             |                 |
| <span data-ttu-id="30148-120">5</span><span class="sxs-lookup"><span data-stu-id="30148-120">5</span></span>          | <span data-ttu-id="30148-121">02000007</span><span class="sxs-lookup"><span data-stu-id="30148-121">02000007</span></span>    | <span data-ttu-id="30148-122">02000003</span><span class="sxs-lookup"><span data-stu-id="30148-122">02000003</span></span>        |
| <span data-ttu-id="30148-123">6</span><span class="sxs-lookup"><span data-stu-id="30148-123">6</span></span>          | <span data-ttu-id="30148-124">02000007</span><span class="sxs-lookup"><span data-stu-id="30148-124">02000007</span></span>    | <span data-ttu-id="30148-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="30148-125">0100000A</span></span>        |
| <span data-ttu-id="30148-126">7</span><span class="sxs-lookup"><span data-stu-id="30148-126">7</span></span>          |             |                 |
| <span data-ttu-id="30148-127">8</span><span class="sxs-lookup"><span data-stu-id="30148-127">8</span></span>          | <span data-ttu-id="30148-128">02000007</span><span class="sxs-lookup"><span data-stu-id="30148-128">02000007</span></span>    | <span data-ttu-id="30148-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="30148-129">0200001C</span></span>        |

<span data-ttu-id="30148-130">Помните, что маркер является 4-байтовым значением:</span><span class="sxs-lookup"><span data-stu-id="30148-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="30148-131">3 младших байта содержат номер строки или RID.</span><span class="sxs-lookup"><span data-stu-id="30148-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="30148-132">Верхний байт содержит тип токена — 0x09 для `mdtInterfaceImpl` .</span><span class="sxs-lookup"><span data-stu-id="30148-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="30148-133">`GetInterfaceImplProps`Возвращает информацию, удерживаемую в строке, токен которой вы задаете в `iImpl` аргументе.</span><span class="sxs-lookup"><span data-stu-id="30148-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="30148-134">Требования</span><span class="sxs-lookup"><span data-stu-id="30148-134">Requirements</span></span>  
 <span data-ttu-id="30148-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30148-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30148-136">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="30148-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30148-137">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="30148-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30148-138">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30148-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30148-139">См. также</span><span class="sxs-lookup"><span data-stu-id="30148-139">See also</span></span>

- [<span data-ttu-id="30148-140">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="30148-140">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="30148-141">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="30148-141">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

---
title: Метод IMetaDataImport::GetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
ms.openlocfilehash: c2abf2813c6e1a9db4264bded32d9cb9c58a2bcb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491060"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="939e4-102">Метод IMetaDataImport::GetParamProps</span><span class="sxs-lookup"><span data-stu-id="939e4-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="939e4-103">Возвращает значения метаданных для параметра, на который ссылается указанный токен ParamDef.</span><span class="sxs-lookup"><span data-stu-id="939e4-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="939e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="939e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="939e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="939e4-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="939e4-106">окне Токен Парамдеф, представляющий параметр, для которого возвращаются метаданные.</span><span class="sxs-lookup"><span data-stu-id="939e4-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="939e4-107">заполняет Указатель на токен MethodDef, представляющий метод, который принимает параметр.</span><span class="sxs-lookup"><span data-stu-id="939e4-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="939e4-108">заполняет Порядковый номер параметра в списке аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="939e4-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="939e4-109">заполняет Буфер для хранения имени параметра.</span><span class="sxs-lookup"><span data-stu-id="939e4-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="939e4-110">окне Запрошенный размер в расширенных символах `szName` .</span><span class="sxs-lookup"><span data-stu-id="939e4-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="939e4-111">заполняет Возвращаемый размер в расширенных символах `szName` .</span><span class="sxs-lookup"><span data-stu-id="939e4-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="939e4-112">заполняет Указатель на любые флаги атрибутов, связанные с параметром.</span><span class="sxs-lookup"><span data-stu-id="939e4-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="939e4-113">Это битовая маска `CorParamAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="939e4-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="939e4-114">заполняет Указатель на флаг, указывающий, что параметр является <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="939e4-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="939e4-115">заполняет Указатель на константную строку, возвращенную параметром.</span><span class="sxs-lookup"><span data-stu-id="939e4-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="939e4-116">заполняет Размер `ppValue` в расширенных символах или нуль, если не содержит `ppValue` строку.</span><span class="sxs-lookup"><span data-stu-id="939e4-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="939e4-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="939e4-117">Remarks</span></span>

<span data-ttu-id="939e4-118">Значения последовательности в `pulSequence` аргументе начинаются с 1 для параметров.</span><span class="sxs-lookup"><span data-stu-id="939e4-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="939e4-119">Возвращаемое значение имеет порядковый номер 0.</span><span class="sxs-lookup"><span data-stu-id="939e4-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="939e4-120">Требования</span><span class="sxs-lookup"><span data-stu-id="939e4-120">Requirements</span></span>  
 <span data-ttu-id="939e4-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="939e4-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="939e4-122">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="939e4-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="939e4-123">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="939e4-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="939e4-124">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="939e4-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="939e4-125">См. также</span><span class="sxs-lookup"><span data-stu-id="939e4-125">See also</span></span>

- [<span data-ttu-id="939e4-126">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="939e4-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="939e4-127">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="939e4-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

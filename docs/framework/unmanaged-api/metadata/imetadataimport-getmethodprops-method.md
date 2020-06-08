---
title: Метод IMetaDataImport::GetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 3c7c3525f2f8753241c9a206e4cf5e552bf06efe
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503631"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="c6150-102">Метод IMetaDataImport::GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="c6150-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="c6150-103">Возвращает метаданные, связанные с методом, на который ссылается указанный токен MethodDef.</span><span class="sxs-lookup"><span data-stu-id="c6150-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6150-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6150-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6150-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6150-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="c6150-106">окне Токен MethodDef, представляющий метод, для которого возвращаются метаданные.</span><span class="sxs-lookup"><span data-stu-id="c6150-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="c6150-107">заполняет Указатель на маркер TypeDef, представляющий тип, реализующий метод.</span><span class="sxs-lookup"><span data-stu-id="c6150-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="c6150-108">заполняет Указатель на буфер с именем метода.</span><span class="sxs-lookup"><span data-stu-id="c6150-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="c6150-109">окне Запрошенный размер `szMethod` .</span><span class="sxs-lookup"><span data-stu-id="c6150-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="c6150-110">заполняет Указатель на размер в расширенных символах `szMethod` , или, в случае усечения, фактическое число расширенных символов в имени метода.</span><span class="sxs-lookup"><span data-stu-id="c6150-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="c6150-111">заполняет Указатель на любые флаги, связанные с методом.</span><span class="sxs-lookup"><span data-stu-id="c6150-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="c6150-112">заполняет Указатель на сигнатуру двоичных метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="c6150-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="c6150-113">заполняет Указатель на размер в байтах для `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="c6150-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="c6150-114">заполняет Указатель на относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="c6150-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="c6150-115">заполняет Указатель на любые флаги реализации метода.</span><span class="sxs-lookup"><span data-stu-id="c6150-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6150-116">Требования</span><span class="sxs-lookup"><span data-stu-id="c6150-116">Requirements</span></span>  
 <span data-ttu-id="c6150-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6150-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6150-118">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c6150-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6150-119">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c6150-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6150-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6150-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6150-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c6150-121">See also</span></span>

- [<span data-ttu-id="c6150-122">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c6150-122">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c6150-123">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c6150-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

---
title: Метод IMetaDataImport2::GetMethodSpecProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
ms.openlocfilehash: 079d9245526ff7914d1cbd6a91f0f2d96a690af5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490449"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="907c3-102">Метод IMetaDataImport2::GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="907c3-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="907c3-103">Возвращает сигнатуру метаданных метода, на который ссылается указанный токен MethodSpec.</span><span class="sxs-lookup"><span data-stu-id="907c3-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="907c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="907c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,
   [out] ULONG            *pcbSigBlob  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="907c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="907c3-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="907c3-106">окне Токен MethodSpec, представляющий создание экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="907c3-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="907c3-107">заполняет Указатель на токен MethodDef или Месодреф, представляющий определение метода.</span><span class="sxs-lookup"><span data-stu-id="907c3-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="907c3-108">заполняет Указатель на сигнатуру двоичных метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="907c3-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="907c3-109">заполняет Размер (в байтах) `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="907c3-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="907c3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="907c3-110">Requirements</span></span>  
 <span data-ttu-id="907c3-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="907c3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="907c3-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="907c3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="907c3-113">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="907c3-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="907c3-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="907c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="907c3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="907c3-115">See also</span></span>

- [<span data-ttu-id="907c3-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="907c3-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="907c3-117">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="907c3-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)

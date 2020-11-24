---
title: Метод IMetaDataImport::GetFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
ms.openlocfilehash: 35f73135dbeea1c79d15e0a9e9367c5d533487ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676869"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="48664-102">Метод IMetaDataImport::GetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="48664-102">IMetaDataImport::GetFieldMarshal Method</span></span>

<span data-ttu-id="48664-103">Возвращает указатель на собственный неуправляемый тип поля, представленного заданным токеном метаданных поля.</span><span class="sxs-lookup"><span data-stu-id="48664-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48664-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48664-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48664-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="48664-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="48664-106">окне Токен метаданных, представляющий поле, для которого необходимо получить сведения о маршалинге взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="48664-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="48664-107">заполняет Указатель на сигнатуру метаданных собственного типа поля.</span><span class="sxs-lookup"><span data-stu-id="48664-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="48664-108">заполняет Размер в байтах для `ppvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="48664-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48664-109">Требования</span><span class="sxs-lookup"><span data-stu-id="48664-109">Requirements</span></span>  

 <span data-ttu-id="48664-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48664-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48664-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="48664-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48664-112">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48664-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48664-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48664-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48664-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48664-114">See also</span></span>

- [<span data-ttu-id="48664-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="48664-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="48664-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="48664-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

---
title: Метод IMetaDataConverter::GetMetaDataFromTypeInfo
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
ms.openlocfilehash: 1f45310bc65bc8614033182a81db451b79bcf97f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714722"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="5b341-102">Метод IMetaDataConverter::GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="5b341-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>

<span data-ttu-id="5b341-103">Возвращает указатель на экземпляр [IMetaDataImport](imetadataimport-interface.md) , представляющий сигнатуру метаданных библиотеки типов, на которую ссылается указанный `ITypeInfo` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="5b341-103">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b341-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b341-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b341-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b341-105">Parameters</span></span>  

 `pITI`  
 <span data-ttu-id="5b341-106">окне Указатель на `ITypeInfo` объект, который ссылается на библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="5b341-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="5b341-107">заполняет Указатель на расположение, которое получает адрес `IMetaDataImport` экземпляра, представляющий подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="5b341-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b341-108">Требования</span><span class="sxs-lookup"><span data-stu-id="5b341-108">Requirements</span></span>  

 <span data-ttu-id="5b341-109">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b341-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b341-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="5b341-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b341-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b341-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b341-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b341-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b341-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5b341-113">See also</span></span>

- [<span data-ttu-id="5b341-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5b341-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5b341-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5b341-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)

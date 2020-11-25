---
title: Метод IMetaDataConverter::GetTypeLibFromMetaData
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: eed8661f8885ca16492ab336a599b5290057843a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714605"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="61ec6-102">Метод IMetaDataConverter::GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="61ec6-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>

<span data-ttu-id="61ec6-103">Возвращает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов с указанными именами библиотеки и модуля.</span><span class="sxs-lookup"><span data-stu-id="61ec6-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61ec6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61ec6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61ec6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="61ec6-105">Parameters</span></span>  

 `strModule`  
 <span data-ttu-id="61ec6-106">окне Имя модуля библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="61ec6-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="61ec6-107">окне Имя библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="61ec6-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="61ec6-108">заполняет Указатель на расположение, которое получает адрес `ITypeLib` экземпляра, представляющий библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="61ec6-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61ec6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="61ec6-109">Requirements</span></span>  

 <span data-ttu-id="61ec6-110">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61ec6-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61ec6-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="61ec6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61ec6-112">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61ec6-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61ec6-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61ec6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ec6-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="61ec6-114">See also</span></span>

- [<span data-ttu-id="61ec6-115">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="61ec6-115">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)

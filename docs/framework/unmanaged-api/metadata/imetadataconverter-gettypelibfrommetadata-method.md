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
ms.openlocfilehash: 79bd8901641ee587e94861c0aec85b812591ea48
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008421"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="3e40a-102">Метод IMetaDataConverter::GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="3e40a-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="3e40a-103">Возвращает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов с указанными именами библиотеки и модуля.</span><span class="sxs-lookup"><span data-stu-id="3e40a-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e40a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e40a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e40a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e40a-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="3e40a-106">окне Имя модуля библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3e40a-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="3e40a-107">окне Имя библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3e40a-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="3e40a-108">заполняет Указатель на расположение, которое получает адрес `ITypeLib` экземпляра, представляющий библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="3e40a-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e40a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3e40a-109">Requirements</span></span>  
 <span data-ttu-id="3e40a-110">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e40a-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e40a-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3e40a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e40a-112">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3e40a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e40a-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e40a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e40a-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3e40a-114">See also</span></span>

- [<span data-ttu-id="3e40a-115">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="3e40a-115">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)

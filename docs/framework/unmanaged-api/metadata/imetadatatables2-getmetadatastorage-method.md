---
title: Метод IMetaDataTables2::GetMetaDataStorage
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
ms.openlocfilehash: 775b3919d1468f26fc3c374dd8ca143aa17853ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708742"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="c4a11-102">Метод IMetaDataTables2::GetMetaDataStorage</span><span class="sxs-lookup"><span data-stu-id="c4a11-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>

<span data-ttu-id="c4a11-103">Возвращает размер и содержимое метаданных, хранящихся в указанном разделе.</span><span class="sxs-lookup"><span data-stu-id="c4a11-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4a11-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4a11-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4a11-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4a11-105">Parameters</span></span>  

 `ppvMd`  
 <span data-ttu-id="c4a11-106">[вход, выход] Указатель на раздел метаданных.</span><span class="sxs-lookup"><span data-stu-id="c4a11-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="c4a11-107">заполняет Размер потока метаданных.</span><span class="sxs-lookup"><span data-stu-id="c4a11-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4a11-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c4a11-108">Requirements</span></span>  

 <span data-ttu-id="c4a11-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4a11-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4a11-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c4a11-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4a11-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c4a11-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4a11-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4a11-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4a11-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c4a11-113">See also</span></span>

- [<span data-ttu-id="c4a11-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="c4a11-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="c4a11-115">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="c4a11-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)

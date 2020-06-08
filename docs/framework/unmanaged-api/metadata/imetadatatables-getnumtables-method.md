---
title: Метод IMetaDataTables::GetNumTables
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNumTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type:
- apiref
ms.openlocfilehash: df02def0c14beb4e9ffd1b9260002767586a59b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490202"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="e4f23-102">Метод IMetaDataTables::GetNumTables</span><span class="sxs-lookup"><span data-stu-id="e4f23-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="e4f23-103">Возвращает количество таблиц в области текущего `IMetaDataTables` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e4f23-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4f23-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4f23-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4f23-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4f23-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="e4f23-106">заполняет Указатель на число таблиц в области текущего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e4f23-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4f23-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e4f23-107">Requirements</span></span>  
 <span data-ttu-id="e4f23-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4f23-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4f23-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e4f23-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e4f23-110">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e4f23-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e4f23-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4f23-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f23-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e4f23-112">See also</span></span>

- [<span data-ttu-id="e4f23-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="e4f23-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="e4f23-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="e4f23-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

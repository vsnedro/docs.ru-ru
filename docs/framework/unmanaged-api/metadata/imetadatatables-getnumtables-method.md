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
ms.openlocfilehash: 7e1ea16e7954f21b1349e88d43d7e3b271a57ed7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680298"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="a46db-102">Метод IMetaDataTables::GetNumTables</span><span class="sxs-lookup"><span data-stu-id="a46db-102">IMetaDataTables::GetNumTables Method</span></span>

<span data-ttu-id="a46db-103">Возвращает количество таблиц в области текущего `IMetaDataTables` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a46db-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a46db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a46db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a46db-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a46db-105">Parameters</span></span>  

 `pcTables`  
 <span data-ttu-id="a46db-106">заполняет Указатель на число таблиц в области текущего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a46db-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a46db-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a46db-107">Requirements</span></span>  

 <span data-ttu-id="a46db-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a46db-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a46db-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a46db-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a46db-110">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a46db-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a46db-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a46db-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a46db-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a46db-112">See also</span></span>

- [<span data-ttu-id="a46db-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="a46db-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="a46db-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="a46db-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

---
title: Метод IMetaDataTables::GetString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
ms.openlocfilehash: 8ecaa003084064be1071a85aa726c38d773ec0b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672582"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="38e88-102">Метод IMetaDataTables::GetString</span><span class="sxs-lookup"><span data-stu-id="38e88-102">IMetaDataTables::GetString Method</span></span>

<span data-ttu-id="38e88-103">Возвращает строку по указанному индексу из столбца таблицы в области текущей ссылки.</span><span class="sxs-lookup"><span data-stu-id="38e88-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38e88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38e88-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="38e88-105">Parameters</span></span>  

 `ixString`  
 <span data-ttu-id="38e88-106">окне Индекс, с которого начинается поиск следующего значения.</span><span class="sxs-lookup"><span data-stu-id="38e88-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="38e88-107">заполняет Указатель на указатель на возвращаемое строковое значение.</span><span class="sxs-lookup"><span data-stu-id="38e88-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38e88-108">Требования</span><span class="sxs-lookup"><span data-stu-id="38e88-108">Requirements</span></span>  

 <span data-ttu-id="38e88-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38e88-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38e88-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="38e88-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38e88-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38e88-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38e88-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38e88-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e88-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="38e88-113">See also</span></span>

- [<span data-ttu-id="38e88-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="38e88-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="38e88-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="38e88-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

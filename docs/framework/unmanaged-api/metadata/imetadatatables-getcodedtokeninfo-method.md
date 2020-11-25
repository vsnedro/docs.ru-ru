---
title: Метод IMetaDataTables::GetCodedTokenInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
ms.openlocfilehash: b79ac7f71ec0551336298a90829e1f37e2e30b20
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711091"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="f9a3a-102">Метод IMetaDataTables::GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="f9a3a-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>

<span data-ttu-id="f9a3a-103">Возвращает указатель на массив токенов, связанных с указанным индексом строки.</span><span class="sxs-lookup"><span data-stu-id="f9a3a-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9a3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9a3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9a3a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9a3a-105">Parameters</span></span>  

 `ixCdTkn`  
 <span data-ttu-id="f9a3a-106">окне Тип возвращаемого закодированного токена.</span><span class="sxs-lookup"><span data-stu-id="f9a3a-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f9a3a-107">заполняет Указатель на длину `ppTokens` .</span><span class="sxs-lookup"><span data-stu-id="f9a3a-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="f9a3a-108">заполняет Указатель на указатель на массив, содержащий список возвращенных токенов.</span><span class="sxs-lookup"><span data-stu-id="f9a3a-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="f9a3a-109">заполняет Указатель на указатель на имя маркера в `ixCdTkn` .</span><span class="sxs-lookup"><span data-stu-id="f9a3a-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9a3a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f9a3a-110">Requirements</span></span>  

 <span data-ttu-id="f9a3a-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9a3a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9a3a-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f9a3a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9a3a-113">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9a3a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9a3a-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9a3a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a3a-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f9a3a-115">See also</span></span>

- [<span data-ttu-id="f9a3a-116">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="f9a3a-116">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="f9a3a-117">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="f9a3a-117">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

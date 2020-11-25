---
title: Метод IMetaDataTables::GetBlob
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
ms.openlocfilehash: 32f32625ee40d50249ce3e009add543c4137b196
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726474"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="81855-102">Метод IMetaDataTables::GetBlob</span><span class="sxs-lookup"><span data-stu-id="81855-102">IMetaDataTables::GetBlob Method</span></span>

<span data-ttu-id="81855-103">Возвращает указатель на большой двоичный объект (BLOB) по указанному индексу столбца.</span><span class="sxs-lookup"><span data-stu-id="81855-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81855-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81855-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81855-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="81855-105">Parameters</span></span>  

 `ixBlob`  
 <span data-ttu-id="81855-106">окне Адрес памяти, из которого будет получено значение `ppData` .</span><span class="sxs-lookup"><span data-stu-id="81855-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="81855-107">заполняет Указатель на размер в байтах `ppData` .</span><span class="sxs-lookup"><span data-stu-id="81855-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="81855-108">заполняет Указатель на указатель на извлекаемые двоичные данные.</span><span class="sxs-lookup"><span data-stu-id="81855-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81855-109">Требования</span><span class="sxs-lookup"><span data-stu-id="81855-109">Requirements</span></span>  

 <span data-ttu-id="81855-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81855-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81855-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="81855-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="81855-112">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="81855-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="81855-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81855-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81855-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="81855-114">See also</span></span>

- [<span data-ttu-id="81855-115">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="81855-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="81855-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="81855-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

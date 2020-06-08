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
ms.openlocfilehash: ff97e419c5309fa7cb820cb7e82db96fee34f30c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501278"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="16521-102">Метод IMetaDataTables::GetBlob</span><span class="sxs-lookup"><span data-stu-id="16521-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="16521-103">Возвращает указатель на большой двоичный объект (BLOB) по указанному индексу столбца.</span><span class="sxs-lookup"><span data-stu-id="16521-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16521-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16521-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16521-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="16521-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="16521-106">окне Адрес памяти, из которого будет получено значение `ppData` .</span><span class="sxs-lookup"><span data-stu-id="16521-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="16521-107">заполняет Указатель на размер в байтах `ppData` .</span><span class="sxs-lookup"><span data-stu-id="16521-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="16521-108">заполняет Указатель на указатель на извлекаемые двоичные данные.</span><span class="sxs-lookup"><span data-stu-id="16521-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16521-109">Требования</span><span class="sxs-lookup"><span data-stu-id="16521-109">Requirements</span></span>  
 <span data-ttu-id="16521-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16521-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16521-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="16521-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="16521-112">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="16521-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="16521-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16521-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16521-114">См. также</span><span class="sxs-lookup"><span data-stu-id="16521-114">See also</span></span>

- [<span data-ttu-id="16521-115">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="16521-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="16521-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="16521-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

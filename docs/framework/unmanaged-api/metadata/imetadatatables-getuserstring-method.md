---
title: Метод IMetaDataTables::GetUserString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
ms.openlocfilehash: 21ce66722e069573b651ada950b64ef6d97220fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501148"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="b3e39-102">Метод IMetaDataTables::GetUserString</span><span class="sxs-lookup"><span data-stu-id="b3e39-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="b3e39-103">Получает жестко заданную строку по указанному индексу в строковом столбце текущей области.</span><span class="sxs-lookup"><span data-stu-id="b3e39-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="b3e39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3e39-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="b3e39-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3e39-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="b3e39-106">окне Значение индекса, из которого будет извлечена жестко заданная строка.</span><span class="sxs-lookup"><span data-stu-id="b3e39-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="b3e39-107">заполняет Указатель на размер `ppData` .</span><span class="sxs-lookup"><span data-stu-id="b3e39-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="b3e39-108">заполняет Указатель на указатель на возвращаемую строку.</span><span class="sxs-lookup"><span data-stu-id="b3e39-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="b3e39-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b3e39-109">Requirements</span></span>

<span data-ttu-id="b3e39-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3e39-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b3e39-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b3e39-111">**Header:** Cor.h</span></span>

<span data-ttu-id="b3e39-112">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b3e39-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="b3e39-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3e39-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b3e39-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b3e39-114">See also</span></span>

- [<span data-ttu-id="b3e39-115">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="b3e39-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b3e39-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="b3e39-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

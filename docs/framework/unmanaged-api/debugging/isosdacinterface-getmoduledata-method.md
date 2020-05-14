---
title: 'Метод ИсосдаЦинтерфаце:: Жетмодуледата'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 14e0eb812c84a0042150345d039451adf178caf1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396920"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="0d7de-102">Метод ИсосдаЦинтерфаце:: Жетмодуледата</span><span class="sxs-lookup"><span data-stu-id="0d7de-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="0d7de-103">Извлекает данные, соответствующие модулю, загруженному по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="0d7de-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0d7de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d7de-104">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="0d7de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d7de-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="0d7de-106">окне Адрес модуля, для которого нужно получить сведения.</span><span class="sxs-lookup"><span data-stu-id="0d7de-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="0d7de-107">заполняет [Структура дакпмодуледата](dacpmoduledata-structure.md) для хранения сведений о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="0d7de-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d7de-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="0d7de-108">Remarks</span></span>

<span data-ttu-id="0d7de-109">Предоставленный метод является частью `ISOSDacInterface` интерфейса и соответствует слоту 14 таблицы виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="0d7de-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="0d7de-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0d7de-110">Requirements</span></span>

<span data-ttu-id="0d7de-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d7de-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0d7de-112">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="0d7de-112">**Header:** None</span></span>  
<span data-ttu-id="0d7de-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="0d7de-113">**Library:** None</span></span>  
<span data-ttu-id="0d7de-114">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0d7de-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0d7de-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="0d7de-115">See also</span></span>

- [<span data-ttu-id="0d7de-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="0d7de-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="0d7de-117">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="0d7de-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)

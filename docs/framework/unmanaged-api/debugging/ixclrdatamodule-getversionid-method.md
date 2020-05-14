---
title: 'Метод Иксклрдатамодуле:: Жетверсионид'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetVersionId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetVersionId Method
helpviewer.keywords:
- IXCLRDataModule::GetVersionId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ff8ccf42d1131fb15d7473ae12ecefde9d55177f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395280"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="f993a-102">Метод Иксклрдатамодуле:: Жетверсионид</span><span class="sxs-lookup"><span data-stu-id="f993a-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="f993a-103">Возвращает идентификатор версии модуля.</span><span class="sxs-lookup"><span data-stu-id="f993a-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f993a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f993a-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="f993a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f993a-105">Parameters</span></span>

`vid`\
<span data-ttu-id="f993a-106">заполняет Идентификатор версии модуля.</span><span class="sxs-lookup"><span data-stu-id="f993a-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="f993a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f993a-107">Remarks</span></span>

<span data-ttu-id="f993a-108">Предоставленный метод является частью `IXCLRDataModule` интерфейса и соответствует слоту й таблицы виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="f993a-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="f993a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f993a-109">Requirements</span></span>

<span data-ttu-id="f993a-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f993a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f993a-111">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="f993a-111">**Header:** None</span></span>  
<span data-ttu-id="f993a-112">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="f993a-112">**Library:** None</span></span>  
<span data-ttu-id="f993a-113">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f993a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f993a-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f993a-114">See also</span></span>

- [<span data-ttu-id="f993a-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="f993a-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="f993a-116">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="f993a-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

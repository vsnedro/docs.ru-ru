---
title: 'Метод Иксклрдатамодуле:: Жетмесоддефинитионбитокен'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 074949145be588fc34266a9f2ee501caeeffb9d3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420881"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="7816b-102">Метод Иксклрдатамодуле:: Жетмесоддефинитионбитокен</span><span class="sxs-lookup"><span data-stu-id="7816b-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="7816b-103">Возвращает определение метода, соответствующее заданному маркеру метаданных.</span><span class="sxs-lookup"><span data-stu-id="7816b-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7816b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7816b-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="7816b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7816b-105">Parameters</span></span>

`token`\
<span data-ttu-id="7816b-106">окне Токен метода.</span><span class="sxs-lookup"><span data-stu-id="7816b-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="7816b-107">заполняет Определение метода.</span><span class="sxs-lookup"><span data-stu-id="7816b-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="7816b-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7816b-108">Remarks</span></span>

<span data-ttu-id="7816b-109">Предоставленный метод является частью `IXCLRDataModule` интерфейса и соответствует слоту 26th таблицы виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="7816b-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="7816b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7816b-110">Requirements</span></span>

<span data-ttu-id="7816b-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7816b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7816b-112">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="7816b-112">**Header:** None</span></span>  
<span data-ttu-id="7816b-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="7816b-113">**Library:** None</span></span>  
<span data-ttu-id="7816b-114">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7816b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7816b-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="7816b-115">See also</span></span>

- [<span data-ttu-id="7816b-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="7816b-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="7816b-117">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="7816b-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

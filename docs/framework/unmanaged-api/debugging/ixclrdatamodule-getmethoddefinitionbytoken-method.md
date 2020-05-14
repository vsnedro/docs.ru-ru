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
ms.openlocfilehash: c70920205b27376d453bdd0a13223c6a5569075b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395298"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="52fe9-102">Метод Иксклрдатамодуле:: Жетмесоддефинитионбитокен</span><span class="sxs-lookup"><span data-stu-id="52fe9-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="52fe9-103">Возвращает определение метода, соответствующее заданному маркеру метаданных.</span><span class="sxs-lookup"><span data-stu-id="52fe9-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="52fe9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52fe9-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="52fe9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52fe9-105">Parameters</span></span>

`token`\
<span data-ttu-id="52fe9-106">окне Токен метода.</span><span class="sxs-lookup"><span data-stu-id="52fe9-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="52fe9-107">заполняет Определение метода.</span><span class="sxs-lookup"><span data-stu-id="52fe9-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="52fe9-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="52fe9-108">Remarks</span></span>

<span data-ttu-id="52fe9-109">Предоставленный метод является частью `IXCLRDataModule` интерфейса и соответствует слоту 26th таблицы виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="52fe9-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="52fe9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="52fe9-110">Requirements</span></span>

<span data-ttu-id="52fe9-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52fe9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="52fe9-112">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="52fe9-112">**Header:** None</span></span>  
<span data-ttu-id="52fe9-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="52fe9-113">**Library:** None</span></span>  
<span data-ttu-id="52fe9-114">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="52fe9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="52fe9-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="52fe9-115">See also</span></span>

- [<span data-ttu-id="52fe9-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="52fe9-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="52fe9-117">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="52fe9-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

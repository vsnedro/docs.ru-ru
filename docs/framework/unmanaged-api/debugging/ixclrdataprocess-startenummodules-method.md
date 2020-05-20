---
title: 'Метод Иксклрдатапроцесс:: Стартенуммодулес'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d55b07ea3fada73237919bf677163a9096d5ad04
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420725"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="7b243-102">Метод Иксклрдатапроцесс:: Стартенуммодулес</span><span class="sxs-lookup"><span data-stu-id="7b243-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="7b243-103">Предоставляет описатель для перечисления модулей процесса.</span><span class="sxs-lookup"><span data-stu-id="7b243-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7b243-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b243-104">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="7b243-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b243-105">Parameters</span></span>

`handle`\
<span data-ttu-id="7b243-106">заполняет Маркер для перечисления модулей.</span><span class="sxs-lookup"><span data-stu-id="7b243-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b243-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7b243-107">Remarks</span></span>

<span data-ttu-id="7b243-108">Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует слоту 24 таблицы виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="7b243-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="7b243-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7b243-109">Requirements</span></span>

<span data-ttu-id="7b243-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b243-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7b243-111">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="7b243-111">**Header:** None</span></span>  
<span data-ttu-id="7b243-112">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="7b243-112">**Library:** None</span></span>  
<span data-ttu-id="7b243-113">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7b243-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7b243-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="7b243-114">See also</span></span>

- [<span data-ttu-id="7b243-115">Перечисление Клрдатасаурцетипе</span><span class="sxs-lookup"><span data-stu-id="7b243-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="7b243-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="7b243-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="7b243-117">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="7b243-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

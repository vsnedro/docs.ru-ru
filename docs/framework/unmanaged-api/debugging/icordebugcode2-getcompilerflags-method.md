---
title: Метод ICorDebugCode2::GetCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
ms.openlocfilehash: 734a05d96aed309541708d4e6f80ed61cab85637
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893499"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="f0891-102">Метод ICorDebugCode2::GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="f0891-102">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="f0891-103">Возвращает флаги, указывающие условия, при которых этот объект кода был либо JIT-скомпилирован, либо создан с помощью генератора образов в машинном коде (Ngen. exe).</span><span class="sxs-lookup"><span data-stu-id="f0891-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="f0891-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0891-104">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="f0891-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0891-105">Parameters</span></span>

`pdwFlags`  
<span data-ttu-id="f0891-106">заполняет Указатель на значение перечисления [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) , которое указывает поведение JIT-компилятора или генератора образов в машинном код.</span><span class="sxs-lookup"><span data-stu-id="f0891-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0891-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f0891-107">Requirements</span></span>

<span data-ttu-id="f0891-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0891-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f0891-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0891-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="f0891-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0891-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="f0891-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0891-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

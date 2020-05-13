---
title: Метод ICorDebugModule2::ResolveAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
ms.openlocfilehash: e64e39d10d20f63430ffe9d2c4df8643e286a677
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210043"
---
# <a name="icordebugmodule2resolveassembly-method"></a>Метод ICorDebugModule2::ResolveAssembly

Разрешает сборку, на которую ссылается указанный токен метаданных.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a>Параметры

`tkAssemblyRef`\
окне `mdToken`Значение, которое ссылается на сборку.

`ppAssembly`\
заполняет Указатель на адрес объекта ICorDebugAssembly, который представляет сборку.

## <a name="remarks"></a>Remarks

Если сборка еще не загружена при `ResolveAssembly` вызове метода, возвращается значение HRESULT, равное CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

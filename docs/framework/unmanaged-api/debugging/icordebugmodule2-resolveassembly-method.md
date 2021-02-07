---
description: 'Дополнительные сведения о методе: ICorDebugModule2:: Ресолвеассембли'
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
ms.openlocfilehash: fba53b8ff76e4d3deb1876d2a20a7a2edc20bd06
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722598"
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
окне `mdToken` Значение, которое ссылается на сборку.

`ppAssembly`\
заполняет Указатель на адрес объекта ICorDebugAssembly, который представляет сборку.

## <a name="remarks"></a>Remarks

Если сборка еще не загружена при `ResolveAssembly` вызове метода, возвращается значение HRESULT, равное CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

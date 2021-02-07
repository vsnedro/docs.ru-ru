---
description: 'Дополнительные сведения: метод ICorDebugFunction:: GetLocalVarSigToken'
title: Метод ICorDebugFunction::GetLocalVarSigToken
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
ms.openlocfilehash: cd7fb03829285ddcb1da2f1a93985fa1f98d3d39
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692502"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a>Метод ICorDebugFunction::GetLocalVarSigToken

Возвращает маркер метаданных для сигнатуры локальной переменной функции, представленной этим экземпляром ICorDebugFunction.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pmdSig`  
 заполняет Указатель на `mdSignature` маркер для сигнатуры локальной переменной этой функции или `mdSignatureNil` , если эта функция не имеет локальных переменных.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

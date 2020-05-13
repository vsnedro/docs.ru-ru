---
title: Метод ICorDebugNativeFrame::GetLocalDoubleRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
ms.openlocfilehash: 21c4d00e4156b9db27ae4188aace19764a2be53e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213079"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a>Метод ICorDebugNativeFrame::GetLocalDoubleRegisterValue
Возвращает значение аргумента или локальной переменной, которая хранится в двух указанных регистрах для этого собственного кадра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `highWordReg`  
 окне Значение перечисления "CorDebugRegister", указывающее регистр, содержащий старшее слово значения.  
  
 `lowWordReg`  
 окне Значение `CorDebugRegister` перечисления, указывающее регистр, содержащий нижнее слово значения.  
  
 `cbSigBlob`  
 окне Целое число, указывающее размер подписи двоичных метаданных, на которую ссылается `pvSigBlob` параметр.  
  
 `pvSigBlob`  
 окне `PCCOR_SIGNATURE`Значение, которое указывает на сигнатуру двоичных метаданных для типа значения.  
  
 `ppValue`  
 заполняет Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение, хранящееся в указанных регистрах.  
  
## <a name="remarks"></a>Remarks  
 `GetLocalDoubleRegisterValue`Метод можно использовать либо в машинном кадре, либо в кадре JIT-компиляции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

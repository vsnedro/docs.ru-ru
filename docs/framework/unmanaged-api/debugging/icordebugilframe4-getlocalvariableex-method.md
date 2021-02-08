---
description: 'Дополнительные сведения о методе: ICorDebugILFrame4:: GetLocalVariableEx'
title: Метод ICorDebugILFrame4::GetLocalVariableEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
ms.openlocfilehash: 4eb6b3abbaf05c0373a487d9bd9d575b58a9af49
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791222"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a>Метод ICorDebugILFrame4::GetLocalVariableEx

[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Получает значение указанной локальной переменной в этом кадре стека промежуточного языка (IL) и дополнительно получает доступ к переменной, добавленной в инструментарий ReJIT профилировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,
   [in] DWORD dwIndex,
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `flags`  
 окне Элемент перечисления [ILCodeKind](ilcodekind-enumeration.md) , указывающий, включается ли переменная, добавленная в инструментирование профилировщика ReJIT, в кадр.  
  
 `dwIndex`  
 [в] Индекс локальной переменной в кадре стека промежуточного языка.  
  
 `ppValue`  
 заполняет Указатель на адрес объекта ICorDebugValue, который представляет извлеченное значение.  
  
## <a name="remarks"></a>Remarks  

 Этот метод аналогичен методу [жетлокалвариабле](icordebugilframe-getlocalvariable-method.md) , за исключением того, что он дополнительно получает доступ к переменной, добавленной в инструментарий профилировщика ReJIT. Вызов этого метода со `flags` значением `ILCODE_ORIGINAL_IL` эквивалентен вызову [жетлокалвариабле](icordebugilframe-getlocalvariable-method.md); если метод оснащен дополнительными локальными переменными, доступ к этим переменным невозможен. `ILCODE_REJIT_IL` обеспечивает отладчику доступ к локальным переменным, добавленным в инструментарий ReJIT профилировщика. Если промежуточный язык не инструментирован, метод возвращает значение `E_INVALIDARG`.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugILFrame4](icordebugilframe4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [ReJIT: руководство по How-To](/archive/blogs/davbr/rejit-a-how-to-guide)

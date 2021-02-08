---
description: 'Дополнительные сведения о методе: ICorDebugILFrame3:: Жетретурнвалуефорилоффсет'
title: Метод ICorDebugILFrame3::GetReturnValueForILOffset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
ms.openlocfilehash: 4be4cb3a108394f2701f6690b06f6c2252ae25cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791274"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>Метод ICorDebugILFrame3::GetReturnValueForILOffset

Возвращает объект ICorDebugValue, инкапсулирующий возвращаемое значение функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ILOffset`  
 Смещение IL. См. раздел «Примечания».  
  
 `ppReturnValue`  
 Указатель на адрес объекта "ICorDebugValue" интерфейса, который предоставляет сведения о возвращаемом значении вызова функции.  
  
## <a name="remarks"></a>Remarks  

 Этот метод используется вместе с методом [ICorDebugCode3:: жетретурнвалуеливеоффсет](icordebugcode3-getreturnvalueliveoffset-method.md) для получения возвращаемого значения метода. Это особенно полезно в случае с методами, возвращаемые значения которых игнорируются, как в следующих двух примерах кода. Первый пример вызывает <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> метод, но игнорирует возвращаемое значение метода.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 Во втором примере показана гораздо более распространенная проблема при отладке. Так как метод используется в качестве аргумента в вызове метода, его возвращаемое значение доступно только в том случае, если отладчик проходит через вызываемый метод. Во многих случаях, особенно если вызванный метод определен во внешней библиотеке, это невозможно.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Если передать метод [ICorDebugCode3:: жетретурнвалуеливеоффсет](icordebugcode3-getreturnvalueliveoffset-method.md) в качестве смещения Il на сайт вызова функции, он возвращает одно или несколько машинных смещений. Затем отладчик может установить точки останова для этих собственных смещений в функции. Когда отладчик обращается к одной из точек останова, можно передать то же смещение IL, которое вы передали этому методу для получения возвращаемого значения. Затем отладчик должен очистить все заданные точки останова.  
  
> [!WARNING]
> Метод и методы [ICorDebugCode3:: жетретурнвалуеливеоффсет](icordebugcode3-getreturnvalueliveoffset-method.md) `ICorDebugILFrame3::GetReturnValueForILOffset` позволяют получать сведения о возвращаемых значениях только для ссылочных типов. Получение сведений о возвращаемых значениях из типов значений (то есть все типы, производные от <xref:System.ValueType> ) не поддерживаются.  
  
 Смещение IL, заданное `ILOffset` параметром, должно находиться на сайте вызова функции, а отладка должна быть остановлена в точке останова, установленной в машинном смещении, возвращенном методом [ICorDebugCode3:: жетретурнвалуеливеоффсет](icordebugcode3-getreturnvalueliveoffset-method.md) для того же смещения IL. Если отлаживаемая программа не остановлена в правильном расположении для указанного смещения IL, API завершится ошибкой.  
  
 Если вызов функции не возвращает значение, API завершится ошибкой.  
  
 `ICorDebugILFrame3::GetReturnValueForILOffset`Метод доступен только в системах на базе x86 и AMD64.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md)
- [Интерфейс ICorDebugILFrame3](icordebugilframe3-interface.md)

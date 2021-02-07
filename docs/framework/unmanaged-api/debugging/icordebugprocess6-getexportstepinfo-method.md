---
description: 'Дополнительные сведения о методе: ICorDebugProcess6:: Жетекспортстепинфо'
title: Метод ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: e14b5e66d90fb2ece91991b3634fc2ad86fac895
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722013"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a>Метод ICorDebugProcess6::GetExportStepInfo

Предоставляет информацию о функциях, экспортируемых в ходе выполнения, для пошагового перемещения по управляемому коду.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a>Параметры  

 pszExportName  
 [входной] Имя функции экспорта во время выполнения, записываемой в таблице экспорта PE.  
  
 invokeKind  
 заполняет Указатель на член перечисления [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) , описывающий, как экспортируемая функция будет вызывать управляемый код.  
  
 invokePurpose  
 заполняет Указатель на член перечисления [кордебугкодеинвокепурпосе](cordebugcodeinvokepurpose-enumeration.md) , описывающий, почему экспортируемая функция будет вызывать управляемый код.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Метод может возвращать значения, перечисленные в следующей таблице.  
  
|Возвращаемое значение|Описание|  
|------------------|-----------------|  
|`S_OK`|Успешный вызов метода.|  
|`E_POINTER`|`pInvokeKind` или `pInvokePurpose` имеет **значение NULL**.|  
|Другие ошибочные значения `HRESULT`.|По мере необходимости.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess6](icordebugprocess6-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)

---
description: 'Дополнительные сведения о: Интерфейс IMetaDataEmit2'
title: Интерфейс IMetaDataEmit2
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: db1880d64bf3b1e9084d6745251c174788a4afe7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745688"
---
# <a name="imetadataemit2-interface"></a>Интерфейс IMetaDataEmit2

Расширяет интерфейс [IMetaDataEmit](imetadataemit-interface.md) в основном, чтобы обеспечить возможность работы с универсальными типами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DefineGenericParam](imetadataemit2-definegenericparam-method.md)|Создает определение для параметра универсального типа и получает маркер для этого параметра универсального типа.|  
|[Метод DefineMethodSpec](imetadataemit2-definemethodspec-method.md)|Создает универсальный экземпляр метода и получает маркер для определения.|  
|[Метод GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md)|Возвращает значение, указывающее разницу в размере данных, необходимых для выражения изменений в текущем сеансе "изменить и продолжить".|  
|[Метод ResetENCLog](imetadataemit2-resetenclog-method.md)|Сбрасывает журнал изменения и продолжения и запускает новый сеанс.|  
|[Метод SaveDelta](imetadataemit2-savedelta-method.md)|Сохраняет изменения из текущего сеанса "изменить и продолжить" в указанный файл.|  
|[Метод SaveDeltaToMemory](imetadataemit2-savedeltatomemory-method.md)|Сохраняет изменения из текущего сеанса "изменить и продолжить" в память.|  
|[Метод SaveDeltaToStream](imetadataemit2-savedeltatostream-method.md)|Сохраняет изменения из текущего сеанса "изменить и продолжить" в указанный поток.|  
|[Метод SetGenericParamProps](imetadataemit2-setgenericparamprops-method.md)|Задает значения свойств для определения универсального параметра, на которое ссылается указанный токен.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](metadata-interfaces.md)
- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)

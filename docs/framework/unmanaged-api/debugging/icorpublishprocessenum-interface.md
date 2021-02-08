---
description: 'Дополнительные сведения о: интерфейс ICorPublishProcessEnum'
title: Интерфейс ICorPublishProcessEnum
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 87d80d066995dbeca67f461e01652dd3deb3bf1b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790494"
---
# <a name="icorpublishprocessenum-interface"></a>Интерфейс ICorPublishProcessEnum

Подкласс интерфейса [ICorPublishEnum](icorpublishenum-interface.md) , предоставляющий методы для прохода по коллекции объектов [ICorPublishProcess](icorpublishprocess-interface.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Следующий метод](icorpublishprocessenum-next-method.md)|Возвращает указанное количество `ICorPublishProcess` экземпляров из коллекции, начиная с текущей позиции.|  
  
## <a name="remarks"></a>Remarks  

 `ICorPublishProcessEnum`Интерфейс реализует методы абстрактного интерфейса [ICorPublishEnum](icorpublishenum-interface.md).  
  
 `ICorPublishProcessEnum`Экземпляр создается методом [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) . Обход коллекции `ICorPublishProcess` объектов основан на условиях фильтрации, заданных на момент `ICorPublishProcessEnum` создания экземпляра.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Кокласс CorpubPublish](corpubpublish-coclass.md)

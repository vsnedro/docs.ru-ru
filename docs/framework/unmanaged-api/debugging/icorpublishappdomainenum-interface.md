---
description: 'Дополнительные сведения о: интерфейс ICorPublishAppDomainEnum'
title: Интерфейс ICorPublishAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: 4e84af576103a792308fd44f903f2ae4daa5d736
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721792"
---
# <a name="icorpublishappdomainenum-interface"></a>Интерфейс ICorPublishAppDomainEnum

Подкласс интерфейса [ICorPublishEnum](icorpublishenum-interface.md) , предоставляющий методы для прохода по коллекции объектов [ICorPublishAppDomain](icorpublishappdomain-interface.md) , которые в данный момент существуют в процессе.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Следующий метод](icorpublishappdomainenum-next-method.md)|Возвращает указанное количество `ICorPublishAppDomain` экземпляров из коллекции, начиная с текущей позиции.|  
  
## <a name="remarks"></a>Remarks  

 `ICorPublishAppDomainEnum`Интерфейс реализует методы абстрактного интерфейса [ICorPublishEnum](icorpublishenum-interface.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Кокласс CorpubPublish](corpubpublish-coclass.md)

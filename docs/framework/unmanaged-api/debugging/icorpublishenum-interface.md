---
description: 'Дополнительные сведения о: интерфейс ICorPublishEnum'
title: Интерфейс ICorPublishEnum
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
ms.openlocfilehash: c0d50f67bd61eecbade0b226f2f569ac26712faf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721610"
---
# <a name="icorpublishenum-interface"></a>Интерфейс ICorPublishEnum

Служит абстрактным базовым интерфейсом для перечислителей, используемых в публикации сведений о процессах и доменах приложений.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](icorpublishenum-clone-method.md)|Создает копию данного объекта `ICorPublishEnum`.|  
|[Метод GetCount](icorpublishenum-getcount-method.md)|Возвращает число элементов в перечислении.|  
|[Метод Reset](icorpublishenum-reset-method.md)|Перемещает курсор в начало перечисления.|  
|[Метод Skip](icorpublishenum-skip-method.md)|Перемещает курсор вперед в перечислении на указанное число элементов.|  
  
## <a name="remarks"></a>Remarks  

 Следующие перечислители являются производными от `ICorPublishEnum` :  
  
- [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)  
  
- [ICorPublishProcessEnum](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Кокласс CorpubPublish](corpubpublish-coclass.md)
- [Интерфейсы отладки](debugging-interfaces.md)

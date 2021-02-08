---
description: 'Дополнительные сведения о: Интерфейс IMetaDataError'
title: Интерфейс IMetaDataError
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
ms.openlocfilehash: f32c8abc3cccce770b86ce47016d9b7e18acad23
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771695"
---
# <a name="imetadataerror-interface"></a>Интерфейс IMetaDataError

Предоставляет механизм обратного вызова для сообщения об ошибках во время слияния метаданных.  
  
> [!NOTE]
> `IMetaDataError`Интерфейс должен быть реализован клиентом.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод OnError](imetadataerror-onerror-method.md)|Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](metadata-interfaces.md)

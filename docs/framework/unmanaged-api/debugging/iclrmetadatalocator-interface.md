---
title: Интерфейс ICLRMetadataLocator
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
ms.openlocfilehash: 734f8eaa7c520bbf1ad1208ece42751e967a208a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859719"
---
# <a name="iclrmetadatalocator-interface"></a>Интерфейс ICLRMetadataLocator
Используется уровнем служб доступа к данным для определения местоположения метаданных сборок в целевом процессе.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Metadata](iclrmetadatalocator-getmetadata-method.md)|Извлекает метаданные изображения из целевого процесса.|  
  
## <a name="remarks"></a>Примечания  
 Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости. Например, реализация для активного процесса будет отличаться от реализации дампа памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)

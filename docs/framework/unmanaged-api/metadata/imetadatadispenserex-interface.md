---
title: Интерфейс IMetaDataDispenserEx
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
ms.openlocfilehash: 96f0c0c254ce255581ac2937c805096918ab29e8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008057"
---
# <a name="imetadatadispenserex-interface"></a>Интерфейс IMetaDataDispenserEx
Расширяет интерфейс [интерфейса IMetaDataDispenser](imetadatadispenser-interface.md) , чтобы предоставить возможность контролировать работу API метаданных в текущей области метаданных.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод FindAssembly](imetadatadispenserex-findassembly-method.md)|Этот метод не реализован. При вызове возвращается E_NOTIMPL.|  
|[Метод FindAssemblyModule](imetadatadispenserex-findassemblymodule-method.md)|Этот метод не реализован. При вызове возвращается E_NOTIMPL.|  
|[Метод GetCORSystemDirectory](imetadatadispenserex-getcorsystemdirectory-method.md)|Возвращает каталог, содержащий текущую среду CLR. Этот метод поддерживается только для использования необработанными отладчиками. Если вызывается из другого компонента, он возвратит E_NOTIMPL.|  
|[Метод GetOption](imetadatadispenserex-getoption-method.md)|Возвращает значение указанного параметра для текущей области метаданных. Параметр определяет, как обрабатываются вызовы к текущей области метаданных.|  
|[Метод OpenScopeOnITypeInfo](imetadatadispenserex-openscopeonitypeinfo-method.md)|Этот метод не реализован. При вызове возвращается E_NOTIMPL.|  
|[Метод SetOption](imetadatadispenserex-setoption-method.md)|Задает для указанного параметра заданное значение для текущей области метаданных. Параметр определяет, как обрабатываются вызовы к текущей области метаданных.|  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейсы метаданных](metadata-interfaces.md)
- [Интерфейс IMetaDataDispenser](imetadatadispenser-interface.md)
- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)

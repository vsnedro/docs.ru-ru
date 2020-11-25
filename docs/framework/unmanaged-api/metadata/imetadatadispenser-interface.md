---
title: Интерфейс IMetaDataDispenser
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: c798aeba46adf91a8c13f8143c00f02173a0bb52
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726118"
---
# <a name="imetadatadispenser-interface"></a>Интерфейс IMetaDataDispenser

Предоставляет методы для создания новой области метаданных или открытия существующей.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DefineScope](imetadatadispenser-definescope-method.md)|Создает новую область в памяти, в которой можно создавать новые метаданные.|  
|[Метод OpenScope](imetadatadispenser-openscope-method.md)|Открывает существующий файл на диске и сопоставляет его метаданные с памятью.|  
|[Метод OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md)|Открывает область памяти, которая содержит существующие метаданные. Это значит, что этот метод открывает указанную область памяти, в которой существующие данные обрабатываются как метаданные.|  
  
## <a name="requirements"></a>Требования  

 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Интерфейсы метаданных](metadata-interfaces.md)

---
description: 'Дополнительные сведения о: интерфейс IMetaDataDispenser'
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
ms.openlocfilehash: 5ba37fc05a4e1897b100967d32b268f91a0e4402
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721012"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Интерфейсы метаданных](metadata-interfaces.md)

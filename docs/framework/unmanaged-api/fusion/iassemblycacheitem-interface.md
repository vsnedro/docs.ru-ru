---
description: 'Дополнительные сведения о: интерфейс IAssemblyCacheItem'
title: Интерфейс IAssemblyCacheItem
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
ms.openlocfilehash: 2dcb721f6b65ecca93262f9af2ba355d94bb774d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760874"
---
# <a name="iassemblycacheitem-interface"></a>Интерфейс IAssemblyCacheItem

Представляет отдельную сборку в глобальном кэше сборок.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AbortItem](iassemblycacheitem-abortitem-method.md)|Позволяет сборке в глобальном кэше сборок выполнять операции очистки до ее освобождения.|  
|[Метод Commit](iassemblycacheitem-commit-method.md)|Фиксирует в памяти ссылку на кэшированную сборку.|  
|[Метод CreateStream](iassemblycacheitem-createstream-method.md)|Создает поток с указанными именем и форматом.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Fusion-интерфейсы](fusion-interfaces.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)
- [Интерфейс IAssemblyCache](iassemblycache-interface.md)

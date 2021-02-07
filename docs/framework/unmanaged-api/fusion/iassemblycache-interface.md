---
description: 'Дополнительные сведения о: интерфейс IAssemblyCache'
title: Интерфейс IAssemblyCache
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
ms.openlocfilehash: 29c042fc101180085a697e02376b91b0e1ffd19f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760931"
---
# <a name="iassemblycache-interface"></a>Интерфейс IAssemblyCache

Представляет глобальный кэш сборок для использования технологией Fusion.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateAssemblyCacheItem](iassemblycache-createassemblycacheitem-method.md)|Возвращает ссылку на новый [IAssemblyCacheItem](iassemblycacheitem-interface.md).|  
|[Метод CreateAssemblyScavenger](iassemblycache-createassemblyscavenger-method.md)|Зарезервировано для внутреннего использования технологией Fusion.|  
|[Метод InstallAssembly](iassemblycache-installassembly-method.md)|Устанавливает указанную сборку в глобальный кэш сборок.|  
|[Метод QueryAssemblyInfo](iassemblycache-queryassemblyinfo-method.md)|Возвращает запрошенные данные о указанной сборке.|  
|[Метод UninstallAssembly](iassemblycache-uninstallassembly-method.md)|Удаляет указанную сборку из глобального кэша сборок.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Fusion-интерфейсы](fusion-interfaces.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)

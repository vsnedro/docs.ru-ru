---
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
ms.openlocfilehash: df4f0ba018b55202c22cb90b22b927a9c426c4ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696860"
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
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Fusion-интерфейсы](fusion-interfaces.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)

---
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
ms.openlocfilehash: 72922d1fd0f8ae5e59fe76c7aa50f9c52dcd5302
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719948"
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
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Fusion-интерфейсы](fusion-interfaces.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)
- [Интерфейс IAssemblyCache](iassemblycache-interface.md)

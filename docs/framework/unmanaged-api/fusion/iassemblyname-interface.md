---
title: Интерфейс IAssemblyName
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
ms.openlocfilehash: f6feed9f59715f9a2801cd3a2a99a087957d4377
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715073"
---
# <a name="iassemblyname-interface"></a>Интерфейс IAssemblyName

Предоставляет методы для описания и работы с уникальным удостоверением сборки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](iassemblyname-clone-method.md)|Создает неполную копию этого `IAssemblyName` объекта.|  
|[Метод Finalize](iassemblyname-finalize-method.md)|Разрешает этому `IAssemblyName` объекту освобождать ресурсы и выполнять другие операции очистки перед вызовом деструктора.|  
|[Метод GetDisplayName](iassemblyname-getdisplayname-method.md)|Возвращает удобное для восприятия имя сборки, на которую ссылается этот `IAssemblyName` объект.|  
|[Метод GetName](iassemblyname-getname-method.md)|Возвращает простое незашифрованное имя сборки, на которую ссылается этот `IAssemblyName` объект.|  
|[Метод GetProperty](iassemblyname-getproperty-method.md)|Возвращает указатель на свойство, на которое ссылается указанный объект `PropertyId` .|  
|[Метод GetVersion](iassemblyname-getversion-method.md)|Возвращает сведения о версии для сборки, на которую ссылается этот `IAssemblyName` объект.|  
|[Метод IsEqual](iassemblyname-isequal-method.md)|Определяет `IAssemblyName` , равен ли указанный объект этому объекту `IAssemblyName` на основе указанных флагов сравнения.|  
|[Метод SetProperty](iassemblyname-setproperty-method.md)|Задает значение свойства, на которое ссылается указанный объект `PropertyId` .|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Fusion-интерфейсы](fusion-interfaces.md)
- [Интерфейс IAssemblyEnum](iassemblyenum-interface.md)

---
description: 'Дополнительные сведения о: интерфейс ICLRAssemblyIdentityManager'
title: Интерфейс ICLRAssemblyIdentityManager
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: d6238ec51a8cc1bb61eaa96e5297656c447df785
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790062"
---
# <a name="iclrassemblyidentitymanager-interface"></a>Интерфейс ICLRAssemblyIdentityManager

Предоставляет методы, поддерживающие взаимодействие между узлом и общеязыковой средой выполнения (CLR) о сборках.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetBindingIdentityFromFile](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|Возвращает данные привязки удостоверения сборки для сборки по указанному пути к файлу.|  
|[Метод GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|Возвращает канонические данные удостоверений сборки для сборки в указанном потоке.|  
|[Метод GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|Возвращает экземпляр [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) из заданного списка частичных идентификаторов сборки.|  
|[Метод GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|Возвращает перечислитель [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) для удостоверений сборок, на которые ссылается сборка с указанным удостоверением.|  
|[Метод GetReferencedAssembliesFromFile](iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|Возвращает экземпляр [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) , содержащий список сборок, на которые ссылается сборка по указанному пути к файлу.|  
|[Метод GetReferencedAssembliesFromStream](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|Возвращает указатель на `ICLRReferenceAssemblyEnum` объект, содержащий данные идентификации сборки для сборок, на которые ссылается сборка в указанном потоке.|  
|[Метод IsStronglyNamed](iclrassemblyidentitymanager-isstronglynamed-method.md)|Возвращает значение, указывающее, является ли указанная сборка строго именованной.|  
  
## <a name="remarks"></a>Remarks  

 Используйте `ICLRAssemblyIdentityManager` для получения экземпляров `ICLRAssemblyReferenceList` и для перечисления идентификаторов сборок.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Интерфейс ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)

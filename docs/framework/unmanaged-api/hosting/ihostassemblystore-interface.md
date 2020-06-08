---
title: Интерфейс IHostAssemblyStore
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
ms.openlocfilehash: cca73eec663b9afd12ecea5ab9d7073ea0168d33
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501564"
---
# <a name="ihostassemblystore-interface"></a>Интерфейс IHostAssemblyStore
Предоставляет методы, позволяющие узлу загружать сборки и модули независимо от общеязыковой среды выполнения (CLR).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ProvideAssembly](ihostassemblystore-provideassembly-method.md)|Возвращает ссылку на сборку, на которую не ссылается [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , возвращенную из вызова [IHostAssemblyManager:: GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).|  
|[Метод ProvideModule](ihostassemblystore-providemodule-method.md)|Разрешает модуль в сборке или в связанном (не внедренном) файле ресурсов.|  
  
## <a name="remarks"></a>Примечания  
 `IHostAssemblyStore`Предоставляет узлу способ эффективного загрузки сборок на основе удостоверения сборки. Узел загружает сборки, возвращая `IStream` экземпляры, которые указывают непосредственно в байтах.  
  
 Среда CLR определяет, реализован ли узел `IHostAssemblyStore` путем вызова `IHostAssemblyManager::GetNonHostAssemblyStores` после инициализации. Это позволяет узлу, например, управлять привязкой к пользовательским сборкам, а также использовать среду выполнения для привязки к .NET Framework сборкам.  
  
> [!NOTE]
> При предоставлении реализации `IHostAssemblyStore` узел определяет его цель для разрешения всех сборок, на которые не ссылается объект, `ICLRAssemblyReferenceList` возвращенный из `IHostAssemblyManager::GetNonHostStoreAssemblies` .  
  
> [!NOTE]
> .NET Framework версии 2,0 не позволяет узлу загружать машинный образ сборки, как это предоставляется служебной программой [генератора образов в машинном код (Ngen. exe)](../../tools/ngen-exe-native-image-generator.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](ihostassemblymanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)

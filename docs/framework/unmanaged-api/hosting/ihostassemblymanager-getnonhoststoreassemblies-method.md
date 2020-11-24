---
title: Метод IHostAssemblyManager::GetNonHostStoreAssemblies
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
ms.openlocfilehash: a34b907514376927d8a1aa66b136916108b704d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681149"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a>Метод IHostAssemblyManager::GetNonHostStoreAssemblies

Возвращает указатель интерфейса на объект [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , представляющий список сборок, которые должны загружаться хостом в среде CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppReferenceList`  
 заполняет Указатель на адрес объекта `ICLRAssemblyReferenceList` , содержащий список ссылок на сборки, которые узел загружает в среду CLR.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`GetNonHostStoreAssemblies` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно свободной памяти для создания списка ссылок для запрошенного объекта `ICLRAssemblyReferenceList` .|  
  
## <a name="remarks"></a>Комментарии  

 Среда CLR разрешает ссылки с помощью следующего набора рекомендаций:  
  
- Во первых, он обращается к списку ссылок на сборки, возвращаемых `GetNonHostStoreAssemblies` .  
  
- Если сборка отображается в списке, среда CLR привязывает ее к обычному.  
  
- Если сборка не отображается в списке и узел предоставил реализацию [IHostAssemblyStore](ihostassemblystore-interface.md), среда CLR вызывает [IHostAssemblyStore::P ровидеассембли](ihostassemblystore-provideassembly-method.md) , чтобы разрешить узлу предоставить сборку для привязки.  
  
- В противном случае среда CLR не сможет выполнить привязку к сборке.  
  
 Если узел `ppReferenceList` имеет значение null, среда CLR сначала проверяет глобальный кэш сборок, вызывает `ProvideAssembly` , а затем проверяет базу приложения для разрешения ссылки на сборку.  
  
> [!NOTE]
> После инициализации среда CLR вызывает `GetNonHostStoreAssemblies` только один раз. Метод не вызывается снова.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](ihostassemblymanager-interface.md)
- [Интерфейс IHostAssemblyStore](ihostassemblystore-interface.md)

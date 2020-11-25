---
title: Метод IHostAssemblyStore::ProvideModule
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
ms.openlocfilehash: 35805d277774e1de03bb7dee1740a2e1305a97c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733000"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>Метод IHostAssemblyStore::ProvideModule

Разрешает модуль в сборке или связанном (но не внедренном) файле ресурсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pBindInfo`  
 окне Указатель на экземпляр [модулебиндинфо](modulebindinfo-structure.md) , который описывает имя запрашиваемого модуля <xref:System.AppDomain> , сборки и имени модуля.  
  
 `pdwModuleId`  
 заполняет Указатель на уникальный идентификатор для `IStream` содержащего загруженного модуля.  
  
 `ppStmModuleImage`  
 заполняет Указатель на адрес `IStream` объекта, который содержит загружаемый переносимый исполняемый файл (PE), или значение null, если не удалось найти модуль.  
  
 `ppStmPDB`  
 заполняет Указатель на адрес `IStream` объекта, который содержит сведения об отладке программы (PDB) для запрошенного модуля, или значение null, если PDB-файл найти не удалось.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`ProvideModule` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|Не удалось найти запрошенную сборку или связанный ресурс.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` недостаточно велик, чтобы вместить идентификатор, который требуется вернуть узлу.|  
  
## <a name="remarks"></a>Комментарии  

 Значение идентификатора, возвращенное для `pdwModuleId` , задается узлом. Идентификаторы должны быть уникальными в течение всего времени существования процесса. Среда CLR использует это значение в качестве уникального идентификатора для связанного потока. Он проверяет каждое значение по значениям `pAssemblyId` , возвращаемым вызовами [провидеассембли](ihostassemblystore-provideassembly-method.md) , и значениями, `pdwModuleId` возвращаемыми другими вызовами метода `ProvideModule` . Если узел возвращает одно и то же значение идентификатора для другого `IStream` , среда CLR проверяет, было ли уже сопоставлено содержимое этого потока. Если это так, среда CLR загружает существующую копию изображения вместо сопоставления нового. Таким образом, идентификатор также не должен перекрываться с идентификаторами сборок, возвращенными из `ProvideAssembly` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](ihostassemblymanager-interface.md)
- [Интерфейс IHostAssemblyStore](ihostassemblystore-interface.md)

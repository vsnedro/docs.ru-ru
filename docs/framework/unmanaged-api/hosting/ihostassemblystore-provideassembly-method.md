---
description: 'Дополнительные сведения о методе: IHostAssemblyStore::P Ровидеассембли'
title: Метод IHostAssemblyStore::ProvideAssembly
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
ms.openlocfilehash: f8917cb28dd3898343a7b6ee08bd54096df8cfa7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789506"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>Метод IHostAssemblyStore::ProvideAssembly

Возвращает ссылку на сборку, на которую не ссылается [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , возвращаемую из [IHostAssemblyManager:: GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md). Среда CLR вызывает `ProvideAssembly` для каждой сборки, которая не отображается в списке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pBindInfo`  
 окне Указатель на экземпляр [ассемблибиндинфо](assemblybindinfo-structure.md) , используемый узлом для определения определенных характеристик привязки, включая присутствие или отсутствие политики управления версиями, а также сборку, к которой необходимо выполнить привязку.  
  
 `pAssemblyId`  
 заполняет Указатель на уникальный идентификатор для запрошенной сборки для этого `IStream` .  
  
 `pHostContext`  
 заполняет Указатель на данные конкретного узла, который используется для определения свидетельства запрошенной сборки без вызова неуправляемого кода. `pHostContext` соответствует <xref:System.Reflection.Assembly.HostContext%2A> свойству управляемого <xref:System.Reflection.Assembly> класса.  
  
 `ppStmAssemblyImage`  
 заполняет Указатель на адрес объекта `IStream` , который содержит загружаемый переносимый исполняемый файл (PE), или значение null, если сборку найти не удалось.  
  
 `ppStmPDB`  
 заполняет Указатель на адрес `IStream` , содержащий сведения об отладке программы (PDB), или значение null, если PDB-файл не найден.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|Не удалось найти запрошенную сборку.|  
|E_NOT_SUFFICIENT_BUFFER|Размер буфера, указанный в, `pAssemblyId` недостаточно велик для хранения идентификатора, который требуется вернуть узлу.|  
  
## <a name="remarks"></a>Remarks  

 Значение идентификатора, возвращенное для `pAssemblyId` , задается узлом. Идентификаторы должны быть уникальными в течение всего времени существования процесса. Среда CLR использует это значение в качестве уникального идентификатора потока. Он проверяет каждое значение по значениям `pAssemblyId` , возвращаемым другими вызовами метода `ProvideAssembly` . Если узел возвращает одно и то же `pAssemblyId` значение для другого `IStream` , среда CLR проверяет, было ли уже сопоставлено содержимое этого потока. Если это так, среда выполнения загружает существующую копию изображения вместо сопоставления нового.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](ihostassemblymanager-interface.md)
- [Интерфейс IHostAssemblyStore](ihostassemblystore-interface.md)

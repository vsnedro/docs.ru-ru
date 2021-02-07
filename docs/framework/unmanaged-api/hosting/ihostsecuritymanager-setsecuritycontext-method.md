---
description: 'Дополнительные сведения о методе: IHostSecurityManager:: SetSecurityContext'
title: Метод IHostSecurityManager::SetSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
ms.openlocfilehash: ee2de40e043e626aba1d75540faab3cae4c8fb7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671481"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a>Метод IHostSecurityManager::SetSecurityContext

Задает контекст безопасности выполняемого в данный момент потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `eContextType`  
 окне Одно из значений [еконтексттипе](econtexttype-enumeration.md) , указывающее, какой тип контекста используется средой CLR для размещения на узле.  
  
 `ppSecurityContext`  
 заполняет Указатель на адрес нового объекта [IHostSecurityContext](ihostsecuritycontext-interface.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`SetSecurityContext` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 Среда CLR вызывает `SetSecurityContext` в нескольких сценариях. Перед выполнением конструкторов классов и модулей и методов завершения среда CLR вызывает `SetSecurityContext` для защиты узла от сбоев при выполнении. Затем он сбрасывает контекст безопасности до исходного состояния после выполнения конструктора или метода завершения, используя другой вызов `SetSecurityContext` . Аналогичный шаблон происходит при завершении ввода-вывода. Если узел реализует [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), среда CLR вызывает `SetSecurityContext` после того, как узел вызывает [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md).  
  
 В асинхронных точках рабочих потоков среда CLR вызывает `SetSecurityContext` в <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> или внутри [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)в зависимости от того, РЕАЛИЗУЕТ ли узел или CLR пул потоков.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [Перечисление EContextType](econtexttype-enumeration.md)
- [Интерфейс ICLRIoCompletionManager](iclriocompletionmanager-interface.md)
- [Интерфейс IHostIoCompletionManager](ihostiocompletionmanager-interface.md)
- [Интерфейс IHostSecurityContext](ihostsecuritycontext-interface.md)
- [Интерфейс IHostSecurityManager](ihostsecuritymanager-interface.md)
- [Интерфейс IHostThreadPoolManager](ihostthreadpoolmanager-interface.md)

---
description: 'Дополнительные сведения о методе: IHostSecurityManager:: Getsecuritycontext-'
title: Метод IHostSecurityManager::GetSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
ms.openlocfilehash: 0dc9e0380d2fb218b68f6beb85fa1ccba8826d85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671569"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a>Метод IHostSecurityManager::GetSecurityContext

Возвращает запрошенный [IHostSecurityContext](ihostsecuritycontext-interface.md) из узла.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `eContextType`  
 окне Одно из значений [еконтексттипе](econtexttype-enumeration.md) , указывающее тип возвращаемого контекста безопасности.  
  
 `ppSecurityContext`  
 заполняет Адрес указателя интерфейса на `IHostSecurityContext` `eContextType` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`GetSecurityContext` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 Узел может управлять доступом кода к маркерам потоков как средой CLR, так и кодом пользователя. Он также может гарантировать, что полные сведения о контексте безопасности передаются по асинхронным операциям или кодовым точкам с ограниченным доступом к коду. `IHostSecurityContext` инкапсулирует эти сведения о контексте безопасности, которые непрозрачны для среды CLR. Среда CLR захватывает эти сведения и перемещает их между отправкой рабочего элемента пула потоков, выполнением метода завершения, а также созданием модулей и классов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EContextType](econtexttype-enumeration.md)
- [Интерфейс IHostSecurityContext](ihostsecuritycontext-interface.md)
- [Интерфейс IHostSecurityManager](ihostsecuritymanager-interface.md)

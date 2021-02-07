---
description: 'Дополнительные сведения о методе: Iclrerrorreportingmanagergetbucketparametersforcurrentexception:: BeginCustomDump'
title: Метод ICLRErrorReportingManager::BeginCustomDump
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
ms.openlocfilehash: 3f8498068d50ffc6ea00cf4f08f969c92f010d6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689486"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a>Метод ICLRErrorReportingManager::BeginCustomDump

Задает конфигурацию дампов пользовательской кучи для отчетов об ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwFlavor`  
 окне Значение [екустомдумпфлавор](ecustomdumpflavor-enumeration.md) , указывающее тип дампа кучи, на основе которого создается дамп пользовательской кучи.  
  
 `dwNumItems`  
 окне Длина `items` массива. Если `dwFlavor` значение не DUMP_FLAVOR_Mini, `dwNumItems` должно быть равно нулю.  
  
 `items`  
 окне Массив экземпляров [кустомдумпитем](customdumpitem-structure.md) , указывающий элементы для добавления в мини-дамп. Если `dwFlavor` значение не DUMP_FLAVOR_Mini, `items` должно быть равно null.  
  
 `dwReserved`  
 [in] Зарезервирован для будущего использования.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод возвратился успешно.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 `BeginCustomDump`Метод задает конфигурацию дампа пользовательской кучи. Метод [ендкустомдумп](iclrerrorreportingmanager-endcustomdump-method.md) очищает конфигурацию дампа пользовательской кучи и освобождает любое связанное состояние. Он должен вызываться после завершения создания дампа пользовательской кучи.  
  
> [!IMPORTANT]
> Сбой вызова `EndCustomDump` приводит к утечке памяти.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структура CustomDumpItem](customdumpitem-structure.md)
- [Перечисление ECustomDumpFlavor](ecustomdumpflavor-enumeration.md)
- [Интерфейс ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)

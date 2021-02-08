---
description: 'Дополнительные сведения о методе: ICLRRuntimeHost:: ExecuteInDefaultAppDomain'
title: Метод ICLRRuntimeHost::ExecuteInDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
ms.openlocfilehash: 0fae9be69cf67da252dcdb423432ec922c0b00ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785139"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a>Метод ICLRRuntimeHost::ExecuteInDefaultAppDomain

Вызывает указанный метод указанного типа в указанной управляемой сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzAssemblyPath`  
 окне Путь к элементу <xref:System.Reflection.Assembly> , который определяет <xref:System.Type> метод, для которого нужно вызвать.  
  
 `pwzTypeName`  
 окне Имя объекта <xref:System.Type> , определяющего вызываемый метод.  
  
 `pwzMethodName`  
 окне Имя вызываемого метода.  
  
 `pwzArgument`  
 окне Строковый параметр для передачи в метод.  
  
 `pReturnValue`  
 заполняет Целочисленное значение, возвращаемое вызванным методом.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает E_FAIL, список отзыва сертификатов больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 Вызванный метод должен иметь следующую сигнатуру:  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 где `pwzMethodName` представляет имя вызванного метода и `pwzArgument` представляет строковое значение, передаваемое в качестве параметра этому методу. Если значение HRESULT установлено в S_OK, то для параметра задается `pReturnValue` целочисленное значение, возвращаемое вызванным методом. В противном случае `pReturnValue` значение не задано.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeHost](iclrruntimehost-interface.md)

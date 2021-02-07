---
description: 'Дополнительные сведения о методе: ICLRProbingAssemblyEnum:: Get'
title: Метод ICLRProbingAssemblyEnum::Get
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
ms.openlocfilehash: 77fb93b30a3b9b01b32fef9af661c84f484ef758
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716527"
---
# <a name="iclrprobingassemblyenumget-method"></a>Метод ICLRProbingAssemblyEnum::Get

Возвращает удостоверение сборки по указанному индексу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwIndex`  
 окне Отсчитываемый от нуля индекс возвращаемого удостоверения сборки.  
  
 `pwzBuffer`  
 заполняет Буфер, содержащий данные удостоверения сборки.  
  
 `pcchBufferSize`  
 [вход, выход] Размер `pwzBuffer` буфера.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`Get` успешно возвращено.|  
|ERROR_INSUFFICIENT_BUFFER|`pwzBuffer` слишком мал.|  
|ERROR_NO_MORE_ITEMS|Перечисление не содержит больше элементов.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы любых методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 Удостоверение с индексом 0 — это удостоверение, относящееся к архитектуре процессора. Удостоверение с индексом 1 — это нейтральная к архитектуре сборка для промежуточного языка Майкрософт (MSIL). Удостоверение с индексом 2 не содержит сведений об архитектуре.  
  
 `Get` обычно вызывается дважды. Первый вызов предоставляет значение NULL для `pwzBuffer` , а устанавливает `pcchBufferSize` в качестве размера, соответствующего `pwzBuffer` . Второй вызов предоставляет соответствующий размер `pwzBuffer` и содержит канонические данные удостоверений сборки после завершения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md)
- [Интерфейс ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)

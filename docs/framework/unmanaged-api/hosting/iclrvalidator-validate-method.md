---
description: 'Дополнительные сведения о методе: Иклрвалидатор:: Validate'
title: Метод ICLRValidator::Validate
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
ms.openlocfilehash: a188315d44021fc8bf40be9bb9aecac436351467
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636748"
---
# <a name="iclrvalidatorvalidate-method"></a>Метод ICLRValidator::Validate

Проверяет переносимый исполняемый (PE) или промежуточный язык Майкрософт (MSIL) в указанном файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);
```  
  
## <a name="parameters"></a>Параметры  

 `veh`  
 окне Указатель на `IVEHandler` экземпляр, который обрабатывает ошибки проверки.  
  
 `ulAppDomainId`  
 окне Идентификатор текущего <xref:System.AppDomain> .  
  
 `ulFlags`  
 окне Сочетание значений [валидаторфлагс](validatorflags-enumeration.md) , указывающих тип проверки, которую следует выполнить.  
  
 `ulMaxError`  
 окне Максимальное число ошибок, которое необходимо разрешить перед выходом из проверки.  
  
 `token`  
 [in] Не используется.  
  
 `fileName`  
 окне Имя проверяемого файла.  
  
 `pe`  
 окне Указатель на файловый буфер.  
  
 `ulSize`  
 окне Размер проверяемого файла в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`Validate` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** IValidator. idl, IValidator. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRValidator](iclrvalidator-interface.md)

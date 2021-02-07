---
description: 'Дополнительные сведения о методе: IValidator:: Validate'
title: Метод IValidator::Validate
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
ms.openlocfilehash: 6df70274a788b949686fe2509b525c5a8b04089c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680022"
---
# <a name="ivalidatorvalidate-method"></a>Метод IValidator::Validate

Проверяет указанный переносимый исполняемый (PE) или промежуточный язык MSIL-файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `veh`  
 окне Указатель на `IVEHandler` экземпляр, который обрабатывает ошибки проверки.  
  
 `pAppDomain`  
 окне Указатель на домен приложения, в который загружается файл.  
  
 `ulFlags`  
 окне Побитовое сочетание значений [валидаторфлагс](validatorflags-enumeration.md) , указывающее, какие проверки должны быть выполнены.  
  
 `ulMaxError`  
 окне Максимальное число ошибок, которое необходимо разрешить перед выходом из проверки.  
  
 `token`  
 [in] Не используется.  
  
 `fileName`  
 окне Строка, указывающая имя проверяемого файла.  
  
 `pe`  
 окне Указатель на буфер памяти, в котором хранится файл.  
  
 `ulSize`  
 окне Размер проверяемого файла в байтах.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** IValidator. idl, IValidator. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  

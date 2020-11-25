---
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
ms.openlocfilehash: 3c59114f78af1aa8705318af093e47d4f03a82ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699148"
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
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  

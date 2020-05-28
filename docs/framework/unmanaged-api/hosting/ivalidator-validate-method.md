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
ms.openlocfilehash: 688abd210cca193bf03c40f000b74ecb66eb8ede
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008551"
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
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  

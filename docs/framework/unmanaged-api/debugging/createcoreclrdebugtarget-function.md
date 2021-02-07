---
description: Дополнительные сведения о функции Креатекореклрдебугтаржет
title: Функция CreateCoreClrDebugTarget
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: 30a6af29e6e1a6ee2c827049a3c792f2d663a702
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661580"
---
# <a name="createcoreclrdebugtarget-function"></a>Функция CreateCoreClrDebugTarget

Создает подключение к прокси-серверу отладчика, запущенному на удаленном компьютере, и возвращает объект [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) , который можно использовать для запроса выполняющихся процессов и загрузки сред выполнения на удаленном компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwAddress`  
 [in] IPv4-адрес удаленного целевого компьютера.  
  
 `ppTarget`  
 заполняет Указатель на указатель на объект [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) , который будет создан.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK  
 Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.  
  
 E_OUTOFMEMORY  
 Не удается выделить достаточно памяти для `ppTarget`.  
  
 E_FAIL (или другие коды возврата E_)  
 Прочие сбои.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Кореклрремотедебуггингинтерфацес. h  
  
 **Библиотека:** mscordbi_macx86.dll  
  
 **Платформа .NET Framework версии:** 3,5 SP1

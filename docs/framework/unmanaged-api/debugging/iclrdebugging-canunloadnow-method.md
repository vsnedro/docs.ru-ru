---
description: 'Дополнительные сведения о методе: ICLRDebugging:: CanUnloadNow'
title: Метод ICLRDebugging::CanUnloadNow
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
ms.openlocfilehash: 537494fe862c58aa8a8768dd5ce2abc8ca94f87d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723378"
---
# <a name="iclrdebuggingcanunloadnow-method"></a>Метод ICLRDebugging::CanUnloadNow

Определяет, используется ли по-прежнему Библиотека, предоставленная интерфейсом [иклрдебуггинглибрарипровидер](iclrdebugginglibraryprovider-interface.md) , или она может быть выгружена.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a>Параметры  

 `hmodule`  
 окне Базовый адрес модуля в целевом процессе.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Модуль, на который указывает ссылка, `hmodule` может быть выгружен.|  
|S_FALSE|Модуль, на который ссылается, по `hmodule` -прежнему используется.|  
|COR_E_NOT_CLR|Указанный модуль не является модулем CLR.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Remarks  

 Этот метод проверяет, освобождаются ли все экземпляры `ICorDebug*` интерфейсов, и пока нет потоков в вызове метода [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)

---
description: 'Дополнительные сведения о методе: ICorConfiguration:: АдддебугжерспеЦиалсреад'
title: Метод ICorConfiguration::AddDebuggerSpecialThread
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
ms.openlocfilehash: b6904c2e4d5c265244ac096e0d64c2fc7f5d1be5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636719"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a>Метод ICorConfiguration::AddDebuggerSpecialThread

Указывает службам отладки, что определенному потоку должен быть разрешено продолжать выполнение, пока отладчик не остановит работу приложения во время управляемых или неуправляемых сценариев отладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwSpecialThreadId`  
 окне Идентификатор потока, который должен быть разрешен для продолжения выполнения.  
  
## <a name="remarks"></a>Remarks  

 Указанный поток не может выполнять управляемый код или вводить среду выполнения каким бы то ни было образом. Примером такого потока может быть внутрипроцессный поток для поддержки устаревших отладчиков скриптов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorConfiguration](icorconfiguration-interface.md)

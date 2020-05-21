---
title: Интерфейс ICorConfiguration
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
ms.openlocfilehash: 3b8c9421dea4040a9f183b886f1ad8575cace780
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762437"
---
# <a name="icorconfiguration-interface"></a>Интерфейс ICorConfiguration
Предоставляет методы для настройки среды CLR.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AddDebuggerSpecialThread](icorconfiguration-adddebuggerspecialthread-method.md)|Указывает службам отладки, что определенному потоку должен быть разрешено продолжать выполнение, пока отладчик не остановит работу приложения во время управляемых или неуправляемых сценариев отладки.|  
|[Метод SetDebuggerThreadControl](icorconfiguration-setdebuggerthreadcontrol-method.md)|Задает интерфейс обратного вызова, который службы отладки будут вызывать как потоки CLR, блокируются и разблокируются для отладки.|  
|[Метод SetGCHostControl](icorconfiguration-setgchostcontrol-method.md)|Задает интерфейс обратного вызова, используемый сборщиком мусора для запроса изменения ограничения виртуальной памяти на узле.|  
|[Метод SetGCThreadControl](icorconfiguration-setgcthreadcontrol-method.md)|Задает интерфейс обратного вызова для потоков планирования для задач, не относящихся к среде выполнения, которые в противном случае были бы заблокированы для сборки мусора.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](hosting-interfaces.md)
- [Компонентный класс CorRuntimeHost](corruntimehost-coclass.md)

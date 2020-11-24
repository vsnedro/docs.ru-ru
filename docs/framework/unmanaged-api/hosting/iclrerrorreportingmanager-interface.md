---
title: Интерфейс ICLRErrorReportingManager
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
ms.openlocfilehash: d3816c8a3b6204b053505aa888eb28d696f8990b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677852"
---
# <a name="iclrerrorreportingmanager-interface"></a>Интерфейс ICLRErrorReportingManager

Предоставляет методы, позволяющие основному приложению настраивать пользовательские дампы стека для отчетов об ошибках.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md)|Задает конфигурацию пользовательских дампов стека для отчетов об ошибках.|  
|[Метод EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md)|Очищает конфигурацию пользовательского дампа стека, которая была задана предыдущим вызовом метода `BeginCustomDump` .|  
|[Метод GetBucketParametersForCurrentException](iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Возвращает контейнер Watson для текущего исключения в вызывающем потоке.|  
  
## <a name="remarks"></a>Комментарии  

 `BeginCustomDump`Метод задает конфигурацию пользовательского дампа стека. `EndCustomDump`Метод очищает конфигурацию дампа пользовательского стека и освобождает любое связанное состояние. Он должен вызываться после завершения пользовательского дампа.  
  
> [!IMPORTANT]
> Сбой вызова `EndCustomDump` приводит к утечке памяти.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисление ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md)
- [Интерфейсы размещения](hosting-interfaces.md)

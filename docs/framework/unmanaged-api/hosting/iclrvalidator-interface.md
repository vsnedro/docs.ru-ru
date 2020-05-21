---
title: Интерфейс ICLRValidator
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: e071f9cba7e991c59bf697647e0e4badea57573a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762049"
---
# <a name="iclrvalidator-interface"></a>Интерфейс ICLRValidator
Предоставляет методы для проверки переносимых исполняемых (PE) образов и создания отчетов об ошибках проверки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод FormatEventInfo](iclrvalidator-formateventinfo-method.md)|Возвращает подробное сообщение об указанной ошибке проверки.|  
|[Метод Validate](iclrvalidator-validate-method.md)|Проверяет переносимый исполняемый файл или язык MSIL в указанном файле.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** IValidator. idl, IValidator. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Кокласс CLRRuntimeHost](clrruntimehost-coclass.md)

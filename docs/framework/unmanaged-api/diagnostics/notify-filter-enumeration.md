---
title: Перечисление NOTIFY_FILTER
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
ms.openlocfilehash: b20e18d5f4314a0ab1442ac7bd5c6514e4db85d5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609486"
---
# <a name="notify_filter-enumeration"></a>Перечисление NOTIFY_FILTER
Определяет обратные вызовы для функций отладчика. Дополнительные сведения см. в описании метода [INotifySource2:: сетнотифифилтер](inotifysource2-setnotifyfilter-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|Указывает, что должен быть вызван метод [INotifySink2:: OnSyncCallOut](inotifysink2-onsynccallout-method.md) .|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|Указывает, что должен быть вызван метод [INotifySink2:: OnSyncCallEnter](inotifysink2-onsynccallenter-method.md) .|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|Указывает, что должен быть вызван метод [INotifySink2:: онсинккаллексит](inotifysink2-onsynccallexit-method.md) .|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|Указывает, что должен быть вызван метод [INotifySink2:: онсинккаллретурн](inotifysink2-onsynccallreturn-method.md) .|  
|`NOTIFY_FILTER_ALLSYNC`|Указывает, что должны быть вызваны все методы [INotifySink2](inotifysink2-interface.md) .|  
|`NOTIFY_FILTER_ALL`|Активирует все существующие и будущие уведомления.|  
|`NOTIFY_FILTER_NONE`|Указывает, что методы уведомления вызывать не нужно.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Дополнительно

- [Перечисления хранилища символов диагностики](diagnostics-symbol-store-enumerations.md)

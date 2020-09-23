---
title: Имя источника, указанное в EventLogSource, зарегистрировано в журнале, отличном от указанного в EventLogName
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 1b577e3b0613001b6241dcfdc59c8c84029197d2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058934"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>Имя источника, указанное в EventLogSource, зарегистрировано в журнале, отличном от указанного в EventLogName

`EventLog` пытается сослаться на источник, который зарегистрирован в другом журнале. Для добавления записей в журнал событий необходимо задать свойство <xref:System.Diagnostics.EventLog.Source%2A> . Свойство <xref:System.Diagnostics.EventLog.Source%2A> регистрирует компонент в журнале событий в качестве допустимого источника записей. Один источник может быть связан только с одним журналом событий одновременно (и поэтому может добавлять записи только в него).  
  
 По умолчанию при попытке добавить запись в журнал без предварительной регистрации компонента в качестве разрешенного источника система автоматически регистрирует его в этом журнале, используя значение свойства <xref:System.Diagnostics.EventLog.Source%2A> в качестве строки источника.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Убедитесь в том, что источник зарегистрирован в соответствующем журнале. Для этого используйте метод <xref:System.Diagnostics.EventLog.CreateEventSource%2A> или одну из его перегрузок, чтобы указать строку, однозначно идентифицирующую компонент в журнале событий.  
  
## <a name="see-also"></a>См. также

- [Администрирование журналов событий](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))
- [Ссылки на журнал событий](/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))
- [Как добавить приложение в качестве источника записей журнала событий](/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))
- [Как удалить источник события](/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))

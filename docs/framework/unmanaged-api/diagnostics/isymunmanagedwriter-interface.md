---
description: 'Дополнительные сведения о: интерфейс ISymUnmanagedWriter'
title: Интерфейс ISymUnmanagedWriter
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter
helpviewer_keywords:
- ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type:
- apiref
ms.openlocfilehash: 20fc0fd9b76b1aae4090582fe48a8a8e77d77c9f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762244"
---
# <a name="isymunmanagedwriter-interface"></a>Интерфейс ISymUnmanagedWriter

Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Abort](isymunmanagedwriter-abort-method.md)|Закрывает модуль записи символов без фиксации символов в хранилище символов.|  
|[Метод Close](isymunmanagedwriter-close-method.md)|Закрывает модуль записи символов после фиксации символов в хранилище символов.|  
|[Метод CloseMethod](isymunmanagedwriter-closemethod-method.md)|Закрывает текущий метод. После закрытия метода в нем нельзя определять символы.|  
|[Метод CloseNamespace](isymunmanagedwriter-closenamespace-method.md)|Закрывает Последнее открытое пространство имен.|  
|[Метод CloseScope](isymunmanagedwriter-closescope-method.md)|Закрывает текущую лексическую область видимости.|  
|[Метод DefineConstant](isymunmanagedwriter-defineconstant-method.md)|Определяет имя для постоянного значения.|  
|[Метод DefineDocument](isymunmanagedwriter-definedocument-method.md)|Определяет исходный документ.|  
|[Метод DefineField](isymunmanagedwriter-definefield-method.md)|Определяет одну переменную, не находящиеся в методе.|  
|[Метод DefineGlobalVariable](isymunmanagedwriter-defineglobalvariable-method.md)|Определяет одну глобальную переменную.|  
|[Метод DefineLocalVariable](isymunmanagedwriter-definelocalvariable-method.md)|Определяет одну переменную в текущей лексической области видимости.|  
|[Метод DefineParameter](isymunmanagedwriter-defineparameter-method.md)|Определяет один параметр в текущем методе.|  
|[Метод DefineSequencePoints](isymunmanagedwriter-definesequencepoints-method.md)|Определяет группу точек следования в текущем методе.|  
|[Метод GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md)|Возвращает сведения, необходимые компилятору для записи записи каталога отладки в заголовке переносимого исполняемого файла (PE).|  
|[Метод Initialize](isymunmanagedwriter-initialize-method.md)|Задает интерфейс передатчика метаданных, с которым будет связан этот модуль записи, и задает имя выходного файла, в который будут записываться отладочные символы.|  
|[Метод Initialize2](isymunmanagedwriter-initialize2-method.md)|Задает интерфейс передатчика метаданных, с которым будет связан этот модуль записи, задает имя выходного файла, в который будут записываться символы отладки, и задает конечное расположение файла базы данных программы (PDB).|  
|[Метод OpenMethod](isymunmanagedwriter-openmethod-method.md)|Открывает метод, в который порождается символьная информация.|  
|[Метод OpenNamespace](isymunmanagedwriter-opennamespace-method.md)|Открывает новое пространство имен.|  
|[Метод OpenScope](isymunmanagedwriter-openscope-method.md)|Открывает новую лексическую область видимости в текущем методе.|  
|[Метод RemapToken](isymunmanagedwriter-remaptoken-method.md)|Уведомляет средство записи символов о том, что маркер метаданных был повторно сопоставлен при выдаче метаданных.|  
|[Метод SetMethodSourceRange](isymunmanagedwriter-setmethodsourcerange-method.md)|Указывает истинные начало и конец метода в исходном файле.|  
|[Метод SetScopeRange](isymunmanagedwriter-setscoperange-method.md)|Определяет диапазон смещений для заданной лексической области видимости.|  
|[Метод SetSymAttribute](isymunmanagedwriter-setsymattribute-method.md)|Определяет настраиваемый атрибут на основе его имени.|  
|[Метод SetUserEntryPoint](isymunmanagedwriter-setuserentrypoint-method.md)|Задает определяемый пользователем метод, являющийся точкой входа для этого модуля.|  
|[Метод UsingNamespace](isymunmanagedwriter-usingnamespace-method.md)|Указывает, что данное полное имя пространства имен используется в открытой лексической области.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedWriter2](isymunmanagedwriter2-interface.md)
- [Интерфейс ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)

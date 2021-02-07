---
description: 'Дополнительные сведения о: Интерфейс ISymUnmanagedReader'
title: Интерфейс ISymUnmanagedReader
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
ms.openlocfilehash: bad4fdbac3bf6f03fa0db79ce54a5b0ca897028f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763804"
---
# <a name="isymunmanagedreader-interface"></a>Интерфейс ISymUnmanagedReader

Представляет средство чтения символов, которое предоставляет доступ к документам, методам и переменным в хранилище символов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetDocument](isymunmanagedreader-getdocument-method.md)|Находит документ.|  
|[Метод GetDocuments](isymunmanagedreader-getdocuments-method.md)|Возвращает массив всех документов, определенных в хранилище символов.|  
|[Метод GetDocumentVersion](isymunmanagedreader-getdocumentversion-method.md)|Возвращает указанную версию указанного документа.|  
|[Метод GetGlobalVariables](isymunmanagedreader-getglobalvariables-method.md)|Возвращает все глобальные переменные.|  
|[Метод GetMethod](isymunmanagedreader-getmethod-method.md)|Возвращает метод чтения символов по заданному токену метода.|  
|[Метод GetMethodByVersion](isymunmanagedreader-getmethodbyversion-method.md)|Возвращает метод чтения символов по заданному маркеру метода и номеру версии для редактирования и копирования.|  
|[Метод GetMethodFromDocumentPosition](isymunmanagedreader-getmethodfromdocumentposition-method.md)|Возвращает метод, содержащий точку останова в заданной позиции в документе.|  
|[Метод GetMethodsFromDocumentPosition](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Возвращает массив методов, каждый из которых содержит точку останова в заданной позиции в документе.|  
|[Метод GetMethodVersion](isymunmanagedreader-getmethodversion-method.md)|Возвращает версию метода.|  
|[Метод GetNamespaces](isymunmanagedreader-getnamespaces-method.md)|Возвращает пространства имен, определенные в глобальной области в этом хранилище символов.|  
|[Метод GetSymAttribute](isymunmanagedreader-getsymattribute-method.md)|Возвращает настраиваемый атрибут на основе его имени.|  
|[Метод GetSymbolStoreFileName](isymunmanagedreader-getsymbolstorefilename-method.md)|Предоставляет имя файла на диске для хранилища символов.|  
|[Метод GetUserEntryPoint](isymunmanagedreader-getuserentrypoint-method.md)|Возвращает метод, указанный в качестве точки входа пользователя для модуля, если он есть.|  
|[Метод GetVariables](isymunmanagedreader-getvariables-method.md)|Возвращает нелокальную переменную с учетом ее родителя и имени.|  
|[Метод Initialize](isymunmanagedreader-initialize-method.md)|Инициализирует средство чтения символов с помощью интерфейса средства импорта метаданных, с которым будет связан этот модуль чтения, вместе с именем файла модуля.|  
|[Метод ReplaceSymbolStore](isymunmanagedreader-replacesymbolstore-method.md)|Заменяет имеющееся хранилище символов разностным хранилищем символов.|  
|[Метод UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md)|Обновляет существующее хранилище символов разностным хранилищем символов.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedReader2](isymunmanagedreader2-interface.md)

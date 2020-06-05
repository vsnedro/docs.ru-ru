---
title: Оператор Error
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 35ba1f19654d1d23ac1ec73564bc36b0af4f6777
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404749"
---
# <a name="error-statement"></a>Оператор Error
Имитирует возникновение ошибки.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a>Компоненты  
 `errornumber`  
 Обязательный. Может быть любым допустимым номером ошибки.  
  
## <a name="remarks"></a>Комментарии  
 Эта `Error` инструкция поддерживается для обеспечения обратной совместимости. В новом коде, особенно при создании объектов, используйте `Err` `Raise` метод объекта для создания ошибок времени выполнения.  
  
 Если `errornumber` определено, `Error` инструкция вызывает обработчик ошибок после того, как свойства `Err` объекта присвоены следующие значения по умолчанию:  
  
|Свойство|Значение|  
|--------------|-----------|  
|`Number`|Значение, указанное в качестве аргумента `Error` инструкции. Может быть любым допустимым номером ошибки.|  
|`Source`|Имя текущего проекта Visual Basic.|  
|`Description`|Строковое выражение, соответствующее возвращаемому значению `Error` функции для указанного объекта `Number` , если эта строка существует. Если строка не существует, `Description` содержит строку нулевой длины ("").|  
|`HelpFile`|Полный диск, путь и имя файла подходящего файла справки Visual Basic.|  
|`HelpContext`|Соответствующий идентификатор контекста файла справки Visual Basic для ошибки, соответствующей `Number` свойству.|  
|`LastDLLError`|Ноль.|  
  
 Если обработчик ошибок не существует или не включен, сообщение об ошибке создается и отображается в `Err` свойствах объекта.  
  
> [!NOTE]
> Некоторые приложения Visual Basic узла не могут создавать объекты. Чтобы определить, может ли он создавать классы и объекты, см. документацию по ведущему приложению.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Error` оператор для создания номера ошибки 11.  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft. VisualBasic](../runtime-library-members.md)  
  
 **Сборка:** Библиотека времени выполнения Visual Basic (в Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [Оператор On Error](on-error-statement.md)
- [Оператор Resume](resume-statement.md)
- [сообщения об ошибках](../error-messages/index.md)

---
description: 'Дополнительные сведения: оператор End <keyword> (Visual Basic)'
title: Оператор End <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: ba21d4ba68a054d77d4f29307d49ed8e82bb6b50
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769199"
---
# <a name="end-keyword-statement-visual-basic"></a>Оператор End \<keyword> (Visual Basic)

Если за ним следует дополнительное ключевое слово, завершает определение блока операторов, представленного этим ключевым словом.

## <a name="syntax"></a>Синтаксис

```vb
End AddHandler
End Class
End Enum
End Event
End Function
End Get
End If
End Interface
End Module
End Namespace
End Operator
End Property
End RaiseEvent  
End RemoveHandler  
End Select
End Set
End Structure
End Sub
End SyncLock
End Try
End While
End With  
```  
  
## <a name="parts"></a>Компоненты

|Отделение|Описание|
|---|---|
|`End`|Обязательный элемент. Завершает определение программного элемента.|
|`AddHandler`|Требуется для завершения `AddHandler` метода доступа, начатого соответствующим `AddHandler` оператором в пользовательской [инструкции Event](event-statement.md).|
|`Class`|Требуется для завершения определения класса, начатого соответствующим [оператором класса](class-statement.md).|
|`Enum`|Требуется для завершения определения перечисления, начатого соответствующей [инструкцией enum](enum-statement.md).|
|`Event`|Требуется для завершения `Custom` определения события, начатого соответствующей [инструкцией Event](event-statement.md).|  
|`Function`|Требуется для завершения `Function` определения процедуры, начатой соответствующей [инструкцией Function](function-statement.md). Если выполнение встречает `End Function` оператор, управление возвращается в вызывающий код.|
|`Get`|Требуется для завершения `Property` определения процедуры, начатой соответствующей [инструкцией GET](get-statement.md). Если выполнение встречает `End Get` оператор, управление возвращается инструкции, запрашивающей значение свойства.|
|`If`|Требуется для завершения `If` ... `Then` ...`Else` блок определения, начатого соответствующим `If` оператором. См. раздел [If... Затем... Else, инструкция](if-then-else-statement.md).|
|`Interface`|Требуется для завершения определения интерфейса, начатого соответствующей [инструкцией интерфейса](interface-statement.md).|
|`Module`|Требуется для завершения определения модуля, начатого соответствующим [оператором модуля](module-statement.md).|
|`Namespace`|Требуется для завершения определения пространства имен, начатого соответствующей [инструкцией Namespace](namespace-statement.md).|
|`Operator`|Требуется для завершения определения оператора, начатого соответствующим [оператором оператора](operator-statement.md).|
|`Property`|Требуется для завершения определения свойства, начатого соответствующим [оператором Property](property-statement.md).|
|`RaiseEvent`|Требуется для завершения `RaiseEvent` метода доступа, начатого соответствующим `RaiseEvent` оператором в пользовательской [инструкции Event](event-statement.md).|
|`RemoveHandler`|Требуется для завершения `RemoveHandler` метода доступа, начатого соответствующим `RemoveHandler` оператором в пользовательской [инструкции Event](event-statement.md).|
|`Select`|Требуется для завершения `Select` определения блока..., `Case` начатого соответствующим `Select` оператором. См. раздел [SELECT... Case, инструкция](select-case-statement.md).  
|`Set`|Требуется для завершения `Property` определения процедуры, начатой соответствующей [инструкцией SET](set-statement.md). Если выполнение встречает `End Set` оператор, управление возвращается в инструкцию, устанавливая значение свойства.  
|`Structure`|Требуется для завершения определения структуры, начатой соответствующей [инструкцией Structure](structure-statement.md).  
|`Sub`|Требуется для завершения `Sub` определения процедуры, начатой соответствующим [подоператором](sub-statement.md). Если выполнение встречает `End Sub` оператор, управление возвращается в вызывающий код.  
|`SyncLock`|Требуется для завершения `SyncLock` определения блока, начатого соответствующим `SyncLock` оператором. См. раздел [оператор SyncLock](synclock-statement.md).  
|`Try`|Требуется для завершения `Try` ... `Catch` ...`Finally` блок определения, начатого соответствующим `Try` оператором. См [. раздел try... Перехватить... Оператор finally](try-catch-finally-statement.md).  
|`While`|Требуется для завершения `While` определения цикла, начатого соответствующим `While` оператором. См [. раздел while... Конец оператора while](while-end-while-statement.md).  
|`With`| Требуется для завершения `With` определения блока, начатого соответствующим `With` оператором. См [. раздел with... Конец оператора](with-end-with-statement.md).  
|||
  
## <a name="directives"></a>Директивы

Если перед ним стоит знак решетки ( `#` ), `End` ключевое слово завершает блок предварительной обработки, представленный соответствующей директивой.  

```vb
#End ExternalSource
#End If
#End Region
```

|Отделение|Описание|
|---|---|
|`#End`|Обязательный элемент. Завершает определение блока предварительной обработки.|
|`ExternalSource`|Требуется для завершения внешнего блока источника, начатого соответствующей [директивой #ExternalSource](../directives/externalsource-directive.md).|
|`If`|Требуется для завершения блока условной компиляции, начатого соответствующей `#If` директивой. См [. #If... Then... #Else директивы](../directives/if-then-else-directives.md).|
|`Region`|Требуется для завершения блока исходного региона, начатого соответствующей [директивой #Region](../directives/region-directive.md).|
|||

## <a name="remarks"></a>Remarks

[Оператор End](end-statement.md)без дополнительного ключевого слова завершает выполнение немедленно.

## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  

`End`Инструкция без дополнительного ключевого слова не поддерживается.  
  
## <a name="see-also"></a>См. также

- [End, инструкция](end-statement.md)

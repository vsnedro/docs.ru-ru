---
title: Практическое руководство. Удаление системного ресурса
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: dd15c6746628f45b072d46eea40051ed9afb7921
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403502"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Практическое руководство. Удаление системного ресурса (Visual Basic)
Вы можете использовать `Using` блок, чтобы гарантировать, что система уничтожает ресурс, когда код выходит из блока. Это полезно, если вы используете системный ресурс, который потребляет большой объем памяти или что другие компоненты также хотят использовать.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Удаление подключения к базе данных после завершения работы с ним кода  
  
1. Убедитесь, что вы включили соответствующий [оператор Imports (пространство имен .NET и тип)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) для подключения к базе данных в начале исходного файла (в данном случае <xref:System.Data.SqlClient> ).  
  
2. Создайте `Using` блок с `Using` `End Using` инструкциями и. Внутри блока разместите код, который работает с подключением к базе данных.  
  
3. Объявите соединение и создайте его экземпляр в составе `Using` инструкции.  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Система уничтожает ресурс независимо от того, как вы выйдете из блока, включая случай необработанного исключения.  
  
     Обратите внимание, что доступ извне блока невозможен `sqc` `Using` , так как его область ограничена блоком.  
  
     Эту же методику можно использовать для системных ресурсов, таких как файловый обработчик или оболочка COM. `Using`Если вы хотите оставить ресурс доступным для других компонентов после выхода из блока, используйте блок `Using` .  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.SqlClient.SqlConnection>
- [Поток управления](index.md)
- [Структуры решений](decision-structures.md)
- [Циклические структуры](loop-structures.md)
- [Другие структуры управления](other-control-structures.md)
- [Вложенные структуры управления](nested-control-structures.md)
- [Оператор using](../../../language-reference/statements/using-statement.md)

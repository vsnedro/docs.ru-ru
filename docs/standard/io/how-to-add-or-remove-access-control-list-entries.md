---
title: Практическое руководство. добавление или удаление записей списка управления доступом (только для .NET Framework)
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
ms.openlocfilehash: ff5a09207b3a1d810f9611dd6bb8cfd206adf1e8
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187974"
---
# <a name="how-to-add-or-remove-access-control-list-entries-net-framework-only"></a>Практическое руководство. добавление или удаление записей списка управления доступом (только для .NET Framework)

Для добавления или удаления записей списка управления доступом (ACL) из файла или каталога получите объект <xref:System.Security.AccessControl.FileSecurity> или <xref:System.Security.AccessControl.DirectorySecurity> из файла или каталога. Измените объект, а затем примените его к файлу или каталогу.  
  
## <a name="add-or-remove-an-acl-entry-from-a-file"></a>Добавление или удаление элемента списка ACL из файла  
  
1. Вызовите метод <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> для получения объекта <xref:System.Security.AccessControl.FileSecurity>, содержащего текущие элементы списка ACL файла.  
  
2. Добавьте и удалите элементы списка ACL из объекта <xref:System.Security.AccessControl.FileSecurity>, возвращенного в шаге 1.  
  
3. Чтобы применить изменения, передайте объект <xref:System.Security.AccessControl.FileSecurity> в метод <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType>.  
  
## <a name="add-or-remove-an-acl-entry-from-a-directory"></a>Добавление или удаление элемента списка ACL из каталога  
  
1. Вызовите метод <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> для получения объекта <xref:System.Security.AccessControl.DirectorySecurity>, содержащего текущие элементы списка ACL каталога.  
  
2. Добавьте и удалите элементы списка ACL из объекта <xref:System.Security.AccessControl.DirectorySecurity>, возвращенного в шаге 1.  
  
3. Чтобы применить изменения, передайте объект <xref:System.Security.AccessControl.DirectorySecurity> в метод <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
 Для выполнения этого примера необходимо указать допустимую учетную запись пользователя или группы. В этом примере используется объект <xref:System.IO.File>. Используйте ту же процедуру для классов <xref:System.IO.FileInfo>, <xref:System.IO.Directory> и <xref:System.IO.DirectoryInfo>.

 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  

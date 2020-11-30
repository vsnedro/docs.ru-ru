---
title: Практическое руководство. Перечисление хранилищ для изолированного хранилища
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
ms.openlocfilehash: f01ca70b3fd5b778274ef5bd7fcb63e26d9916a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734651"
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a>Практическое руководство. Перечисление хранилищ для изолированного хранилища

Перечислить все изолированные хранилища для текущего пользователя можно с помощью статического метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType>. Этот метод принимает значение <xref:System.IO.IsolatedStorage.IsolatedStorageScope> и возвращает перечислитель <xref:System.IO.IsolatedStorage.IsolatedStorageFile>. Чтобы перечислить хранилища, вам нужно разрешение <xref:System.Security.Permissions.IsolatedStorageFilePermission>, которое указывает значение <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser>. При вызове метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> со значением <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> он возвращает массив объектов <xref:System.IO.IsolatedStorage.IsolatedStorageFile>, определенных для текущего пользователя.  
  
## <a name="example"></a>Пример  

 Следующий пример кода получает хранилище, изолированное по пользователю и сборке, создает в нем несколько файлов и извлекает эти файлы с помощью метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [Изолированное хранилище](isolated-storage.md)

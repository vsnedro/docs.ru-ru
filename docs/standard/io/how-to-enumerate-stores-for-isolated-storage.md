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
ms.openlocfilehash: 9c7163dda34f254320ab7da86856d8731cd39426
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830770"
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a><span data-ttu-id="daba8-102">Практическое руководство. Перечисление хранилищ для изолированного хранилища</span><span class="sxs-lookup"><span data-stu-id="daba8-102">How to: Enumerate Stores for Isolated Storage</span></span>
<span data-ttu-id="daba8-103">Перечислить все изолированные хранилища для текущего пользователя можно с помощью статического метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="daba8-103">You can enumerate all isolated stores for the current user by using the  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> static method.</span></span> <span data-ttu-id="daba8-104">Этот метод принимает значение <xref:System.IO.IsolatedStorage.IsolatedStorageScope> и возвращает перечислитель <xref:System.IO.IsolatedStorage.IsolatedStorageFile>.</span><span class="sxs-lookup"><span data-stu-id="daba8-104">This  method takes an <xref:System.IO.IsolatedStorage.IsolatedStorageScope> value and returns an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> enumerator.</span></span> <span data-ttu-id="daba8-105">Чтобы перечислить хранилища, вам нужно разрешение <xref:System.Security.Permissions.IsolatedStorageFilePermission>, которое указывает значение <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser>.</span><span class="sxs-lookup"><span data-stu-id="daba8-105">To enumerate stores, you must have the <xref:System.Security.Permissions.IsolatedStorageFilePermission> permission that specifies the <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> value.</span></span> <span data-ttu-id="daba8-106">При вызове метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> со значением <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> он возвращает массив объектов <xref:System.IO.IsolatedStorage.IsolatedStorageFile>, определенных для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="daba8-106">If you call the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method with the <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> value, it returns an array of <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that are defined for the current user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daba8-107">Пример</span><span class="sxs-lookup"><span data-stu-id="daba8-107">Example</span></span>  
 <span data-ttu-id="daba8-108">Следующий пример кода получает хранилище, изолированное по пользователю и сборке, создает в нем несколько файлов и извлекает эти файлы с помощью метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="daba8-108">The following code example obtains a store that is isolated by user and assembly, creates a few files, and retrieves those files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="daba8-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="daba8-109">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [<span data-ttu-id="daba8-110">Изолированное хранилище</span><span class="sxs-lookup"><span data-stu-id="daba8-110">Isolated Storage</span></span>](isolated-storage.md)

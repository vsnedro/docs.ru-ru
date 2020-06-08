---
title: Практическое руководство. Удаление хранилищ из области изолированного хранения
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, deleting
- data stores, deleting
- deleting stores
- removing stores
- isolated storage, deleting stores
- storing data using isolated storage, deleting stores
- data storage using isolated storage, deleting stores
ms.assetid: 3947e333-5af6-4601-b2f1-24d4d6129cf3
ms.openlocfilehash: 885dc8e3ca0ea99de460cee7dd093b061f916388
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291894"
---
# <a name="how-to-delete-stores-in-isolated-storage"></a><span data-ttu-id="9bf85-102">Практическое руководство. Удаление хранилищ из области изолированного хранения</span><span class="sxs-lookup"><span data-stu-id="9bf85-102">How to: Delete Stores in Isolated Storage</span></span>
<span data-ttu-id="9bf85-103">Класс <xref:System.IO.IsolatedStorage.IsolatedStorageFile> предоставляет два метода для удаления файлов изолированного хранилища.</span><span class="sxs-lookup"><span data-stu-id="9bf85-103">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class supplies two methods for deleting isolated storage files:</span></span>  
  
- <span data-ttu-id="9bf85-104">Метод экземпляра <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> не требует аргументов и удаляет хранилище, которое его вызывает.</span><span class="sxs-lookup"><span data-stu-id="9bf85-104">The instance method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> does not take any arguments and deletes the store that calls it.</span></span> <span data-ttu-id="9bf85-105">Для данной операции не требуется никаких разрешений.</span><span class="sxs-lookup"><span data-stu-id="9bf85-105">No permissions are required for this operation.</span></span> <span data-ttu-id="9bf85-106">Код, имеющий доступ к хранилищу, может удалить данные внутри него полностью или выборочно.</span><span class="sxs-lookup"><span data-stu-id="9bf85-106">Any code that can access the store can delete any or all the data inside it.</span></span>  
  
- <span data-ttu-id="9bf85-107">Статический метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> принимает значение перечисления <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> и удаляет все хранилища пользователя, выполняющего этот код.</span><span class="sxs-lookup"><span data-stu-id="9bf85-107">The static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> takes the <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> enumeration value, and deletes all the stores for the user who is running the code.</span></span> <span data-ttu-id="9bf85-108">Для выполнения операции требуется разрешение <xref:System.Security.Permissions.IsolatedStorageFilePermission> для значения <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> .</span><span class="sxs-lookup"><span data-stu-id="9bf85-108">This operation requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> permission for the <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bf85-109">Пример</span><span class="sxs-lookup"><span data-stu-id="9bf85-109">Example</span></span>  
 <span data-ttu-id="9bf85-110">В следующем примере кода демонстрируется использование статических методов и методов экземпляра <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="9bf85-110">The following code example demonstrates the use of the static and instance <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> methods.</span></span> <span data-ttu-id="9bf85-111">Класс получает два хранилища: одно — изолированное по пользователю и сборке, другое — изолированное по пользователю, домену и сборке.</span><span class="sxs-lookup"><span data-stu-id="9bf85-111">The class obtains two stores; one is isolated for user and assembly and the other is isolated for user, domain, and assembly.</span></span> <span data-ttu-id="9bf85-112">Затем изолированное по пользователю, домену и сборке хранилище удаляется вызовом метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> файла изолированного хранилища  `isoStore1`.</span><span class="sxs-lookup"><span data-stu-id="9bf85-112">The user, domain, and assembly store is then deleted by calling the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> method of the isolated storage file  `isoStore1`.</span></span> <span data-ttu-id="9bf85-113">Далее вызовом статического метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>удаляются все оставшиеся хранилища пользователя.</span><span class="sxs-lookup"><span data-stu-id="9bf85-113">Then, all remaining stores for the user are deleted by calling the static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.IsolatedStorage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source3.cs#3)]
 [!code-vb[Conceptual.IsolatedStorage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9bf85-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9bf85-114">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [<span data-ttu-id="9bf85-115">Изолированное хранилище</span><span class="sxs-lookup"><span data-stu-id="9bf85-115">Isolated Storage</span></span>](isolated-storage.md)

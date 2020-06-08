---
title: Выполнение задач с My.Application, My.Computer и My.User
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 55961d6857b690fc2726f541df8a5497a3207928
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411698"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="8dce6-102">Выполнение задач с My.Application, My.Computer и My.User (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8dce6-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>

<span data-ttu-id="8dce6-103">Следующие три центральных объекта `My` предоставляют доступ к информации и часто используемым функциям: `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>) и `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span><span class="sxs-lookup"><span data-stu-id="8dce6-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="8dce6-104">Вы можете использовать эти объекты для доступа к информации, связанной с текущим приложением, с компьютером, на котором установлено это приложение, или с текущим пользователем этого приложения, соответственно.</span><span class="sxs-lookup"><span data-stu-id="8dce6-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="8dce6-105">My.Application, My.Computer и My.User</span><span class="sxs-lookup"><span data-stu-id="8dce6-105">My.Application, My.Computer, and My.User</span></span>  

 <span data-ttu-id="8dce6-106">В следующих примерах продемонстрировано извлечение информации с помощью `My`.</span><span class="sxs-lookup"><span data-stu-id="8dce6-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 <span data-ttu-id="8dce6-107">Помимо извлечения информации, предоставляемые этими тремя объектами элементы позволяют выполнять методы, связанные с этими объектами.</span><span class="sxs-lookup"><span data-stu-id="8dce6-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="8dce6-108">Например, с помощью `My.Computer` вы можете получить доступ к разным методам для управления файлами или изменения реестра.</span><span class="sxs-lookup"><span data-stu-id="8dce6-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="8dce6-109">Операции файлового ввода-вывода работают намного быстрее и проще с применением объекта `My`, который содержит разнообразные методы и свойства для управления файлами, каталогами и дисками.</span><span class="sxs-lookup"><span data-stu-id="8dce6-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="8dce6-110">Объект <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> позволяет считывать данные из крупных структурированных файлов с разделителями полей или полями фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="8dce6-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="8dce6-111">Код этого примера открывает `reader` `TextFieldParser` и применяет его для чтения данных из `C:\TestFolder1\test1.txt`.</span><span class="sxs-lookup"><span data-stu-id="8dce6-111">This example opens the `TextFieldParser` `reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 <span data-ttu-id="8dce6-112">`My.Application` позволяет изменить язык и региональные параметры для текущего приложения.</span><span class="sxs-lookup"><span data-stu-id="8dce6-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="8dce6-113">В следующем примере показано, как можно вызвать этот метод.</span><span class="sxs-lookup"><span data-stu-id="8dce6-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8dce6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8dce6-114">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [<span data-ttu-id="8dce6-115">Зависимость My от типа проекта</span><span class="sxs-lookup"><span data-stu-id="8dce6-115">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)

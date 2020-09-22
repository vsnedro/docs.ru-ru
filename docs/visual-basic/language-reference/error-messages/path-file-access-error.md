---
title: Ошибка доступа к пути к файлу
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 70de8f9cb33ab3d889f4916ae3d5de48cd218092
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871192"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="7b921-102">Ошибка доступа к пути/файлу</span><span class="sxs-lookup"><span data-stu-id="7b921-102">Path/File access error</span></span>

<span data-ttu-id="7b921-103">Во время операции доступа к файлу или диску операционная система не может установить соединение между путем и именем файла.</span><span class="sxs-lookup"><span data-stu-id="7b921-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7b921-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7b921-104">To correct this error</span></span>  
  
1. <span data-ttu-id="7b921-105">Убедитесь, что спецификация файла правильно отформатирована.</span><span class="sxs-lookup"><span data-stu-id="7b921-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="7b921-106">Имя файла может содержать полный (абсолютный) или относительный путь.</span><span class="sxs-lookup"><span data-stu-id="7b921-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="7b921-107">Полный путь начинается с имени диска (если путь находится на другом диске) и содержит явный путь от корня к файлу.</span><span class="sxs-lookup"><span data-stu-id="7b921-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="7b921-108">Любой путь, который не является полным, указывается относительно текущего диска и каталога.</span><span class="sxs-lookup"><span data-stu-id="7b921-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2. <span data-ttu-id="7b921-109">Убедитесь, что не предпринималась попытка сохранить файл, который заменит существующий файл, который доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7b921-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="7b921-110">В этом случае измените атрибут "только для чтения" целевого файла или сохраните файл с другим именем.</span><span class="sxs-lookup"><span data-stu-id="7b921-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3. <span data-ttu-id="7b921-111">Убедитесь, что вы не попытались открывать файл, доступный только для чтения, в последовательном `Output` или `Append` режиме.</span><span class="sxs-lookup"><span data-stu-id="7b921-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="7b921-112">В этом случае откройте файл в `Input` режиме или измените атрибут "только для чтения" файла.</span><span class="sxs-lookup"><span data-stu-id="7b921-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4. <span data-ttu-id="7b921-113">Убедитесь, что вы не попытались изменить проект Visual Basic в базе данных или документе.</span><span class="sxs-lookup"><span data-stu-id="7b921-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b921-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7b921-114">See also</span></span>

- [<span data-ttu-id="7b921-115">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="7b921-115">Error Types</span></span>](../../programming-guide/language-features/error-types.md)

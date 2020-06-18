---
title: 'Как выполнить: Написание параметров пользователя во время выполнения с помощью C#'
description: Сведения о записи параметров во время выполнения с помощью C# путем сохранения изменений параметров между сеансами приложения путем вызова метода Save.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 6154ff1b92d6c2d4c788299e59eb8f73e6b69c4b
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904329"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="89541-103">Руководство. запись параметров пользователя во время выполнения с помощью C\#</span><span class="sxs-lookup"><span data-stu-id="89541-103">How To: Write User Settings at Run Time with C\#</span></span>

<span data-ttu-id="89541-104">Параметры с областью действия приложения доступны только для чтения. Их можно изменить только во время разработки или путем изменения CONFIG-файла между сеансами приложения.</span><span class="sxs-lookup"><span data-stu-id="89541-104">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="89541-105">Параметры, имеющие область действия пользователя, однако, можно записывать во время выполнения так же, как значение любого свойства.</span><span class="sxs-lookup"><span data-stu-id="89541-105">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="89541-106">Новое значение сохраняется в течение всего сеанса приложения.</span><span class="sxs-lookup"><span data-stu-id="89541-106">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="89541-107">Для сохранения изменений параметров между сеансами приложения вызовите метод Save.</span><span class="sxs-lookup"><span data-stu-id="89541-107">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="89541-108">Практические руководства. запись и сохранение пользовательских параметров во время выполнения с помощью C\#</span><span class="sxs-lookup"><span data-stu-id="89541-108">How To: Write and Persist User Settings at Run Time with C\#</span></span>
  
1. <span data-ttu-id="89541-109">Получите доступ к параметру и присвойте ему новое значение, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="89541-109">Access the setting and assign it a new value as shown in this example:</span></span>  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. <span data-ttu-id="89541-110">Если необходимо сохранять изменения параметров между сеансами приложения, вызовите метод Save, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="89541-110">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
<span data-ttu-id="89541-111">Параметры пользователя сохраняются в файле в папке, вложенной в скрытую локальную папку данных приложения.</span><span class="sxs-lookup"><span data-stu-id="89541-111">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89541-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="89541-112">See also</span></span>

- [<span data-ttu-id="89541-113">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="89541-113">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="89541-114">Как выполнить: Считывание параметров во время выполнения с помощью C#</span><span class="sxs-lookup"><span data-stu-id="89541-114">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="89541-115">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="89541-115">Application Settings Overview</span></span>](application-settings-overview.md)

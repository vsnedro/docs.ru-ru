---
ms.service: multiple
ms.date: 9/20/2018
ms.topic: include
ms.openlocfilehash: bfa7bcefff45bc325d7bba3aa2b9b3a8f0d439fa
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433160"
---
<span data-ttu-id="2759e-101">Создайте текстовый файл с именем `azureauth.json`.</span><span class="sxs-lookup"><span data-stu-id="2759e-101">Create a text file named `azureauth.json`.</span></span> <span data-ttu-id="2759e-102">При создании субъекта-службы вставьте выходные данные JSON.</span><span class="sxs-lookup"><span data-stu-id="2759e-102">Paste the JSON output from when you created the service principal.</span></span>

<span data-ttu-id="2759e-103">Сохраните этот файл в безопасном расположении в вашей системе, доступном для кода.</span><span class="sxs-lookup"><span data-stu-id="2759e-103">Save this file in a secure location on your system where your code can read it.</span></span> <span data-ttu-id="2759e-104">При помощи PowerShell установите переменную среды с именем `AZURE_AUTH_LOCATION` и указанием полного пути к файлу, например:</span><span class="sxs-lookup"><span data-stu-id="2759e-104">Use PowerShell to set an environment variable named `AZURE_AUTH_LOCATION` with the full path to the file, for example:</span></span>

```powershell
[Environment]::SetEnvironmentVariable("AZURE_AUTH_LOCATION", "C:\src\azureauth.json", "User")
```

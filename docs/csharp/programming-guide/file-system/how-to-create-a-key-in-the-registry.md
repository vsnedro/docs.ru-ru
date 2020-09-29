---
title: Руководство по программированию на C#. Как создать раздел в реестре
description: Сведения о создании раздела в реестре. Изучите пример кода, инструкции по компиляции и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: c51fa61aa4c501921d5c7ace99a8c5aaf7b29f58
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203921"
---
# <a name="how-to-create-a-key-in-the-registry-c-programming-guide"></a><span data-ttu-id="8e5dd-104">Руководство по программированию на C#. Создание раздела в реестре</span><span class="sxs-lookup"><span data-stu-id="8e5dd-104">How to create a key in the registry (C# Programming Guide)</span></span>

<span data-ttu-id="8e5dd-105">Код в этом примере добавляет в раздел Names реестра текущего пользователя пару значений — Name и Isabella.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-105">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e5dd-106">Пример</span><span class="sxs-lookup"><span data-stu-id="8e5dd-106">Example</span></span>  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e5dd-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="8e5dd-107">Compiling the Code</span></span>  
  
- <span data-ttu-id="8e5dd-108">Скопируйте код и вставьте его в метод `Main` консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-108">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
- <span data-ttu-id="8e5dd-109">Замените параметр `Names` на имя ключа, который находится прямо в узле HKEY_CURRENT_USER реестра.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-109">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
- <span data-ttu-id="8e5dd-110">Замените параметр `Name` на имя значения, которое находится прямо в узле Names.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-110">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8e5dd-111">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="8e5dd-111">Robust Programming</span></span>  

 <span data-ttu-id="8e5dd-112">Проверьте структуру реестра и найдите подходящее место для ключа.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-112">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="8e5dd-113">Для этого можно, например, открыть ключ программного обеспечения текущего пользователя и создать ключ с названием вашей компании.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-113">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="8e5dd-114">Затем добавьте в ключ компании значения реестра.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-114">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="8e5dd-115">При следующих условиях может возникнуть исключение:</span><span class="sxs-lookup"><span data-stu-id="8e5dd-115">The following conditions might cause an exception:</span></span>  
  
- <span data-ttu-id="8e5dd-116">Пустое имя ключа.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-116">The name of the key is null.</span></span>  
  
- <span data-ttu-id="8e5dd-117">У пользователя нет разрешения на создание разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-117">The user does not have permissions to create registry keys.</span></span>  
  
- <span data-ttu-id="8e5dd-118">Имя ключа превышает ограничение в 255 символов.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-118">The key name exceeds the 255-character limit.</span></span>  
  
- <span data-ttu-id="8e5dd-119">Раздел является закрытым.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-119">The key is closed.</span></span>  
  
- <span data-ttu-id="8e5dd-120">Раздел реестра доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-120">The registry key is read-only.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="8e5dd-121">Безопасность .NET</span><span class="sxs-lookup"><span data-stu-id="8e5dd-121">.NET Security</span></span>  

 <span data-ttu-id="8e5dd-122">Безопаснее записывать данные в папку пользователя (`Microsoft.Win32.Registry.CurrentUser`), чем на локальный компьютер (`Microsoft.Win32.Registry.LocalMachine`).</span><span class="sxs-lookup"><span data-stu-id="8e5dd-122">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="8e5dd-123">Создавая значение реестра, необходимо решить, что делать, если это значение уже существует.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-123">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="8e5dd-124">Другой процесс (возможно, вредоносный) мог уже создать это значение и получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-124">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="8e5dd-125">Данные, добавленные в значение реестра, становятся доступными для другого процесса.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-125">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="8e5dd-126">Чтобы этого избежать, используйте `Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="8e5dd-126">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="8e5dd-127">метод.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-127">method.</span></span> <span data-ttu-id="8e5dd-128">Он возвращает значение NULL, если раздел еще не существует.</span><span class="sxs-lookup"><span data-stu-id="8e5dd-128">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="8e5dd-129">Небезопасно хранить секретные данные (например, пароли) в реестре как обычный текст, даже если раздел реестра защищен с помощью списков управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="8e5dd-129">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5dd-130">См. также</span><span class="sxs-lookup"><span data-stu-id="8e5dd-130">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="8e5dd-131">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8e5dd-131">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8e5dd-132">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="8e5dd-132">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="8e5dd-133">Чтение, запись и удаление данных реестра с помощью C#</span><span class="sxs-lookup"><span data-stu-id="8e5dd-133">Read, write and delete from the registry with C#</span></span>](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)

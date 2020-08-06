---
title: Руководство по программированию на C#. Как создать раздел в реестре
description: Сведения о создании раздела в реестре. Изучите пример кода, инструкции по компиляции и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: 6db076bc22e098c285b74a8c10e8b5f456c2c55e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299985"
---
# <a name="how-to-create-a-key-in-the-registry-c-programming-guide"></a><span data-ttu-id="73bdc-104">Руководство по программированию на C#. Создание раздела в реестре</span><span class="sxs-lookup"><span data-stu-id="73bdc-104">How to create a key in the registry (C# Programming Guide)</span></span>
<span data-ttu-id="73bdc-105">Код в этом примере добавляет в раздел Names реестра текущего пользователя пару значений — Name и Isabella.</span><span class="sxs-lookup"><span data-stu-id="73bdc-105">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="73bdc-106">Пример</span><span class="sxs-lookup"><span data-stu-id="73bdc-106">Example</span></span>  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73bdc-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="73bdc-107">Compiling the Code</span></span>  
  
- <span data-ttu-id="73bdc-108">Скопируйте код и вставьте его в метод `Main` консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="73bdc-108">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
- <span data-ttu-id="73bdc-109">Замените параметр `Names` на имя ключа, который находится прямо в узле HKEY_CURRENT_USER реестра.</span><span class="sxs-lookup"><span data-stu-id="73bdc-109">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
- <span data-ttu-id="73bdc-110">Замените параметр `Name` на имя значения, которое находится прямо в узле Names.</span><span class="sxs-lookup"><span data-stu-id="73bdc-110">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="73bdc-111">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="73bdc-111">Robust Programming</span></span>  
 <span data-ttu-id="73bdc-112">Проверьте структуру реестра и найдите подходящее место для ключа.</span><span class="sxs-lookup"><span data-stu-id="73bdc-112">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="73bdc-113">Для этого можно, например, открыть ключ программного обеспечения текущего пользователя и создать ключ с названием вашей компании.</span><span class="sxs-lookup"><span data-stu-id="73bdc-113">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="73bdc-114">Затем добавьте в ключ компании значения реестра.</span><span class="sxs-lookup"><span data-stu-id="73bdc-114">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="73bdc-115">При следующих условиях может возникнуть исключение:</span><span class="sxs-lookup"><span data-stu-id="73bdc-115">The following conditions might cause an exception:</span></span>  
  
- <span data-ttu-id="73bdc-116">Пустое имя ключа.</span><span class="sxs-lookup"><span data-stu-id="73bdc-116">The name of the key is null.</span></span>  
  
- <span data-ttu-id="73bdc-117">У пользователя нет разрешения на создание разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="73bdc-117">The user does not have permissions to create registry keys.</span></span>  
  
- <span data-ttu-id="73bdc-118">Имя ключа превышает ограничение в 255 символов.</span><span class="sxs-lookup"><span data-stu-id="73bdc-118">The key name exceeds the 255-character limit.</span></span>  
  
- <span data-ttu-id="73bdc-119">Раздел является закрытым.</span><span class="sxs-lookup"><span data-stu-id="73bdc-119">The key is closed.</span></span>  
  
- <span data-ttu-id="73bdc-120">Раздел реестра доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="73bdc-120">The registry key is read-only.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="73bdc-121">Безопасность .NET</span><span class="sxs-lookup"><span data-stu-id="73bdc-121">.NET Security</span></span>  
 <span data-ttu-id="73bdc-122">Безопаснее записывать данные в папку пользователя (`Microsoft.Win32.Registry.CurrentUser`), чем на локальный компьютер (`Microsoft.Win32.Registry.LocalMachine`).</span><span class="sxs-lookup"><span data-stu-id="73bdc-122">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="73bdc-123">Создавая значение реестра, необходимо решить, что делать, если это значение уже существует.</span><span class="sxs-lookup"><span data-stu-id="73bdc-123">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="73bdc-124">Другой процесс (возможно, вредоносный) мог уже создать это значение и получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="73bdc-124">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="73bdc-125">Данные, добавленные в значение реестра, становятся доступными для другого процесса.</span><span class="sxs-lookup"><span data-stu-id="73bdc-125">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="73bdc-126">Чтобы этого избежать, используйте `Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="73bdc-126">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="73bdc-127">метод.</span><span class="sxs-lookup"><span data-stu-id="73bdc-127">method.</span></span> <span data-ttu-id="73bdc-128">Он возвращает значение NULL, если раздел еще не существует.</span><span class="sxs-lookup"><span data-stu-id="73bdc-128">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="73bdc-129">Небезопасно хранить секретные данные (например, пароли) в реестре как обычный текст, даже если раздел реестра защищен с помощью списков управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="73bdc-129">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73bdc-130">См. также</span><span class="sxs-lookup"><span data-stu-id="73bdc-130">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="73bdc-131">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="73bdc-131">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="73bdc-132">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="73bdc-132">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="73bdc-133">Чтение, запись и удаление данных реестра с помощью C#</span><span class="sxs-lookup"><span data-stu-id="73bdc-133">Read, write and delete from the registry with C#</span></span>](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)

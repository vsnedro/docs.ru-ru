---
title: Практическое руководство. Использование защиты данных
description: Узнайте, как использовать защиту данных путем доступа к API защиты данных (DPAPI) в .NET.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET], data protection API
- data [.NET], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET], data protection API
- data protection API [.NET]
- decryption
- data [.NET], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: 263a07ddf357734e819fffdd41cdff60657adf15
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557064"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="95f5e-103">Практическое руководство. Использование защиты данных</span><span class="sxs-lookup"><span data-stu-id="95f5e-103">How to: Use Data Protection</span></span>

> [!NOTE]
> <span data-ttu-id="95f5e-104">Эта статья относится к Windows.</span><span class="sxs-lookup"><span data-stu-id="95f5e-104">This article applies to Windows.</span></span>
>
> <span data-ttu-id="95f5e-105">Дополнительные сведения о ASP.NET Core см. в разделе [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="95f5e-105">For information about ASP.NET Core, see [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).</span></span>

<span data-ttu-id="95f5e-106">.NET предоставляет доступ к API защиты данных (DPAPI), который позволяет шифровать данные с помощью информации из текущей учетной записи пользователя или компьютера.</span><span class="sxs-lookup"><span data-stu-id="95f5e-106">.NET provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="95f5e-107">Использование API защиты данных позволяет упростить сложную задачу явного создания и хранения криптографического ключа.</span><span class="sxs-lookup"><span data-stu-id="95f5e-107">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
<span data-ttu-id="95f5e-108">Используйте класс <xref:System.Security.Cryptography.ProtectedData> для шифрования копии массива байтов.</span><span class="sxs-lookup"><span data-stu-id="95f5e-108">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="95f5e-109">Эта функция доступна в .NET Framework, .NET Core и .NET 5.</span><span class="sxs-lookup"><span data-stu-id="95f5e-109">This functionality is available in .NET Framework, .NET Core, and .NET 5.</span></span>  <span data-ttu-id="95f5e-110">Можно указать, что данные, зашифрованные текущей учетной записью пользователя, могут быть расшифрованы только той же учетной записью, либо можно указать, что данные, зашифрованные текущей учетной записью пользователя, могут быть расшифрованы любой учетной записью на компьютере.</span><span class="sxs-lookup"><span data-stu-id="95f5e-110">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="95f5e-111">Подробное описание параметров <xref:System.Security.Cryptography.ProtectedData> см. в разделе, посвященном перечислению <xref:System.Security.Cryptography.DataProtectionScope>.</span><span class="sxs-lookup"><span data-stu-id="95f5e-111">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="95f5e-112">Шифрование данных в файл или поток при помощи функции защиты данных</span><span class="sxs-lookup"><span data-stu-id="95f5e-112">To encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="95f5e-113">Создайте случайную энтропию.</span><span class="sxs-lookup"><span data-stu-id="95f5e-113">Create random entropy.</span></span>  
  
2. <span data-ttu-id="95f5e-114">Вызовите статический метод <xref:System.Security.Cryptography.ProtectedData.Protect%2A> во время передачи массива байтов для шифрования, энтропии и области защиты данных.</span><span class="sxs-lookup"><span data-stu-id="95f5e-114">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="95f5e-115">Запишите зашифрованные данные в файл или поток.</span><span class="sxs-lookup"><span data-stu-id="95f5e-115">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="95f5e-116">Расшифровка данных из файла или потока при помощи функции защиты данных</span><span class="sxs-lookup"><span data-stu-id="95f5e-116">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="95f5e-117">Считайте зашифрованные данные из файла или потока.</span><span class="sxs-lookup"><span data-stu-id="95f5e-117">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="95f5e-118">Вызовите статический метод <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> во время передачи массива байтов для расшифровки и области защиты данных.</span><span class="sxs-lookup"><span data-stu-id="95f5e-118">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95f5e-119">Пример</span><span class="sxs-lookup"><span data-stu-id="95f5e-119">Example</span></span>

<span data-ttu-id="95f5e-120">В следующем примере кода показаны два вида шифрования и расшифровки.</span><span class="sxs-lookup"><span data-stu-id="95f5e-120">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="95f5e-121">Сначала пример кода выполняет шифрование и расшифровку массива байтов в памяти.</span><span class="sxs-lookup"><span data-stu-id="95f5e-121">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="95f5e-122">Далее этот пример кода шифрует копию массива байтов, сохраняет его в файл, загружает данные обратно из файла и затем расшифровывает эти данные.</span><span class="sxs-lookup"><span data-stu-id="95f5e-122">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="95f5e-123">В примере отображаются исходные данные, зашифрованные данные и расшифрованные данные.</span><span class="sxs-lookup"><span data-stu-id="95f5e-123">The example displays the original data, the encrypted data, and the decrypted data.</span></span>

[!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
[!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="95f5e-124">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="95f5e-124">Compiling the Code</span></span>  

<span data-ttu-id="95f5e-125">Этот пример компилируется и выполняется только при нацеливании на .NET Framework и выполняется в Windows.</span><span class="sxs-lookup"><span data-stu-id="95f5e-125">This example compiles and runs only when targeting .NET Framework and running on Windows.</span></span>

- <span data-ttu-id="95f5e-126">Включите ссылку на `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="95f5e-126">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="95f5e-127">Включите пространство имен <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> и <xref:System.Text>.</span><span class="sxs-lookup"><span data-stu-id="95f5e-127">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f5e-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="95f5e-128">See also</span></span>

- [<span data-ttu-id="95f5e-129">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="95f5e-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="95f5e-130">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="95f5e-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="95f5e-131">Кросс-платформенная криптография</span><span class="sxs-lookup"><span data-stu-id="95f5e-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
- [<span data-ttu-id="95f5e-132">ASP.NET Core Защита данных</span><span class="sxs-lookup"><span data-stu-id="95f5e-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)

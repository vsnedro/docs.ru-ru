---
title: Практическое руководство. Использование защиты данных
description: Узнайте, как использовать защиту данных путем доступа к API защиты данных (DPAPI) в .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: c7f88105727dfd33c87a815054aa317ac2052e83
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598597"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="999a4-103">Практическое руководство. Использование защиты данных</span><span class="sxs-lookup"><span data-stu-id="999a4-103">How to: Use Data Protection</span></span>
<span data-ttu-id="999a4-104">Платформа .NET Framework предоставляет доступ к API защиты данных (DPAPI), который позволяет шифровать данные, используя сведения из текущей учетной записи пользователя или с текущего компьютера.</span><span class="sxs-lookup"><span data-stu-id="999a4-104">The .NET Framework provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="999a4-105">Использование API защиты данных позволяет упростить сложную задачу явного создания и хранения криптографического ключа.</span><span class="sxs-lookup"><span data-stu-id="999a4-105">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
 <span data-ttu-id="999a4-106">Используйте класс <xref:System.Security.Cryptography.ProtectedMemory> для шифрования массива байтов в памяти.</span><span class="sxs-lookup"><span data-stu-id="999a4-106">Use the <xref:System.Security.Cryptography.ProtectedMemory> class to encrypt an array of in-memory bytes.</span></span>  <span data-ttu-id="999a4-107">Эта функциональность доступна в операционных системах Microsoft Windows XP и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="999a4-107">This functionality is available in Microsoft Windows XP and later operating systems.</span></span>  <span data-ttu-id="999a4-108">Можно указать, что память, зашифрованная текущим процессом, может быть расшифрована только текущим процессом, всеми процессами либо из того же контекста пользователя.</span><span class="sxs-lookup"><span data-stu-id="999a4-108">You can specify that memory encrypted by the current process can be decrypted by the current process only, by all processes, or from the same user context.</span></span>  <span data-ttu-id="999a4-109">Подробное описание параметров <xref:System.Security.Cryptography.ProtectedMemory> см. в разделе, посвященном перечислению <xref:System.Security.Cryptography.MemoryProtectionScope>.</span><span class="sxs-lookup"><span data-stu-id="999a4-109">See the <xref:System.Security.Cryptography.MemoryProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedMemory> options.</span></span>  
  
 <span data-ttu-id="999a4-110">Используйте класс <xref:System.Security.Cryptography.ProtectedData> для шифрования копии массива байтов.</span><span class="sxs-lookup"><span data-stu-id="999a4-110">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="999a4-111">Эта функциональность доступна в операционных системах Microsoft Windows 2000 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="999a4-111">This functionality is available in Microsoft Windows 2000 and later operating systems.</span></span>  <span data-ttu-id="999a4-112">Можно указать, что данные, зашифрованные текущей учетной записью пользователя, могут быть расшифрованы только той же учетной записью, либо можно указать, что данные, зашифрованные текущей учетной записью пользователя, могут быть расшифрованы любой учетной записью на компьютере.</span><span class="sxs-lookup"><span data-stu-id="999a4-112">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="999a4-113">Подробное описание параметров <xref:System.Security.Cryptography.ProtectedData> см. в разделе, посвященном перечислению <xref:System.Security.Cryptography.DataProtectionScope>.</span><span class="sxs-lookup"><span data-stu-id="999a4-113">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="999a4-114">Шифрование данных в памяти при помощи функции защиты данных</span><span class="sxs-lookup"><span data-stu-id="999a4-114">To encrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="999a4-115">Вызовите статический метод <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> во время передачи массива байтов для шифрования, энтропии и области защиты памяти.</span><span class="sxs-lookup"><span data-stu-id="999a4-115">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the memory protection scope.</span></span>  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="999a4-116">Расшифровка данных в памяти при помощи функции защиты данных</span><span class="sxs-lookup"><span data-stu-id="999a4-116">To decrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="999a4-117">Вызовите статический метод <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> во время передачи массива байтов для расшифровки и области защиты памяти.</span><span class="sxs-lookup"><span data-stu-id="999a4-117">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> method while passing an array of bytes to decrypt and the memory protection scope.</span></span>  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="999a4-118">Шифрование данных в файл или поток при помощи функции защиты данных</span><span class="sxs-lookup"><span data-stu-id="999a4-118">To encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="999a4-119">Создайте случайную энтропию.</span><span class="sxs-lookup"><span data-stu-id="999a4-119">Create random entropy.</span></span>  
  
2. <span data-ttu-id="999a4-120">Вызовите статический метод <xref:System.Security.Cryptography.ProtectedData.Protect%2A> во время передачи массива байтов для шифрования, энтропии и области защиты данных.</span><span class="sxs-lookup"><span data-stu-id="999a4-120">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="999a4-121">Запишите зашифрованные данные в файл или поток.</span><span class="sxs-lookup"><span data-stu-id="999a4-121">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="999a4-122">Расшифровка данных из файла или потока при помощи функции защиты данных</span><span class="sxs-lookup"><span data-stu-id="999a4-122">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="999a4-123">Считайте зашифрованные данные из файла или потока.</span><span class="sxs-lookup"><span data-stu-id="999a4-123">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="999a4-124">Вызовите статический метод <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> во время передачи массива байтов для расшифровки и области защиты данных.</span><span class="sxs-lookup"><span data-stu-id="999a4-124">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="999a4-125">Пример</span><span class="sxs-lookup"><span data-stu-id="999a4-125">Example</span></span>  
 <span data-ttu-id="999a4-126">В следующем примере кода показаны два вида шифрования и расшифровки.</span><span class="sxs-lookup"><span data-stu-id="999a4-126">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="999a4-127">Сначала пример кода выполняет шифрование и расшифровку массива байтов в памяти.</span><span class="sxs-lookup"><span data-stu-id="999a4-127">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="999a4-128">Далее этот пример кода шифрует копию массива байтов, сохраняет его в файл, загружает данные обратно из файла и затем расшифровывает эти данные.</span><span class="sxs-lookup"><span data-stu-id="999a4-128">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="999a4-129">В примере отображаются исходные данные, зашифрованные данные и расшифрованные данные.</span><span class="sxs-lookup"><span data-stu-id="999a4-129">The example displays the original data, the encrypted data, and the decrypted data.</span></span>  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="999a4-130">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="999a4-130">Compiling the Code</span></span>  
  
- <span data-ttu-id="999a4-131">Включите ссылку на `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="999a4-131">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="999a4-132">Включите пространство имен <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> и <xref:System.Text>.</span><span class="sxs-lookup"><span data-stu-id="999a4-132">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="999a4-133">См. также</span><span class="sxs-lookup"><span data-stu-id="999a4-133">See also</span></span>

- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>

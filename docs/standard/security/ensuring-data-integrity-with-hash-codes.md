---
title: Обеспечение целостности данных с помощью хэш-кодов
description: Узнайте, как обеспечить целостность данных с помощью хэш-кодов в .NET. Хэш-код является численным значением фиксированной длины, которое однозначно идентифицирует данные.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET], hash
- data integrity
- checking hash codes
- encryption [.NET], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
ms.openlocfilehash: 085a0ea387e3415e6e916bcdf9055ffaa6753fef
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831095"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="e74da-104">Обеспечение целостности данных с помощью хэш-кодов</span><span class="sxs-lookup"><span data-stu-id="e74da-104">Ensuring Data Integrity with Hash Codes</span></span>
<span data-ttu-id="e74da-105">Хэш-код является численным значением фиксированной длины, которое однозначно идентифицирует данные.</span><span class="sxs-lookup"><span data-stu-id="e74da-105">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="e74da-106">Хэш-коды представляют большие объемы данных в виде намного меньших по объему числовых значений, поэтому они используются с цифровыми подписями.</span><span class="sxs-lookup"><span data-stu-id="e74da-106">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="e74da-107">Хэш-код можно подписать более эффективно, чем значение большего размера.</span><span class="sxs-lookup"><span data-stu-id="e74da-107">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="e74da-108">Хэш-коды также могут использоваться для проверки целостности данных, пересылаемых по незащищенным каналам.</span><span class="sxs-lookup"><span data-stu-id="e74da-108">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="e74da-109">Хэш-код полученных данных можно сравнить с хэш-кодом этих же данных, вычисленным перед их передачей, и на основании этого определить, подвергались ли данные изменениям.</span><span class="sxs-lookup"><span data-stu-id="e74da-109">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
<span data-ttu-id="e74da-110">В этом разделе описываются способы создания и проверки хэш-кодов с помощью классов пространства имен <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="e74da-110">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="e74da-111">Создание хэша</span><span class="sxs-lookup"><span data-stu-id="e74da-111">Generating a Hash</span></span>

 <span data-ttu-id="e74da-112">Управляемые классы, реализующие хэширование, можно использовать для хэширования либо байтового массива, либо управляемого объекта потока.</span><span class="sxs-lookup"><span data-stu-id="e74da-112">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="e74da-113">В примере ниже хэш-алгоритм SHA1 используется для создания хэш-кода строки.</span><span class="sxs-lookup"><span data-stu-id="e74da-113">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="e74da-114">В примере класс <xref:System.Text.UnicodeEncoding> используется для преобразования строки в массив байтов, которые хэшируются с помощью класса <xref:System.Security.Cryptography.SHA256>.</span><span class="sxs-lookup"><span data-stu-id="e74da-114">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA256> class.</span></span> <span data-ttu-id="e74da-115">После этого хэш-код выводится на консоль.</span><span class="sxs-lookup"><span data-stu-id="e74da-115">The hash value is then displayed to the console.</span></span>  

 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="e74da-116">Этот код выводит на консоль следующую строку:</span><span class="sxs-lookup"><span data-stu-id="e74da-116">This code will display the following string to the console:</span></span>  
  
 `185 203 236 22 3 228 27 130 87 23 244 15 87 88 14 43 37 61 106 224 81 172 224 211 104 85 194 197 194 25 120 217`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="e74da-117">Проверка хэша</span><span class="sxs-lookup"><span data-stu-id="e74da-117">Verifying a Hash</span></span>

 <span data-ttu-id="e74da-118">Проверку целостности данных можно производить на основании сравнения их с хэш-кодом.</span><span class="sxs-lookup"><span data-stu-id="e74da-118">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="e74da-119">Обычно данные хэшируются в некоторый момент времени, а затем их хэш-код защищается каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="e74da-119">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="e74da-120">Позже можно снова хэшировать эти данные и результат сравнивать с защищенным хэш-кодом.</span><span class="sxs-lookup"><span data-stu-id="e74da-120">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="e74da-121">Если хэш-коды совпадают, значит, данные не изменялись.</span><span class="sxs-lookup"><span data-stu-id="e74da-121">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="e74da-122">Несовпадение хэш-кодов свидетельствует о том, что данные были повреждены.</span><span class="sxs-lookup"><span data-stu-id="e74da-122">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="e74da-123">Чтобы такой механизм был работоспособен, защищенный хэш должен быть зашифрован или являться недоступным для всех лиц, не имеющих достаточного доверия.</span><span class="sxs-lookup"><span data-stu-id="e74da-123">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="e74da-124">В примере ниже ранее полученный хэш-код строки сравнивается с ее новым хэш-кодом.</span><span class="sxs-lookup"><span data-stu-id="e74da-124">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="e74da-125">В этом примере реализован цикл, производящий побайтовое сравнение хэш-кодов.</span><span class="sxs-lookup"><span data-stu-id="e74da-125">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="e74da-126">Если хэш-коды совпадают, этот код выводит на консоль следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="e74da-126">If the two hash values match, this code displays the following to the console:</span></span>  
  
```console  
The hash codes match.  
```  
  
 <span data-ttu-id="e74da-127">В противном случае на консоль выводится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="e74da-127">If they do not match, the code displays the following:</span></span>  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="e74da-128">См. также статью</span><span class="sxs-lookup"><span data-stu-id="e74da-128">See also</span></span>

- [<span data-ttu-id="e74da-129">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="e74da-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="e74da-130">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="e74da-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="e74da-131">Кросс-платформенная криптография</span><span class="sxs-lookup"><span data-stu-id="e74da-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="e74da-132">ASP.NET Core Защита данных</span><span class="sxs-lookup"><span data-stu-id="e74da-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)

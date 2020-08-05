---
title: Практическое руководство. Подписание XML-документов с помощью цифровых подписей
description: Узнайте, как подписывать XML-документы с помощью цифровых подписей. Используйте классы в пространстве имен System.Security.Cryptography.Xml в .NET.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signatures, XML signing
- System.Security.Cryptography.SignedXml class
- digital signatures, XML signing
- System.Security.Cryptography.RSA class
- XML digital signatures
- XML signing
- signing XML
ms.assetid: 99692ac1-d8c9-42d7-b1bf-2737b01037e4
ms.openlocfilehash: e1457fd659ab63489bd4cfafd7731a4b098a2791
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557077"
---
# <a name="how-to-sign-xml-documents-with-digital-signatures"></a><span data-ttu-id="f8a08-104">Практическое руководство. Подписание XML-документов с помощью цифровых подписей</span><span class="sxs-lookup"><span data-stu-id="f8a08-104">How to: Sign XML Documents with Digital Signatures</span></span>

<span data-ttu-id="f8a08-105">Можно использовать классы в пространстве имен <xref:System.Security.Cryptography.Xml> для подписания XML-документа или его части при помощи цифровой подписи.</span><span class="sxs-lookup"><span data-stu-id="f8a08-105">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to sign an XML document or part of an XML document with a digital signature.</span></span>  <span data-ttu-id="f8a08-106">Цифровые подписи XML (XMLDSIG) позволяют убедиться, что данные не были изменены после подписания.</span><span class="sxs-lookup"><span data-stu-id="f8a08-106">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span>  <span data-ttu-id="f8a08-107">Дополнительные сведения о стандарте XMLDSIG см. в разделе рекомендации по [синтаксису XML-подписи](https://www.w3.org/TR/xmldsig-core/)консорциум W3C (W3C) и обработке.</span><span class="sxs-lookup"><span data-stu-id="f8a08-107">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8a08-108">Код, приведенный в этой статье, относится к Windows.</span><span class="sxs-lookup"><span data-stu-id="f8a08-108">The code in this article applies to Windows.</span></span>

<span data-ttu-id="f8a08-109">В примере кода в этой процедуре показано, как подписать весь XML-документ с помощью цифровой подписи и присоединить подпись к документу в `Signature` элементе <>.</span><span class="sxs-lookup"><span data-stu-id="f8a08-109">The code example in this procedure demonstrates how to digitally sign an entire XML document and attach the signature to the document in a <`Signature`> element.</span></span>  <span data-ttu-id="f8a08-110">Пример создает ключ подписывания RSA, добавляет его в безопасный контейнер ключей и затем использует этот ключ для создания цифровой подписи XML-документа.</span><span class="sxs-lookup"><span data-stu-id="f8a08-110">The example creates an RSA signing key, adds the key to a secure key container, and then uses the key to digitally sign an XML document.</span></span>  <span data-ttu-id="f8a08-111">Впоследствии ключ можно извлечь для проверки цифровой подписи XML либо использовать для подписывания другого XML-документа.</span><span class="sxs-lookup"><span data-stu-id="f8a08-111">The key can then be retrieved to verify the XML digital signature, or can be used to sign another XML document.</span></span>  
  
<span data-ttu-id="f8a08-112">Сведения о том, как проверить цифровую подпись XML, созданную с помощью этой процедуры, см. [в разделе как проверить цифровые подписи XML-документов](how-to-verify-the-digital-signatures-of-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="f8a08-112">For information about how to verify an XML digital signature that was created using this procedure, see [How to: Verify the Digital Signatures of XML Documents](how-to-verify-the-digital-signatures-of-xml-documents.md).</span></span>  
  
### <a name="to-digitally-sign-an-xml-document"></a><span data-ttu-id="f8a08-113">Создание цифровой подписи XML-документа</span><span class="sxs-lookup"><span data-stu-id="f8a08-113">To digitally sign an XML document</span></span>  
  
1. <span data-ttu-id="f8a08-114">Создайте объект <xref:System.Security.Cryptography.CspParameters> и укажите имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="f8a08-114">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToSignXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="f8a08-115">Создайте асимметричный ключ, используя класс <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="f8a08-115">Generate an asymmetric key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="f8a08-116">Этот ключ автоматически сохраняется в контейнер ключей при передаче объекта <xref:System.Security.Cryptography.CspParameters> в конструктор класса <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="f8a08-116">The key is automatically saved to the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="f8a08-117">Этот ключ будет использоваться для подписывания XML-документа.</span><span class="sxs-lookup"><span data-stu-id="f8a08-117">This key will be used to sign the XML document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToSignXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="f8a08-118">Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML-файл с диска.</span><span class="sxs-lookup"><span data-stu-id="f8a08-118">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="f8a08-119">Объект <xref:System.Xml.XmlDocument> содержит XML-элемент для шифрования.</span><span class="sxs-lookup"><span data-stu-id="f8a08-119">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToSignXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="f8a08-120">Создайте новый объект <xref:System.Security.Cryptography.Xml.SignedXml> и передайте в него объект <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="f8a08-120">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToSignXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="f8a08-121">Добавьте ключ подписывания RSA в объект <xref:System.Security.Cryptography.Xml.SignedXml>.</span><span class="sxs-lookup"><span data-stu-id="f8a08-121">Add the signing RSA key to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToSignXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="f8a08-122">Создайте объект <xref:System.Security.Cryptography.Xml.Reference>, определяющий, что именно требуется подписать.</span><span class="sxs-lookup"><span data-stu-id="f8a08-122">Create a <xref:System.Security.Cryptography.Xml.Reference> object that describes what to sign.</span></span>  <span data-ttu-id="f8a08-123">Чтобы подписать весь документ целиком, установите для свойства <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> значение `""`.</span><span class="sxs-lookup"><span data-stu-id="f8a08-123">To sign the entire document, set the <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> property to `""`.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToSignXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="f8a08-124">Добавьте объект <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> в объект <xref:System.Security.Cryptography.Xml.Reference>.</span><span class="sxs-lookup"><span data-stu-id="f8a08-124">Add an <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> object to the <xref:System.Security.Cryptography.Xml.Reference> object.</span></span>  <span data-ttu-id="f8a08-125">Преобразование позволяет проверяющему представить XML-данные в той же самой форме, которую использовал подписавший.</span><span class="sxs-lookup"><span data-stu-id="f8a08-125">A transformation allows the verifier to represent the XML data in the identical manner that the signer used.</span></span>  <span data-ttu-id="f8a08-126">XML-данные могут быть представлены различными способами, поэтому этот шаг крайне важен для выполнения проверки.</span><span class="sxs-lookup"><span data-stu-id="f8a08-126">XML data can be represented in different ways, so this step is vital to verification.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToSignXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#8)]  
  
8. <span data-ttu-id="f8a08-127">Добавьте объект <xref:System.Security.Cryptography.Xml.Reference> в объект <xref:System.Security.Cryptography.Xml.SignedXml>.</span><span class="sxs-lookup"><span data-stu-id="f8a08-127">Add the <xref:System.Security.Cryptography.Xml.Reference> object to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#9)]
     [!code-vb[HowToSignXMLDocumentRSA#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#9)]  
  
9. <span data-ttu-id="f8a08-128">Вычислите подпись, вызвав метод <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A>.</span><span class="sxs-lookup"><span data-stu-id="f8a08-128">Compute the signature by calling the <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A> method.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#10)]
     [!code-vb[HowToSignXMLDocumentRSA#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#10)]  
  
10. <span data-ttu-id="f8a08-129">Извлеките XML-представление сигнатуры ( `Signature` элемент> <) и сохраните его в новый <xref:System.Xml.XmlElement> объект.</span><span class="sxs-lookup"><span data-stu-id="f8a08-129">Retrieve the XML representation of the signature (a <`Signature`> element) and save it to a new <xref:System.Xml.XmlElement> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#11)]
     [!code-vb[HowToSignXMLDocumentRSA#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#11)]  
  
11. <span data-ttu-id="f8a08-130">Добавьте элемент в объект <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="f8a08-130">Append the element to the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#12)]
     [!code-vb[HowToSignXMLDocumentRSA#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#12)]  
  
12. <span data-ttu-id="f8a08-131">Сохраните документ.</span><span class="sxs-lookup"><span data-stu-id="f8a08-131">Save the document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#13)]
     [!code-vb[HowToSignXMLDocumentRSA#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="f8a08-132">Пример</span><span class="sxs-lookup"><span data-stu-id="f8a08-132">Example</span></span>  
 <span data-ttu-id="f8a08-133">В этом примере предполагается, что файл с именем `test.xml` существует в том же каталоге, что и скомпилированная программа.</span><span class="sxs-lookup"><span data-stu-id="f8a08-133">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="f8a08-134">Можно поместить следующий XML-код в файл с именем `test.xml` и использовать его вместе с данным примером.</span><span class="sxs-lookup"><span data-stu-id="f8a08-134">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToSignXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToSignXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8a08-135">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f8a08-135">Compiling the Code</span></span>  
  
- <span data-ttu-id="f8a08-136">В проекте, предназначенном для .NET Framework, включите ссылку на `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="f8a08-136">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="f8a08-137">В проекте, ориентированном на .NET Core или .NET 5, установите пакет NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="f8a08-137">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="f8a08-138">Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="f8a08-138">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="f8a08-139">Безопасность .NET</span><span class="sxs-lookup"><span data-stu-id="f8a08-139">.NET Security</span></span>

<span data-ttu-id="f8a08-140">Не следует хранить или передавать закрытый ключ из пары асимметричных ключей в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="f8a08-140">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="f8a08-141">Дополнительные сведения о симметричных и асимметричных криптографических ключах см. в разделе [Создание ключей для шифрования и расшифровки](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="f8a08-141">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
<span data-ttu-id="f8a08-142">Не следует внедрять закрытый ключ непосредственно в исходный код.</span><span class="sxs-lookup"><span data-stu-id="f8a08-142">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="f8a08-143">Внедренные ключи можно легко считывать из сборки с помощью [Ildasm.exe (IL)](../../framework/tools/ildasm-exe-il-disassembler.md) или путем открытия сборки в текстовом редакторе, например в блокноте.</span><span class="sxs-lookup"><span data-stu-id="f8a08-143">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a08-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f8a08-144">See also</span></span>

- [<span data-ttu-id="f8a08-145">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="f8a08-145">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="f8a08-146">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="f8a08-146">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="f8a08-147">Кросс-платформенная криптография</span><span class="sxs-lookup"><span data-stu-id="f8a08-147">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="f8a08-148">Практическое руководство. Проверка цифровых подписей XML-документов</span><span class="sxs-lookup"><span data-stu-id="f8a08-148">How to: Verify the Digital Signatures of XML Documents</span></span>](how-to-verify-the-digital-signatures-of-xml-documents.md)
- [<span data-ttu-id="f8a08-149">ASP.NET Core Защита данных</span><span class="sxs-lookup"><span data-stu-id="f8a08-149">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)

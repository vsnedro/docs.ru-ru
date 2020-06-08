---
title: Создание XML-документа
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
ms.openlocfilehash: 577d353a30c986d198140b4596ae1a7e199ddd6e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291985"
---
# <a name="xml-document-creation"></a><span data-ttu-id="d1a94-102">Создание XML-документа</span><span class="sxs-lookup"><span data-stu-id="d1a94-102">XML Document Creation</span></span>
<span data-ttu-id="d1a94-103">XML-документ можно создать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="d1a94-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="d1a94-104">Один из них заключается в создании объекта **XmlDocument** без параметров.</span><span class="sxs-lookup"><span data-stu-id="d1a94-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="d1a94-105">Второй включает создание объекта **XmlDocument**, которому нужно в качестве параметра передать XmlNameTable.</span><span class="sxs-lookup"><span data-stu-id="d1a94-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="d1a94-106">В следующем примере показано создание пустого объекта **XmlDocument** без параметров.</span><span class="sxs-lookup"><span data-stu-id="d1a94-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="d1a94-107">После создания документа в него можно с помощью метода **Load** загрузить данные из строки, потока, URL-адреса, текстового модуля чтения или класса, производного от **XmlReader**.</span><span class="sxs-lookup"><span data-stu-id="d1a94-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="d1a94-108">Есть еще один метод загрузки: **LoadXML**, который считывает XML из строки.</span><span class="sxs-lookup"><span data-stu-id="d1a94-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="d1a94-109">Дополнительные сведения о различных методах **Load** см. в статье [Считывание XML-документа в DOM](reading-an-xml-document-into-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="d1a94-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="d1a94-110">Существует класс с именем **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="d1a94-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="d1a94-111">Он является таблицей атомарных объектов строки.</span><span class="sxs-lookup"><span data-stu-id="d1a94-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="d1a94-112">Эта таблица предоставляет средству синтаксического анализа XML эффективный способ использовать один и тот же строковый объект для всех повторяющихся имен элементов и атрибутов в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="d1a94-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="d1a94-113">Класс **XmlNameTable** автоматически создается при создании документа, как показано выше, и заполняется именами элементов и атрибутов при загрузке этого документа.</span><span class="sxs-lookup"><span data-stu-id="d1a94-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="d1a94-114">Если у вас уже есть документ с таблицей имен и эти имена можно применить в другом документе, создайте новый документ с помощью метода **Load**, передав ему в качестве параметра таблицу **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="d1a94-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="d1a94-115">Когда документ создается с помощью этого метода, он использует существующую таблицу **XmlNameTable** со всеми атрибутами и элементами, ранее загруженными в нее из другого документа.</span><span class="sxs-lookup"><span data-stu-id="d1a94-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="d1a94-116">Это можно использовать для эффективного сравнения имен элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="d1a94-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="d1a94-117">Дополнительные сведения о классе **XmlNameTable** см. в таблице [Сравнение объектов с помощью XmlNameTable](object-comparison-using-xmlnametable.md).</span><span class="sxs-lookup"><span data-stu-id="d1a94-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="d1a94-118">Справочную информацию см. в статье <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="d1a94-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a94-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d1a94-119">See also</span></span>

- [<span data-ttu-id="d1a94-120">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="d1a94-120">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)

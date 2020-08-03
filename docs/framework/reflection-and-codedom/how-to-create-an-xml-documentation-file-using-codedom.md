---
title: Практическое руководство. Создание XML-файла документации с использованием CodeDOM
description: В этом подробном примере показано, как создать код, формирующий XML-файл документации, с помощью Code Document Object Model (CodeDOM).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CodeDOM, generating XML documentation
- XML documentation, creating using CodeDOM
- Code Document Object Model, generating XML documentation
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
ms.openlocfilehash: f905b996910c6cfbc62378cc4cd6bb8c0e0e6fd4
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865155"
---
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a>Практическое руководство. Создание XML-файла документации с использованием CodeDOM

CodeDOM можно использовать для создания кода, создающего XML-документацию. Этот процесс предполагает создание графа CodeDOM, содержащего комментарии XML-документации, создание кода, а также компиляцию созданного кода с параметром компилятора, при выборе которого в итоге создается XML-документация.  
  
## <a name="create-a-codedom-graph"></a>Создание графа CodeDOM
  
1. Создайте объект <xref:System.CodeDom.CodeCompileUnit>, содержащий граф CodeDOM для примера приложения.  
  
2. С помощью конструктора <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A>, параметру `docComment` которого задано значение `true`, создайте элементы и текст комментариев XML-документации.  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### <a name="generate-the-code-from-the-codecompileunit"></a>Создание кода на основе объекта CodeCompileUnit
  
1. С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> создайте код и исходный файл для компиляции.  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### <a name="compile-the-code-and-generate-the-documentation-file"></a>Компиляция кода и создание файла документации
  
1. Добавьте параметр компилятора **/doc** в свойство <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> объекта <xref:System.CodeDom.Compiler.CompilerParameters> и передайте объект в метод <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A>, чтобы создать файл XML-документации при компиляции кода.  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## <a name="example"></a>Пример

В следующем примере кода создается граф CodeDOM с комментариями документации, на основе этого графа создается файл кода, этот файл компилируется, а затем создается сопоставленный файл XML-документации.  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 В этом примере в файле *HelloWorldDoc.xml* создается следующая XML-документация.  
  
```xml  
<?xml version="1.0" ?>
<doc>  
  <assembly>  
    <name>HelloWorld</name>
  </assembly>  
  <members>  
    <member name="T:Samples.Class1">  
      <summary>  
        Create a Hello World application.
      </summary>
      <seealso cref="M:Samples.Class1.Main" />
    </member>  
    <member name="M:Samples.Class1.Main">  
      <summary>  
        Main method for HelloWorld application.
        <para>Add a new paragraph to the description.</para>
      </summary>  
    </member>  
  </members>  
</doc>  
```  
  
## <a name="compile-permissions"></a>Разрешения на компиляцию
  
Для выполнения этого кода должно быть установлено разрешение `FullTrust`.
  
## <a name="see-also"></a>См. также

- [Документирование кода с помощью XML (Visual Basic)](../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [Комментарии XML-документации](../../csharp/programming-guide/xmldoc/index.md)
- [XML-документация (C++)](/cpp/ide/xml-documentation-visual-cpp)

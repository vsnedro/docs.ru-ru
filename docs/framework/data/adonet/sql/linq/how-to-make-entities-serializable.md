---
title: Практическое руководство. Как обеспечить сериализации сущностей
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: f4528cab21ac678f5d06717d0ce6e7ff7e77d3e4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203505"
---
# <a name="how-to-make-entities-serializable"></a>Практическое руководство. Как обеспечить сериализации сущностей

Возможность сериализации сущностей можно обеспечить при создании кода. К классам сущностей добавляется атрибут <xref:System.Runtime.Serialization.DataContractAttribute>, а к столбцам - атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
 Разработчики, использующие Visual Studio, могут использовать реляционный конструктор объектов для этой цели.  
  
 При использовании программы командной строки SQLMetal используйте параметр **/Serialization** с `unidirectional` аргументом. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Пример  

 В следующих командах средства командной строки SQLMetal создают файлы, содержащие сериализуемые сущности.  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>См. также

- [Сериализация](serialization.md)
- [Создание модели объектов](creating-the-object-model.md)

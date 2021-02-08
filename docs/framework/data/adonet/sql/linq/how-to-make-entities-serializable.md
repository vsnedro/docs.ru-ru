---
description: Дополнительные сведения см. в статье как сделать сущности сериализуемыми.
title: Практическое руководство. Как обеспечить сериализации сущностей
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: cb2253d7933f3584543b4b030bc8b5aa3cc62921
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785943"
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

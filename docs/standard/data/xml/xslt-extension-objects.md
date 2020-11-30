---
title: Объекты расширения XSLT
ms.date: 03/30/2017
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
ms.openlocfilehash: 0e874bb7679854b75a07eb452e47eba0d30807a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720793"
---
# <a name="xslt-extension-objects"></a>Объекты расширения XSLT

Объекты расширения используются для расширения функциональности таблиц стилей. Объекты расширения обслуживаются классом <xref:System.Xml.Xsl.XsltArgumentList>.  
  
 Далее приведены преимущества использования объекта расширения в сравнении с внедренными скриптами.  
  
- Обеспечивает улучшенную инкапсуляцию и повторное использование классов.  
  
- Уменьшает размер и улучшает обслуживание таблиц стилей.  
  
 Объекты расширения XSLT добавляются в объект <xref:System.Xml.Xsl.XsltArgumentList> с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>. В это время с объектом расширения связываются полное имя и URI-код пространства имен.  
  
> [!NOTE]
> Чтобы вызвать метод <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>, необходим набор разрешений FullTrust. См. дополнительные сведения об [управлении доступом к коду](../../../framework/misc/code-access-security.md) и [именованных наборах разрешений](/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).  
  
 Объекты расширения возвращают один из четырех базовых типов данных XPath: `number`, `string`, `Boolean` и `node set`.  
  
 Любой метод, который определен с ключевым словом `params`, позволяющим передавать точно не установленное количество параметров, в настоящее время не поддерживается классом <xref:System.Xml.Xsl.XslCompiledTransform>. Таблицы стилей XSLT, которые используют любой метод, определенный с ключевым словом `params`, не будут работать правильно. Дополнительные сведения см. в руководстве по [params](../../../csharp/language-reference/keywords/params.md).  
  
### <a name="to-use-an-xslt-extension-object"></a>Использование объекта расширения XSLT  
  
1. Создайте объект <xref:System.Xml.Xsl.XsltArgumentList> и добавьте объект расширения с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.  
  
2. Вызовите объект расширения из таблицы стилей.  
  
3. Передайте объект <xref:System.Xml.Xsl.XsltArgumentList> методу <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
## <a name="see-also"></a>См. также

- [Преобразования XSLT](xslt-transformations.md)
- [Рекомендации по безопасности XSLT](xslt-security-considerations.md)

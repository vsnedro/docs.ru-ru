---
title: Разрешение внешних таблиц стилей XSLT и документов
ms.date: 03/30/2017
ms.assetid: 920cfe3b-d525-4bb2-abf6-9431651f9cf9
ms.openlocfilehash: f1fbf950f7d67d46937652987516e5faf9857b85
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686570"
---
# <a name="resolving-external-xslt-style-sheets-and-documents"></a>Разрешение внешних таблиц стилей XSLT и документов

В некоторых случаях в процессе преобразования может потребоваться разрешение внешних ресурсов.  
  
> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 В некоторых случаях в процессе преобразования может потребоваться разрешение внешних ресурсов.  
  
- При использовании метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, чтобы обнаружить внешнюю таблицу стилей.  
  
- При использовании метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, чтобы разрешить любые элементы `<xsl:include>` или `<xsl:import>`, обнаруженные в таблице стилей.  
  
- При использовании метода <xref:System.Xml.Xsl.XslTransform.Transform%2A>, чтобы разрешить любые функции `document()`.  
  
## <a name="using-the-xmlresolver-class"></a>Использование класса XmlResolver  

 Если для проверки подлинности требуется доступ к сетевому ресурсу, используйте методы <xref:System.Xml.Xsl.XslTransform.Load%2A> с параметром <xref:System.Xml.XmlResolver>, чтобы передать объект <xref:System.Xml.XmlResolver> с набором необходимых свойств учетных данных.  
  
 Если нужно использовать специальный класс <xref:System.Xml.XmlResolver> или указать другие учетные данные, то в следующей таблице приведен список необходимых задач, в зависимости от того, когда необходимо разрешить внешний ресурс.  
  
|Процесс, требующий разрешения|Необходимая задача|  
|--------------------------------------|-------------------|  
|При использовании метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, чтобы обнаружить таблицу стилей.|Указать перегруженный метод <xref:System.Xml.Xsl.XslTransform.Load%2A>, который принимает в качестве параметра объект <xref:System.Xml.XmlResolver>, если таблица стилей находится в ресурсе, требующем учетных данных.|  
|При использовании метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, чтобы разрешить элементы `<xsl:include>` или `<xsl:import>`.|Указать перегруженный метод <xref:System.Xml.Xsl.XslTransform.Load%2A>, который принимает в качестве параметра объект <xref:System.Xml.XmlResolver>. Объект <xref:System.Xml.XmlResolver> используется для загрузки таблиц стилей, на которые ссылаются инструкции `import` или `include`. Если передается значение `null`, то внешние ресурсы не разрешаются.|  
|При использовании преобразования для разрешения любых функций `document()`.|Укажите объект <xref:System.Xml.XmlResolver> при преобразовании с помощью метода <xref:System.Xml.Xsl.XslTransform.Transform%2A>, который принимает аргумент <xref:System.Xml.XmlResolver>.|  
  
 Функция `document()` получает другие XML-ресурсы из таблицы стилей, в дополнение к начальным XML-данным, предоставленным входным потоком. Поскольку эта функция обеспечивает включение XML-данных, расположенных в других местах, объект <xref:System.Xml.XmlResolver> со значением `null`, предоставленный методу <xref:System.Xml.Xsl.XslTransform.Transform%2A>, предотвращает выполнение функции `document()`. Если необходимо использовать функцию `document()`, используйте метод <xref:System.Xml.Xsl.XslTransform.Transform%2A>, который получает объект <xref:System.Xml.XmlResolver> в качестве параметра, в дополнение к соответствующему набору разрешений.  
  
 Дополнительные сведения о методе <xref:System.Xml.Xsl.XslTransform.Load%2A> и использовании им класса <xref:System.Xml.XmlResolver> см. в разделе <xref:System.Xml.Xsl.XslTransform.Load%28System.String%2CSystem.Xml.XmlResolver%29?displayProperty=nameWithType>.  
  
 При вызове метода <xref:System.Xml.Xsl.XslTransform.Transform%2A> разрешения вычисляются с учетом свидетельств, предоставленных во время загрузки, и этот набор разрешений назначается всему процессу преобразования. Если функция `document()` пытается инициировать действие, для которого требуются разрешения, отсутствующие в наборе, вызывается исключение.  
  
## <a name="see-also"></a>См. также

- [XSLT-преобразования с помощью класса XslTransform](xslt-transformations-with-the-xsltransform-class.md)
- [Реализация классом XslTransform XSLT-процессора](xsltransform-class-implements-the-xslt-processor.md)
- [Результаты вывода XslTransform](outputs-from-an-xsltransform.md)
- [XSLT-преобразования над различными хранилищами](xslt-transformations-over-different-stores.md)
- [XsltArgumentList для параметров таблицы стилей и объектов расширения](xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md)
- [Использование скриптов таблиц стилей XSLT\<msxsl:script>](xslt-stylesheet-scripting-using-msxsl-script.md)
- [Поддержка функции msxsl:node-set()](support-for-the-msxsl-node-set-function.md)
- [XPathNavigator в преобразованиях](xpathnavigator-in-transformations.md)
- [XPathNodeIterator в преобразованиях](xpathnodeiterator-in-transformations.md)
- [Ввод XPathDocument в XslTransform](xpathdocument-input-to-xsltransform.md)
- [Ввод XmlDataDocument в XslTransform](xmldatadocument-input-to-xsltransform.md)
- [Ввод XmlDocument в XslTransform](xmldocument-input-to-xsltransform.md)

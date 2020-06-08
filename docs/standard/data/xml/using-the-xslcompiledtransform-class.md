---
title: Использование класса XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: 8705b4c6324ce20a1f37d3ee864ab494adcdd6a5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281778"
---
# <a name="using-the-xslcompiledtransform-class"></a>Использование класса XslCompiledTransform
Класс <xref:System.Xml.Xsl.XslCompiledTransform> является обработчиком XSLT в платформе Microsoft .NET Framework. Этот класс используется для компиляции таблиц стилей и выполнения преобразований XSLT.  
  
> [!NOTE]
> Хотя класс <xref:System.Xml.Xsl.XslCompiledTransform> имеет более высокий общий уровень производительности, чем класс <xref:System.Xml.Xsl.XslTransform>, метод <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> класса <xref:System.Xml.Xsl.XslCompiledTransform> может выполняться медленнее, чем метод <xref:System.Xml.Xsl.XslTransform.Load%2A> класса <xref:System.Xml.Xsl.XslTransform> при первом вызове преобразования. Причина этого заключается в необходимости компиляции XSLT-файла перед его загрузкой. Дополнительные сведения см. в следующей записи блога: [XslCompiledTransform выполняется медленнее, чем XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)  
  
## <a name="in-this-section"></a>В этом разделе  
 [Входные данные для класса XslCompiledTransform](inputs-to-the-xslcompiledtransform-class.md)  
 Описываются доступные входные параметры XSLT.  
  
 [Параметры вывода в классе XslCompiledTransform](output-options-on-the-xslcompiledtransform-class.md)  
 Описываются доступные выходные параметры XSLT.  
  
 [Разрешение внешних ресурсов в ходе обработки XSLT](resolving-external-resources-during-xslt-processing.md)  
 Обсуждается использование класса <xref:System.Xml.XmlResolver> для разрешения внешних ресурсов.  
  
 [Расширение таблиц стилей XSLT](extending-xslt-style-sheets.md)  
 Обсуждается поддержка расширений XSLT.  
  
|||  
|-|-|  
|[Устранимые ошибки XSLT](recoverable-xslt-errors.md)|Содержит список поведений по выбору, допустимых в соответствии с рекомендациями консорциума W3C по XSLT 1.0, и описывает, каким образом эти поведения обрабатываются классом <xref:System.Xml.Xsl.XslCompiledTransform>.|  
|[Практическое руководство. Преобразование фрагмента узла](how-to-transform-a-node-fragment.md)|Описывает процесс преобразования фрагмента узла.|  
  
## <a name="related-sections"></a>Связанные разделы  
 [Миграция с класса XslTransform](migrating-from-the-xsltransform-class.md)  
 Обсуждается перенос кода из класса <xref:System.Xml.Xsl.XslTransform>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>

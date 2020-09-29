---
title: Поддержка функции msxsl:node-set()
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
ms.openlocfilehash: 30652d8cbaac333cc1cb35954742b16dc7c4764b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071993"
---
# <a name="support-for-the-msxslnode-set-function"></a>Поддержка функции msxsl:node-set()
Функция `msxsl:node-set` позволяет преобразовать фрагмент дерева результатов в набор узлов. Получаемый в результате набор узлов всегда содержит один узел, который является корневым узлом дерева.  
  
> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](migrating-from-the-xsltransform-class.md).  
  
 Функция `msxsl:node-set` позволяет преобразовать фрагмент дерева результатов в набор узлов. Получаемый в результате набор узлов всегда содержит один узел, который является корневым узлом дерева.  
  
## <a name="example"></a>Пример  
 В следующем примере `$books` - переменная, представляющая собой дерево узлов в таблице стилей. Инструкция for-each в сочетании с функцией `node-set` позволяет пользователю проходить по этому дереву узлов как по набору узлов.  
  
## <a name="nodesetxsl"></a>nodeset.xsl  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.contoso.com"  
                version="1.0">  
    <xsl:variable name="books">  
        <book author="Michael Howard">Writing Secure Code</book>  
        <book author="Michael Kay">XSLT Reference</book>  
    </xsl:variable>  
  
    <xsl:template match="/">  
        <authors>  
            <xsl:for-each select="msxsl:node-set($books)/book">
                <author><xsl:value-of select="@author"/></author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a>Вывод  
 Выходные данные преобразования:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a>См. также

- [Реализация классом XslTransform XSLT-процессора](xsltransform-class-implements-the-xslt-processor.md)

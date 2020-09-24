---
title: Схема параметров криптографии
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: 0215851f83a13ee48547144f08c5c693ec2d90bf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149534"
---
# <a name="cryptography-settings-schema"></a>Схема параметров криптографии

Схема параметров шифрования содержит элементы, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)

|Элемент|Описание|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](cryptoclasses-element.md)|Содержит список криптографических классов, сопоставленных с понятным именем в **\<nameEntry>** элементе.|  
|[**\<cryptoClass**>](cryptoclass-element.md)|Содержит криптографический класс, сопоставленный с понятным именем в **\<nameEntry>** элементе.|  
|[**\<cryptographySettings**>](cryptographysettings-element.md)|Содержит параметры шифрования.|  
|[**\<cryptoNameMapping**>](cryptonamemapping-element.md)|Содержит сопоставления классов с понятными именами.|  
|[**\<mscorlib>** элемент для параметров шифрования](mscorlib-element-for-cryptography-settings.md)|Содержит **\<cryptographySettings>** элемент.|  
|[**\<nameEntry>**](nameentry-element.md)|Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.|  
|[**\<oidEntry>**](oidentry-element.md)|Сопоставляет идентификатор объекта (OID) ASN.1 с понятным именем.|  
|[**\<oidMap>**](oidmap-element.md)|Содержит сопоставления идентификатора объекта ASN.1 с классами.|  
  
## <a name="see-also"></a>См. также

- [Схема файла конфигурации](../index.md)
- [службы шифрования](../../../../standard/security/cryptographic-services.md)

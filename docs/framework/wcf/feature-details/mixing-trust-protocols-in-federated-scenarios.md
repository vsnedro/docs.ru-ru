---
title: Использование нескольких протоколов доверия в сценариях федерации
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: 5ce178c0b2c83469a26993ce6db2d6c87815543b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248179"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Использование нескольких протоколов доверия в сценариях федерации

Возможны сценарии, в которых федеративные клиенты взаимодействуют со службой и службой маркеров безопасности, версии доверия которых не совпадают. Код WSDL службы может содержать утверждение `RequestSecurityTokenTemplate` с элементами WS-Trust, версии которых не совпадают с версией службы маркеров безопасности. В таких случаях клиент Windows Communication Foundation (WCF) преобразует элементы WS-Trust, полученные из, в, `RequestSecurityTokenTemplate` чтобы соответствовать версии доверия STS. WCF обрабатывает несоответствующие версии доверия только для стандартных привязок. Все стандартные параметры алгоритма, распознаваемые WCF, являются частью стандартной привязки. В этом разделе описывается поведение WCF с различными параметрами доверия между службой и STS.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>Проверяющая сторона и служба маркеров безопасности используют версию февраля 2005 г.  

 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 Файл конфигурации клиента содержит список параметров.  
  
 WCF не может различить параметры клиента и службы; Он добавляет все параметры и отправляет их в `RequestSecurityTokenTemplate` (RST).  
  
## <a name="rp-trust-13-and-sts-trust-13"></a>Проверяющая сторона и служба маркеров безопасности используют версию Trust 1.3  

 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 Файл конфигурации клиента содержит элемент `secondaryParameters`, являющийся оболочкой для параметров, заданных проверяющей стороной.  
  
 WCF удаляет `EncryptionAlgorithm` `CanonicalizationAlgorithm` `KeyWrapAlgorithm` элементы и из элемента верхнего уровня в RST, если они существуют внутри `SecondaryParameters` элемента. WCF добавляет `SecondaryParameters` элемент в исходящий RST без изменений.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>Проверяющая сторона использует версию февраля 2005 г., а служба маркеров безопасности - версию Trust 1.3  

 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 Файл конфигурации клиента содержит список параметров.  
  
 В файле конфигурации клиента WCF не может различить параметры службы и клиента. Поэтому WCF преобразует все параметры в пространство имен доверия версии 1,3.  
  
 WCF обрабатывает `KeyType` элементы, `KeySize` и `TokenType` следующим образом:  
  
- Загружается код WSDL, создается привязка и присваиваются значения `KeyType`, `KeySize` и `TokenType` на основании параметров проверяющей стороны. Создается файл конфигурации клиента.  
  
- Теперь клиент может изменять любые параметры в файле конфигурации.  
  
- Во время выполнения WCF копирует все параметры, указанные в `AdditionalTokenParameters` разделе файла конфигурации клиента, за исключением `KeyType` `KeySize` и `TokenType` , поскольку эти параметры задаются во время создания файла конфигурации.  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a>Проверяющая сторона использует версию Trust 1.3, а служба маркеров безопасности - версию февраля 2005 г.  

 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 Файл конфигурации клиента содержит элемент `secondaryParamters`, являющийся оболочкой для параметров, заданных проверяющей стороной.  
  
 WCF копирует все параметры, указанные в `SecondaryParameters` разделе, в элемент RST верхнего уровня, но не преобразует их в пространство имен 2005 WS-Trust.

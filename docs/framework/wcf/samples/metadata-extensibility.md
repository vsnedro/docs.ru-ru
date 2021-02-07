---
description: Дополнительные сведения см. в статье расширение возможностей метаданных.
title: Расширяемость метаданных
ms.date: 03/30/2017
ms.assetid: f92fcc76-0806-4c84-9d63-7aae0d3899de
ms.openlocfilehash: 3ca1117bd5b1e3098a8d8d0ceb21e90bc7e4d39e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752175"
---
# <a name="metadata-extensibility"></a>Расширяемость метаданных

В этом разделе содержатся образцы, демонстрирующие пользовательские метаданные.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Пользовательская конечная точка защищенных метаданных](custom-secure-metadata-endpoint.md)  
 Демонстрирует, как реализовать службу с защищенной конечной точкой метаданных, которая использует одну из привязок обмена, отличной от метаданных, и как настроить [средство служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) или клиенты для выборки метаданных из такой конечной точки метаданных.  
  
 [Пользовательская публикация WSDL](custom-wsdl-publication.md)  
 Показывает, как среди прочих функциональных возможностей реализовать <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> пользовательского атрибута <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> для экспорта свойств атрибута в виде заметок WSDL.

---
title: Расширяемость метаданных
ms.date: 03/30/2017
ms.assetid: f92fcc76-0806-4c84-9d63-7aae0d3899de
ms.openlocfilehash: fb37e33026a5f99bfa033f04eea0bb85fbbe65c7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294330"
---
# <a name="metadata-extensibility"></a>Расширяемость метаданных

В этом разделе содержатся образцы, демонстрирующие пользовательские метаданные.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Пользовательская конечная точка защищенных метаданных](custom-secure-metadata-endpoint.md)  
 Демонстрирует, как реализовать службу с защищенной конечной точкой метаданных, которая использует одну из привязок обмена, отличной от метаданных, и как настроить [средство служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) или клиенты для выборки метаданных из такой конечной точки метаданных.  
  
 [Пользовательская публикация WSDL](custom-wsdl-publication.md)  
 Показывает, как среди прочих функциональных возможностей реализовать <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> пользовательского атрибута <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> для экспорта свойств атрибута в виде заметок WSDL.

---
title: Расширяемость метаданных
ms.date: 03/30/2017
ms.assetid: f92fcc76-0806-4c84-9d63-7aae0d3899de
ms.openlocfilehash: 1e8e7f511b38cf3326b9abbca57df769317a26a4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584627"
---
# <a name="metadata-extensibility"></a>Расширяемость метаданных
В этом разделе содержатся образцы, демонстрирующие пользовательские метаданные.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Пользовательская конечная точка защищенных метаданных](custom-secure-metadata-endpoint.md)  
 Демонстрирует, как реализовать службу с защищенной конечной точкой метаданных, которая использует одну из привязок обмена, отличной от метаданных, и как настроить [средство служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) или клиенты для выборки метаданных из такой конечной точки метаданных.  
  
 [Пользовательская публикация WSDL](custom-wsdl-publication.md)  
 Показывает, как среди прочих функциональных возможностей реализовать <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> пользовательского атрибута <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> для экспорта свойств атрибута в виде заметок WSDL.

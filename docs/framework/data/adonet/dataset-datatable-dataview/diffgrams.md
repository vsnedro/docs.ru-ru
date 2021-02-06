---
description: 'Дополнительные сведения о: дельтами'
title: DiffGrams
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: df00bbfb2c25014ff4e73a2777511bd3593ff8a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652514"
---
# <a name="diffgrams"></a>DiffGrams

DiffGram - это формат XML, определяющий текущую и первоначальную версию элементов данных. Набор данных <xref:System.Data.DataSet> использует формат DiffGram для загрузки и хранения своего содержимого, а также для сериализации содержимого перед отправкой его по сетевому подключению. Когда объект <xref:System.Data.DataSet> записывается как DiffGram, он заполняет DiffGram всеми необходимыми сведениями, чтобы правильно воссоздать содержимое, хотя это не схема, <xref:System.Data.DataSet> включая значения столбцов из **исходной** и **текущей** версий строк, сведения об ошибке строки и порядок строк.  
  
 При отправке и получении набора данных <xref:System.Data.DataSet> из веб-службы XML формат DiffGram используется неявно. Кроме того, при загрузке содержимого <xref:System.Data.DataSet> из XML с помощью метода **ReadXml** или при записи содержимого <xref:System.Data.DataSet> в XML с помощью метода **WriteXml** можно указать, что содержимое считывается или записывается в виде DiffGram. Дополнительные сведения см. в статьях [Загрузка набора данных из XML](loading-a-dataset-from-xml.md) и [запись содержимого набора данных в виде XML-данных](writing-dataset-contents-as-xml-data.md).  
  
 Хотя формат DiffGram в основном используется платформой .NET Framework как формат сериализации для содержимого набора данных <xref:System.Data.DataSet>, его можно также применять для изменения данных в таблицах базы данных Microsoft SQL Server.  
  
 Объект DiffGram создается путем записи содержимого всех таблиц в **\<diffgram>** элемент.  
  
### <a name="to-generate-a-diffgram"></a>Создание Diffgram  
  
1. Создайте список корневых таблиц (таблиц, не имеющих родителей).  
  
2. Для каждой таблицы и ее потомков в списке запишите текущую версию всех строк в первом разделе Diffgram.  
  
3. Для каждой таблицы в <xref:System.Data.DataSet> запишите исходную версию всех строк, если таковые имеются, в **\<before>** разделе Diffgram.  
  
4. Для строк с ошибками запишите содержимое ошибки в **\<errors>** разделе Diffgram.  
  
 Diffgram обрабатывается в последовательном порядке от начала XML-файла до его конца.  
  
### <a name="to-process-a-diffgram"></a>Обработка Diffgram  
  
1. Обработайте первый раздел Diffgram, содержащий текущую версию строк.  
  
2. Обработать второй или **\<before>** раздел, содержащий исходную версию строк измененных и удаленных строк.  
  
    > [!NOTE]
    > Если строка помечена как удаленная, то операция удаления может удалить потомков этой строки в зависимости от свойства `Cascade` текущего набора данных <xref:System.Data.DataSet>.  
  
3. Обработайте **\<errors>** раздел. Установите сведения об ошибках для всех заданных строк и столбцов каждого элемента в этом разделе.  
  
> [!NOTE]
> Если в Diffgram задан режим <xref:System.Data.XmlWriteMode>, то содержимое целевого набора <xref:System.Data.DataSet> и исходного набора <xref:System.Data.DataSet> могут различаться.  
  
## <a name="diffgram-format"></a>Формат дельт  

 Формат DiffGram содержит три раздела: текущие данные, исходные данные и раздел ошибок, как показано в следующем примере.  
  
```xml  
<?xml version="1.0"?>  
<diffgr:diffgram
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  
   <DataInstance>  
   </DataInstance>  
  
  <diffgr:before>  
  </diffgr:before>  
  
  <diffgr:errors>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
 Формат DiffGram состоит из следующих блоков данных:  
  
 **\<**  **_DataInstance_*_  _*>**  
 Имя этого элемента, ***instance** _, используется для объяснения целей в этой документации. Элемент _*_instance_*_ представляет <xref:System.Data.DataSet> строку типа или <xref:System.Data.DataTable> . Вместо _DataInstance * элемент будет содержать имя <xref:System.Data.DataSet> или <xref:System.Data.DataTable> . Этот блок формата DiffGram содержит текущие данные, независимо от изменений в этих данных. Элемент (или строка), который был изменен, определяется с помощью аннотации **diffgr: hasChanges** .  
  
 **\<diffgr:before>**  
 Этот блок формата DiffGram содержит первоначальную версию строки. Элементы в этом блоке сопоставляются с элементами в блоке ***instance** _ с помощью аннотации _ *diffgr: ID**.  
  
 **\<diffgr:errors>**  
 Этот блок формата DiffGram содержит сведения об ошибке для определенной строки в блоке ***instance** _. Элементы в этом блоке сопоставляются с элементами в блоке _*_instance_*_ с помощью аннотации _ *diffgr: ID**.  
  
## <a name="diffgram-annotations"></a>Заметки дельт  

 В формате DiffGrams используется несколько заметок для связывания элементов из разных блоков DiffGram, представляющих разные версии строк или сведения об ошибках в <xref:System.Data.DataSet>.  
  
 В следующей таблице описаны аннотации DiffGram, которые определены в пространстве имен **urn: schemas-microsoft-com: XML-DiffGram-v1**.  
  
|Annotation|Описание|  
|----------------|-----------------|  
|**идентификатор**|Используется для связывания элементов в **\<diffgr:before>** **\<diffgr:errors>** блоках и с элементами в **\<** **_DataInstance_*_ _*>** блоке. Значения с заметкой **diffgr: ID** представлены в формате *[TableName] [ровидентифиер]*. Например, `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Определяет, какой элемент из **\<** **_DataInstance_*_ _*>** блока является родительским элементом текущего элемента. Значения с аннотацией **diffgr: ParentID** находятся в формате *[TableName] [ровидентифиер]*. Например, `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Определяет строку в **\<** **_DataInstance_*_ _*>** блоке как измененную. Аннотация **HasChanges** может иметь одно из следующих двух значений:<br /><br /> **внедрен**<br /> Определяет **добавленную** строку.<br /><br /> **изменено**<br /> Определяет **измененную** строку, содержащую **исходную** версию строки в **\<diffgr:before>** блоке. Обратите внимание, что **Удаленные** строки будут иметь **исходную** версию строки в **\<diffgr:before>** блоке, но элемент с аннотацией в **\<** **_DataInstance_*_ _*>** блоке не будет.|  
|**hasErrors**|Определяет строку в **\<** **_DataInstance_*_ _*>** блоке с помощью **роверрор**. Элемент Error помещается в **\<diffgr:errors>** блок.|  
|**Ошибка**|Содержит текст **роверрор** для определенного элемента в **\<diffgr:errors>** блоке.|  
  
 Набор данных <xref:System.Data.DataSet> содержит дополнительные заметки при считывании или записи содержимого в формате DiffGram. В следующей таблице описаны эти дополнительные аннотации, которые определены в пространстве имен **urn: schemas-microsoft-com: XML-msdata**.  
  
|Annotation|Описание|  
|----------------|-----------------|  
|**ровордер**|Сохраняет порядок строк исходных данных и определяет индекс строки в конкретной таблице <xref:System.Data.DataTable>.|  
|**Скрыта**|Определяет столбец как свойство **ColumnMapping** имеет значение **MappingType. Hidden**. Атрибут записывается в формате **msdata: Hidden** *[имя_столбца]*= "*value*". Например, `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Обратите внимание, что скрытые столбцы записываются как атрибут DiffGram только если они содержат данные. В остальных случаях этот параметр игнорируется.|  
  
## <a name="sample-diffgram"></a>Образец DiffGram  

 Ниже показан пример формата DiffGram. На нем показан результат обновления строки в таблице перед фиксацией изменений. Строка с идентификатором пользователя «ALFKI» была изменена, но не обновлена. В результате существует **Текущая** строка с **идентификатором diffgr: ID** "Customers1" в **\<** **_DataInstance_*_ _*>** блоке, а также **Исходная** строка с **идентификатором diffgr: ID** "Customers1" в **\<diffgr:before>** блоке. Строка с идентификатором CustomerID "АНАТР" включает **роверрор**, поэтому она снабжена заметками `diffgr:hasErrors="true"` и в блоке есть связанный элемент **\<diffgr:errors>** .  
  
```xml  
<diffgr:diffgram xmlns:msdata="urn:schemas-microsoft-com:xml-msdata" xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
  <CustomerDataSet>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0" diffgr:hasChanges="modified">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>New Company</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers2" msdata:rowOrder="1" diffgram:hasErrors="true">  
      <CustomerID>ANATR</CustomerID>  
      <CompanyName>Ana Trujillo Emparedados y Helados</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers3" msdata:rowOrder="2">  
      <CustomerID>ANTON</CustomerID>  
      <CompanyName>Antonio Moreno Taquera</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers4" msdata:rowOrder="3">  
      <CustomerID>AROUT</CustomerID>  
      <CompanyName>Around the Horn</CompanyName>  
    </Customers>  
  </CustomerDataSet>  
  <diffgr:before>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>Alfreds Futterkiste</CompanyName>  
    </Customers>  
  </diffgr:before>  
  <diffgr:errors>  
    <Customers diffgr:id="Customers2" diffgr:Error="An optimistic concurrency violation has occurred for this row."/>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
## <a name="see-also"></a>См. также

- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Загрузка набора данных из XML](loading-a-dataset-from-xml.md)
- [Запись содержимого набора как данных XML](writing-dataset-contents-as-xml-data.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)

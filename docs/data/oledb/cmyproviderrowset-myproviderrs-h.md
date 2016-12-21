---
title: "CMyProviderRowset (MyProviderRS.H) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cmyproviderrowset"
  - ""myproviderrs.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderRowset クラス MyProviderRS.H"
  - "OLE DB プロバイダー, ウィザードが生成したファイル"
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderRowset (MyProviderRS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ウィザードは、行セット オブジェクトのエントリを生成します。  この場合は、`CMyProviderRowset` と呼ばれます。  `CMyProviderRowset` クラスは、`CRowsetImpl` と呼ばれる OLE DB プロバイダー クラスを継承します。このクラスは、行セット オブジェクトに必要なすべてのインターフェイスを実装します。  次に示すコードは、`CRowsetImpl` の継承チェインです。  
  
```  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T > >  
```  
  
 `CRowsetImpl` は、`IAccessor` インターフェイスと `IColumnsInfo` インターフェイスも使用します。  これらのインターフェイスは、テーブル内の出力フィールドに対して使用されます。  また、このクラスは、**IRowsetIdentity** の実装も提供します。これにより、コンシューマーは、2 つの行が同じかどうかを判断できます。  `IRowsetInfo` インターフェイスは行セット オブジェクトのプロパティを実装します。  **IConvertType** インターフェイスを使用すると、プロバイダーは、コンシューマーから要求されたデータ型が、プロバイダーで使用されるデータ型と異なる場合でも、要求された型を返すことができます。  
  
 `IRowset` インターフェイスは、実際にはデータ取得を処理します。  コンシューマーは、最初に `GetNextRows` というメソッドを呼び出して、**HROW** という行ハンドルを返します。  コンシューマーは、次にその **HROW** を使用して **IRowset::GetData** を呼び出し、要求されたデータを取得します。  
  
 `CRowsetImpl` は、いくつかのテンプレート パラメーターもパラメーターとして扱います。  これらのパラメーターにより、`CRowsetImpl` クラスでデータを処理する方法を決定できます。  たとえば、引数 `ArrayType` を使用して、行データの格納に使用されるストレージ機構を決定できます。  **RowClass** パラメーターは、**HROW** を含むクラスを指定します。  
  
 **RowsetInterface** パラメーターを使用すると、`IRowsetLocate` インターフェイスまたは `IRowsetScroll` インターフェイスも使用できます。  `IRowsetLocate` インターフェイスと `IRowsetScroll` インターフェイスは、どちらも `IRowset` を継承します。  したがって、OLE DB プロバイダー テンプレートは、これらのインターフェイス専用の特別な処理を用意する必要があります。  これらのインターフェイスのどちらかを使用する場合は、RowsetInterface パラメーターを使用する必要があります。  
  
## 参照  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)
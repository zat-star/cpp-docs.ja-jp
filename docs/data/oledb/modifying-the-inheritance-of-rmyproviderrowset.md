---
title: "RMyProviderRowset の継承の変更 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "継承 [C++]"
  - "RMyProviderRowset"
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RMyProviderRowset の継承の変更
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`IRowsetLocate` インターフェイスを単純な読み取り専用プロバイダーのコードに追加するには、**RMyProviderRowset** の継承を変更します。  本来、**RMyProviderRowset** は `CRowsetImpl` を継承しています。  この CRowsetImpl の代わりに、**CRowsetBaseImpl** を継承する必要があります。  
  
 この変更を行うには、次のように新しい `CMyRowsetImpl` クラスを MyProviderRS.h に作成します。  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate > >  
{  
...  
};  
```  
  
 次に、MyProviderRS.h の COM インターフェイス マップを次のように編集します。  
  
```  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 これにより、`CMyRowsetImpl` から `IRowset` インターフェイスと `IRowsetLocate` インターフェイスに対して **QueryInterface** を呼び出す COM インターフェイス マップが作成されます。  これ以外の行セット クラスの実装をすべて取得するには、マップは OLE DB テンプレートで定義されている **CRowsetBaseImpl** クラスに `CMyRowsetImpl` クラスをリンクする必要があります。マップは、COM\_INTERFACE\_ENTRY\_CHAIN マクロを使用します。このマクロを追加すると、`QueryInterface` を呼び出したときに、OLE DB テンプレートによって **CRowsetBaseImpl** の COM マップがスキャンされます。  
  
 最後に、`RAgentRowset` を `CMyRowsetBaseImpl` にリンクするために、継承関係を変更します。次のように `RAgentRowset` を `CMyRowsetImpl` から継承します。  
  
```  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
 この `RAgentRowset` では、`IRowsetLocate` インターフェイスを使用しながら、行セット クラスの残りの実装を利用できるようになります。  
  
 この処理が完了すると、[コンシューマーに返される列を動的に判断](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)できます。  
  
## 参照  
 [単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)
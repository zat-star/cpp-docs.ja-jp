---
title: "CUtlProps::OnInterfaceRequested | Microsoft Docs"
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
  - "CUtlProps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnInterfaceRequested メソッド"
ms.assetid: a5e1a879-cff3-4e01-b902-2249a152984f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps::OnInterfaceRequested
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンシューマーが呼び出すと省略可能なインターフェイスの要求は、オブジェクト作成の 1 種類のメソッド インターフェイスです。  
  
## 構文  
  
```  
  
      virtual HRESULT CUtlPropsBase::OnInterfaceRequested(  
   REFIID riid  
);  
```  
  
#### パラメーター  
 `riid`  
 \[\]要求されたインターフェイスの IID。  詳細については、*OLE DB Programmer's Reference* の `ICommand::Execute` の `riid` パラメーターの説明を参照してください \(*MDAC SDK*\)。  
  
## 解説  
 **OnInterfaceRequested** は、コンシューマーがオブジェクト作成インターフェイスの 1 種類のメソッドを呼び出すと省略可能なインターフェイスのコンシューマーの要求を処理します \(**IDBCreateSession**、**IDBCreateCommand**、`IOpenRowset`、または `ICommand`など\)。  ここで要求されたインターフェイスに対応する OLE DB のプロパティを設定します。  たとえば、コンシューマーが **IID\_IRowsetLocate**を要求した場合、**OnInterfaceRequested** は **DBPROP\_IRowsetLocate** インターフェイスを設定します。  すると、行セットの作成時に、正しい状態を保持します。  
  
 このメソッドは、コンシューマーが **IOpenRowset::OpenRowset** または `ICommand::Execute`を呼び出すときに呼び出されます。  
  
 コンシューマーがオブジェクトを開き、省略可能なインターフェイスを要求した場合、プロバイダーはプロパティを `VARIANT_TRUE`がそのインターフェイスに関連付けられた属性を設定する必要があります。  処理する特定のプロパティを有効にするには **OnInterfaceRequested** はプロバイダーの **実行** のメソッドが呼び出される前に呼び出されます。  既定で、**OnInterfaceRequested** は次のインターフェイスを処理します:  
  
-   `IRowsetLocate`  
  
-   `IRowsetChange`  
  
-   `IRowsetUpdate`  
  
-   **IConnectionPointContainer**  
  
-   `IRowsetScroll`  
  
 そのほかのインターフェイスを処理しは関数を処理するデータ ソース、セッション、コマンド、および行セット クラスでこの関数をオーバーライドします。  オーバーライドを設定する標準に移動するとプロパティの設定は、チェーン プロパティを設定するようにプロパティ インターフェイスを取得します。[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)
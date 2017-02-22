---
title: "range_adapter (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::range_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "range_adapter クラス [STL/CLR]"
ms.assetid: 3fbe2a65-1216-46a0-a182-422816b80cfb
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# range_adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

複数 Base Class Library \(BCL\) を実装するために使用する反復子のペアをラップするテンプレート クラスはインターフェイスです。  これは BCL のコレクションと同じように STL\/CLR の範囲を処理するために range\_adapter を使用します。  
  
## 構文  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### パラメーター  
 Iter  
 ラップされた反復子に関連付けられている型。  
  
## メンバー  
  
|メンバー関数|説明|  
|------------|--------|  
|[range\_adapter::range\_adapter](../dotnet/range-adapter-range-adapter-stl-clr.md)|アダプター オブジェクトを構築します。|  
  
|演算子|説明|  
|---------|--------|  
|[range\_adapter::operator\=](../dotnet/range-adapter-operator-assign-stl-clr.md)|格納されている反復子のペアを置き換えます。|  
  
## インターフェイス  
  
|インターフェイス|説明|  
|--------------|--------|  
|<xref:System.Collections.IEnumerable>|コレクションの要素を反復処理します。|  
|<xref:System.Collections.ICollection>|要素のグループを保持します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|iterates through コレクション要素を入力しました。|  
|<xref:System.Collections.Generic.ICollection%601>|指定された要素のグループを保持します。|  
  
## 解説  
 range\_adapter は、要素のシーケンスを区切る反復子のペアを格納します。  オブジェクトは、要素を反復処理するような順序で 4 個の BCL インターフェイスを実装します。  Optimizing のコンテナーと同じように STL\/CLR の範囲を処理するには、このテンプレート クラスを使用します。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/アダプター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [collection\_adapter](../Topic/collection_adapter%20\(STL-CLR\).md)   
 [make\_collection](../dotnet/make-collection-stl-clr.md)
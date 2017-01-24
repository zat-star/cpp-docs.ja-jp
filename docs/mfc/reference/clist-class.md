---
title: "CList クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CList クラス"
  - "一覧"
  - "一覧, 基本クラス"
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CList クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オブジェクト \(重複あり\) を順に並べたリストをサポートします。このリストには、シーケンシャル アクセスまたは値指定によるアクセスを行うことができます。  
  
## 構文  
  
```  
template< class TYPE, class ARG_TYPE = const TYPE& >   
class CList : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CList::CList](../Topic/CList::CList.md)|空の順序付きリストを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CList::AddHead](../Topic/CList::AddHead.md)|要素 \(またはほかのリストのすべての要素\) をリストの先頭に追加します \(その要素を新たに先頭とします\)。|  
|[CList::AddTail](../Topic/CList::AddTail.md)|要素 \(またはほかのリストのすべての要素\) をリストの末尾に追加します \(その要素を新たに末尾とします\)。|  
|[CList::Find](../Topic/CList::Find.md)|ポインターの値で指定された要素の位置を取得します。|  
|[CList::FindIndex](../Topic/CList::FindIndex.md)|0 から始まるインデックスで示される要素の位置を取得します。|  
|[CList::GetAt](../Topic/CList::GetAt.md)|指定した位置の要素を取得します。|  
|[CList::GetCount](../Topic/CList::GetCount.md)|リストの要素数を返します。|  
|[CList::GetHead](../Topic/CList::GetHead.md)|リストの先頭要素を返します。リストが空のときは使用できません。|  
|[CList::GetHeadPosition](../Topic/CList::GetHeadPosition.md)|リストの先頭要素の位置を返します。|  
|[CList::GetNext](../Topic/CList::GetNext.md)|次の要素を順番に取得します。|  
|[CList::GetPrev](../Topic/CList::GetPrev.md)|順次アクセスするときの直前の要素を取得します。|  
|[CList::GetSize](../Topic/CList::GetSize.md)|リストの要素数を返します。|  
|[CList::GetTail](../Topic/CList::GetTail.md)|リストの末尾要素を返します。リストが空のときは使用できません。|  
|[CList::GetTailPosition](../Topic/CList::GetTailPosition.md)|リストの末尾要素の位置を返します。|  
|[CList::InsertAfter](../Topic/CList::InsertAfter.md)|指定した位置の後ろに新しい要素を挿入します。|  
|[CList::InsertBefore](../Topic/CList::InsertBefore.md)|指定した位置の前に新しい要素を挿入します。|  
|[CList::IsEmpty](../Topic/CList::IsEmpty.md)|リストの状態が空 \(要素がない\) かどうかを調べます。|  
|[CList::RemoveAll](../Topic/CList::RemoveAll.md)|リストからすべての要素を削除します。|  
|[CList::RemoveAt](../Topic/CList::RemoveAt.md)|位置で指定されたこの一覧から要素を削除します。|  
|[CList::RemoveHead](../Topic/CList::RemoveHead.md)|リストの先頭にある要素を削除します。|  
|[CList::RemoveTail](../Topic/CList::RemoveTail.md)|リストの末尾にある要素を削除します。|  
|[CList::SetAt](../Topic/CList::SetAt.md)|指定した位置に要素を設定します。|  
  
#### パラメーター  
 `TYPE`  
 リストに格納されているオブジェクトの型。  
  
 `ARG` *\_* `TYPE`  
 リストに格納されているオブジェクト参照に使用される型。  参照である場合があります。  
  
## 解説  
 `CList` の一覧には、二重リンク リストのようになります。  
  
 **POSITION** 型の変数は、リストのキーです。  反復子とブックマークとして場所を保持するリストを順番に検索するに **POSITION** の変数を使用できます。  ただし、インデックス位置は、と同じではありません。  
  
 要素の挿入はリストの先頭、末尾、および既知の **POSITION**に非常に高速です。  シーケンシャル サーチに、値またはインデックスで要素を調べて必要です。  この検索はリストが分かかることがあります。  
  
 リストの各要素をダンプする必要があるときは、1 にダンプ コンテキストの深さを設定するより大きい。  
  
 このクラスの一部のメンバー関数は、グローバルなヘルパー関数を呼び出します。したがって、`CList` クラスの主な用途に合わせて、これらのヘルパー関数をカスタマイズする必要があります。  「MFC マクロとグローバル」の [コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md) を参照してください。  
  
 `CList`の使用の詳細については、" " [&#91;コレクション&#93;](../../mfc/collections.md)を参照してください。  
  
## 使用例  
 [!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/CPP/clist-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CList`  
  
## 必要条件  
 **Header:** afxtempl.h  
  
## 参照  
 [MFC のサンプルが収集されます](../../top/visual-cpp-samples.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMap クラス](../../mfc/reference/cmap-class.md)   
 [CArray クラス](../../mfc/reference/carray-class.md)
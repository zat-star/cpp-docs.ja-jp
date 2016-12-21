---
title: "CObList クラス | Microsoft Docs"
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
  - "CObList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObList クラス"
  - "一覧, object"
  - "オブジェクト [C++], 一覧"
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObList クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アクセスできる `CObject` の一意でないポインターの順次またはポインター値によるサポートの順序付きリスト。  
  
## 構文  
  
```  
class CObList : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CObList::CObList](../Topic/CObList::CObList.md)|`CObject` ポインターの空のリストを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CObList::AddHead](../Topic/CObList::AddHead.md)|要素 \(またはほかのリストのすべての要素\) をリストの先頭に追加します \(その要素を新たに先頭とします\)。|  
|[CObList::AddTail](../Topic/CObList::AddTail.md)|要素 \(またはほかのリストのすべての要素\) をリストの末尾に追加します \(その要素を新たに末尾とします\)。|  
|[CObList::Find](../Topic/CObList::Find.md)|ポインターの値で指定された要素の位置を取得します。|  
|[CObList::FindIndex](../Topic/CObList::FindIndex.md)|0 から始まるインデックスで示される要素の位置を取得します。|  
|[CObList::GetAt](../Topic/CObList::GetAt.md)|指定した位置の要素を取得します。|  
|[CObList::GetCount](../Topic/CObList::GetCount.md)|リストの要素数を返します。|  
|[CObList::GetHead](../Topic/CObList::GetHead.md)|リストの先頭要素を返します。リストが空のときは使用できません。|  
|[CObList::GetHeadPosition](../Topic/CObList::GetHeadPosition.md)|リストの先頭要素の位置を返します。|  
|[CObList::GetNext](../Topic/CObList::GetNext.md)|次の要素を順番に取得します。|  
|[CObList::GetPrev](../Topic/CObList::GetPrev.md)|順次アクセスするときの直前の要素を取得します。|  
|[CObList::GetSize](../Topic/CObList::GetSize.md)|リストの要素数を返します。|  
|[CObList::GetTail](../Topic/CObList::GetTail.md)|リストの末尾要素を返します。リストが空のときは使用できません。|  
|[CObList::GetTailPosition](../Topic/CObList::GetTailPosition.md)|リストの末尾要素の位置を返します。|  
|[CObList::InsertAfter](../Topic/CObList::InsertAfter.md)|指定した位置の後ろに新しい要素を挿入します。|  
|[CObList::InsertBefore](../Topic/CObList::InsertBefore.md)|指定した位置の前に新しい要素を挿入します。|  
|[CObList::IsEmpty](../Topic/CObList::IsEmpty.md)|リストの状態が空 \(要素がない\) かどうかを調べます。|  
|[CObList::RemoveAll](../Topic/CObList::RemoveAll.md)|リストからすべての要素を削除します。|  
|[CObList::RemoveAt](../Topic/CObList::RemoveAt.md)|位置で指定されたこの一覧から要素を削除します。|  
|[CObList::RemoveHead](../Topic/CObList::RemoveHead.md)|リストの先頭にある要素を削除します。|  
|[CObList::RemoveTail](../Topic/CObList::RemoveTail.md)|リストの末尾にある要素を削除します。|  
|[CObList::SetAt](../Topic/CObList::SetAt.md)|指定した位置に要素を設定します。|  
  
## 解説  
 `CObList` の一覧には、二重リンク リストのようになります。  
  
 **POSITION** 型の変数は、リストのキーです。  反復子とブックマークとして場所を保持するリストを順番に検索するに **POSITION** の変数を使用できます。  ただし、インデックス位置は、と同じではありません。  
  
 要素の挿入はリストの先頭、末尾、および既知の **POSITION**に非常に高速です。  シーケンシャル サーチに、値またはインデックスで要素を調べて必要です。  この検索はリストが分かかることがあります。  
  
 `CObList` は、要素のシリアル化とダンプをサポートするために `IMPLEMENT_SERIAL` のマクロが組み込まれています。  `CObject` のポインターのリストがオーバーロードされた挿入演算子を使用して、または `Serialize` のメンバー関数のアーカイブに格納されている場合、`CObject` の各要素では、シリアル化されます。  
  
 リストで `CObject` の各要素をダンプする必要があるときは、1 にダンプ コンテキストの深さを設定するより大きい。  
  
 `CObList` のオブジェクトを削除または要素が削除されたときに、`CObject` のポインターだけが削除されますが、参照する、オブジェクト。  
  
 `CObList`から独自のクラスを派生させることができます。  `CObject`から派生したオブジェクトへのポインターを保持するための、新しいリスト クラスは、新しいデータ メンバー、および新しいメンバー関数を追加します。  `CObject` のすべてのポインターの挿入を使用すると、リストが、タイプ セーフでないことに注意してください。  
  
> [!NOTE]
>  リストをシリアル化する場合は、派生クラスの実装で [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) のマクロを使用する必要があります。  
  
 `CObList`の使用の詳細については、" " [&#91;コレクション&#93;](../../mfc/collections.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CObList`  
  
## 必要条件  
 **Header:** afxcoll.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CStringList クラス](../Topic/CStringList%20Class.md)   
 [CPtrList クラス](../Topic/CPtrList%20Class.md)
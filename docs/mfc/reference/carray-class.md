---
title: "CArray クラス | Microsoft Docs"
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
  - "CArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [C++], クラス"
  - "CArray クラス"
  - "コレクション クラス, テンプレート ベースの"
  - "テンプレート, コレクション クラス"
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
caps.latest.revision: 33
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArray クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C 言語の配列に似ていますが、必要に応じて動的に配列の縮小や拡張ができます。  
  
## 構文  
  
```  
template < class TYPE, class ARG_TYPE = const TYPE& >   
class CArray :   
   public CObject  
```  
  
#### パラメーター  
 `TYPE`  
 配列に格納されるオブジェクトの型を指定するテンプレート パラメーター。  `TYPE` は、`CArray` が返すパラメーターです。  
  
 `ARG` *\_* `TYPE`  
 配列に格納されているオブジェクトにアクセスするときに使われる引数の型を指定するテンプレート パラメーター。  通常、`TYPE` への参照です。  `ARG_TYPE` は、`CArray` に渡すパラメーターです。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CArray::CArray](../Topic/CArray::CArray.md)|空の配列を生成します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CArray::Add](../Topic/CArray::Add.md)|配列の最後に要素を追加します。必要に応じて配列を拡張します。|  
|[CArray::Append](../Topic/CArray::Append.md)|配列に別の配列を追加します。必要に応じて配列を拡張します。|  
|[CArray::Copy](../Topic/CArray::Copy.md)|配列に別の配列をコピーします。必要に応じて配列を拡張します。|  
|[CArray::ElementAt](../Topic/CArray::ElementAt.md)|配列内のポインター要素への一時的な参照を返します。|  
|[CArray::FreeExtra](../Topic/CArray::FreeExtra.md)|現在の上限を超える領域の未使用メモリ全体を解放します。|  
|[CArray::GetAt](../Topic/CArray::GetAt.md)|指定したインデックス位置にある値を返します。|  
|[CArray::GetCount](../Topic/CArray::GetCount.md)|配列の要素数を取得します。|  
|[CArray::GetData](../Topic/CArray::GetData.md)|配列内の要素にアクセスできます。  **NULL** の場合もあります。|  
|[CArray::GetSize](../Topic/CArray::GetSize.md)|配列の要素数を取得します。|  
|[CArray::GetUpperBound](../Topic/CArray::GetUpperBound.md)|有効なインデックスの最大値を返します。|  
|[CArray::InsertAt](../Topic/CArray::InsertAt.md)|配列の指定したインデックス位置に要素 \(または別の配列のすべての要素\) を挿入します。|  
|[CArray::IsEmpty](../Topic/CArray::IsEmpty.md)|配列が空かどうかを判断します。|  
|[CArray::RemoveAll](../Topic/CArray::RemoveAll.md)|配列のすべての要素を削除します。|  
|[CArray::RemoveAt](../Topic/CArray::RemoveAt.md)|指定したインデックス位置にある要素を削除します。|  
|[CArray::SetAt](../Topic/CArray::SetAt.md)|指定したインデックス位置に値を設定します。配列の拡張はできません。|  
|[CArray::SetAtGrow](../Topic/CArray::SetAtGrow.md)|指定したインデックス位置に値を設定します。必要に応じて配列を拡張します。|  
|[CArray::SetSize](../Topic/CArray::SetSize.md)|配列に格納する要素数を設定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CArray::operator](../Topic/CArray::operator.md)|指定したインデックス位置の要素を設定または取得します。|  
  
## 解説  
 配列のインデックスは常に 0 から始まります。  インデックスの上限を固定するか、現在の上限を越えて要素を追加したときに配列を拡張できるようにするかを指定できます。  一部の要素が無効 \(NULL\) の場合でも、メモリは上限まで継続的に割り当てられます。  
  
> [!NOTE]
>  `CArray` オブジェクトのサイズを変更するメソッドや、オブジェクトに要素を追加するメソッドは、ほとんどの場合、[memcpy\_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) を使用して要素を移動します。  `memcpy_s` は、コンストラクターを呼び出す必要のあるオブジェクトと互換性がないため、これは問題になります。  `CArray` 内の項目が `memcpy_s` と互換性がない場合は、適切なサイズで新しい `CArray` を作成する必要があります。  その後、新しい配列にデータを追加するには、[CArray::Copy](../Topic/CArray::Copy.md) と [CArray::SetAt](../Topic/CArray::SetAt.md) を使用する必要があります。これらのメソッドでは、`memcpy_s` ではなく代入演算子が使用されます。  
  
 C 言語の配列と同じように、`CArray` の要素にインデックスを使ってアクセスする時間は一定で、配列のサイズとは無関係です。  
  
> [!TIP]
>  配列を使う場合は、あらかじめ [SetSize](../Topic/CArray::SetSize.md) 関数で配列のサイズを確定し、そのメモリを確保します。  `SetSize` を使用せずに要素を配列に追加すると、配列が頻繁に再割り当てされ、コピーされます。  頻繁に再割り当てとコピーを行うとパフォーマンスが低下し、メモリ断片化の原因になります。  
  
 配列の各要素をダンプする必要があるときは、[CDumpContext](../../mfc/reference/cdumpcontext-class.md) オブジェクトの深さのパラメーターを 1 以上に設定します。  
  
 このクラスの一部のメンバー関数は、グローバルなヘルパー関数を呼び出します。したがって、`CArray` クラスの主な用途に合わせて、これらのヘルパー関数をカスタマイズする必要があります。  「MFC マクロとグローバル」の「[コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md)」を参照してください。  
  
 配列クラスの派生は、リストの派生と同様です。  
  
 `CArray` を使用する方法の詳細については、「[コレクション](../../mfc/collections.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CArray`  
  
## 必要条件  
 `Header:` afxtempl.h  
  
## 参照  
 [MFC のサンプルが収集されます](../../top/visual-cpp-samples.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObArray クラス](../../mfc/reference/cobarray-class.md)   
 [コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md)
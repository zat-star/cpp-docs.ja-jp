---
title: "CObArray クラス | Microsoft Docs"
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
  - "CObArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [C++], オブジェクト型"
  - "配列 [C++], ポインター"
  - "CObArray クラス"
  - "オブジェクトの配列, CObArray クラス"
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObArray クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CObject` ポインターの配列をサポートします。  
  
## 構文  
  
```  
class CObArray : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|`CObject` ポインターの空の配列を生成します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CObArray::Add](../Topic/CObArray::Add.md)|配列の最後に要素を追加します。必要に応じて配列を拡張します。|  
|[CObArray::Append](../Topic/CObArray::Append.md)|配列に別の配列を追加します; 配列を必要に応じて。|  
|[CObArray::Copy](../Topic/CObArray::Copy.md)|配列に別の配列をコピーします。必要に応じて配列を拡張します。|  
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|配列内のポインター要素への一時的な参照を返します。|  
|[CObArray::FreeExtra](../Topic/CObArray::FreeExtra.md)|現在の上限を超える領域の未使用メモリ全体を解放します。|  
|[CObArray::GetAt](../Topic/CObArray::GetAt.md)|指定したインデックス位置にある値を返します。|  
|[CObArray::GetCount](../Topic/CObArray::GetCount.md)|配列の要素数を取得します。|  
|[CObArray::GetData](../Topic/CObArray::GetData.md)|配列内の要素にアクセスできます。  **NULL** の場合もあります。|  
|[CObArray::GetSize](../Topic/CObArray::GetSize.md)|配列の要素数を取得します。|  
|[CObArray::GetUpperBound](../Topic/CObArray::GetUpperBound.md)|有効なインデックスの最大値を返します。|  
|[CObArray::InsertAt](../Topic/CObArray::InsertAt.md)|配列の指定したインデックス位置に要素 \(または別の配列のすべての要素\) を挿入します。|  
|[CObArray::IsEmpty](../Topic/CObArray::IsEmpty.md)|配列が空であるかどうかを判定します。|  
|[CObArray::RemoveAll](../Topic/CObArray::RemoveAll.md)|配列のすべての要素を削除します。|  
|[CObArray::RemoveAt](../Topic/CObArray::RemoveAt.md)|指定したインデックス位置にある要素を削除します。|  
|[CObArray::SetAt](../Topic/CObArray::SetAt.md)|指定したインデックス位置に値を設定します。配列の拡張はできません。|  
|[CObArray::SetAtGrow](../Topic/CObArray::SetAtGrow.md)|指定したインデックス位置に値を設定します。必要に応じて配列を拡張します。|  
|[CObArray::SetSize](../Topic/CObArray::SetSize.md)|配列に格納する要素数を設定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CObArray::operator](../Topic/CObArray::operator.md)|指定したインデックス位置の要素を設定または取得します。|  
  
## 解説  
 これらのオブジェクトの配列は C の配列に似ていますが、必要に応じて動的に縮小し、拡張できます。  
  
 配列のインデックスは常に 0 から始まります。  現在の境界を越えて要素を追加するかどうかを上限を修正するには、境界または配置するように配列を決定できます。  一部の要素が無効 \(NULL\) の場合でも、メモリは上限まで継続的に割り当てられます。  
  
 Win32 の下に、`CObArray` のオブジェクトのサイズは、使用できるメモリ内だけに制限されます。  
  
 C 言語の配列と同じように、`CObArray` の要素にインデックスを使ってアクセスする時間は一定で、配列のサイズとは無関係です。  
  
 `CObArray` は、要素のシリアル化とダンプをサポートするために `IMPLEMENT_SERIAL` のマクロが組み込まれています。  `CObject` のポインター配列がオーバーロードされた挿入演算子を使用して、または `Serialize` のメンバー関数のアーカイブに格納されている場合、`CObject` の各要素は、配列のインデックスとともに、シリアル化されます。  
  
 配列で `CObject` の各要素をダンプする必要があるときは、を 1 に `CDumpContext` のオブジェクトの深さを設定するより大きい。  
  
 `CObArray` のオブジェクトを削除または要素が削除されたときに、`CObject` のポインターだけが削除されますが、参照する、オブジェクト。  
  
> [!NOTE]
>  配列を使用する前に、サイズを設定し、そのメモリを割り当てるために `SetSize` を使用します。  `SetSize` を使用せずに要素を配列に追加すると、配列が頻繁に再割り当てされ、コピーされます。  頻繁に再割り当てとコピーを行うとパフォーマンスが低下し、メモリ断片化の原因になります。  
  
 配列クラスの派生は、リストの派生に似ています。  特殊な目的のクラスの派生リストの詳細については、" " [&#91;コレクション&#93;](../../mfc/collections.md)を参照してください。  
  
> [!NOTE]
>  配列をシリアル化する場合は、派生クラスの実装で `IMPLEMENT_SERIAL` のマクロを使用する必要があります。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CObArray`  
  
## 必要条件  
 **Header:** afxcoll.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CStringArray クラス](../../mfc/reference/cstringarray-class.md)   
 [CPtrArray クラス](../../mfc/reference/cptrarray-class.md)   
 [CByteArray クラス](../../mfc/reference/cbytearray-class.md)   
 [CWordArray クラス](../../mfc/reference/cwordarray-class.md)   
 [CDWordArray クラス](../Topic/CDWordArray%20Class.md)
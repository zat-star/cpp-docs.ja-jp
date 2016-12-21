---
title: "CWordArray クラス | Microsoft Docs"
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
  - "CWordArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [C++], インデックス付き"
  - "CWordArray クラス"
  - "インデックス付き配列"
  - "INT"
  - "UINT"
  - "WORD データ型"
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
caps.latest.revision: 26
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWordArray クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

16 ビットのワードの配列をサポートします。  
  
## 構文  
  
```  
class CWordArray : public CObject  
```  
  
## メンバー  
 `CWordArray` のメンバー関数は [CObArray](../../mfc/reference/cobarray-class.md)クラスのメンバー関数に似ています。  メンバー関数については `CObArray` クラスの説明を参照してください。  関数のパラメーターまたは戻り値として [CObject](../Topic/CObject%20Class.md) のポインターが使われている場合は、**word**に置き換えてください。  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 たとえば、への移動  
  
 `WORD CWordArray::GetAt( int <nIndex> ) const;`  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|空の配列を生成します。|  
  
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
 `CWordArray` は、要素のシリアル化とダンプをサポートするために [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) のマクロが組み込まれています。  ワードの配列がオーバーロードされた挿入演算子を使用して、または [CObject::Serialize](../Topic/CObject::Serialize.md) のメンバー関数のアーカイブに格納されている場合、各要素は、シリアル化されます。  
  
> [!NOTE]
>  配列を使用する前に、サイズを設定し、そのメモリを割り当てるために `SetSize` を使用します。  `SetSize` を使用せずに要素を配列に追加すると、配列が頻繁に再割り当てされ、コピーされます。  頻繁に再割り当てとコピーを行うとパフォーマンスが低下し、メモリ断片化の原因になります。  
  
 配列の各要素をダンプする必要がある場合、は 1 にダンプ コンテキストの深さを設定するより大きい。  
  
 `CWordArray`の使用の詳細については、" " [&#91;コレクション&#93;](../../mfc/collections.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CWordArray`  
  
## 必要条件  
 **Header:** afxcoll.h  
  
## 参照  
 [MFC のサンプルが収集されます](../../top/visual-cpp-samples.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)
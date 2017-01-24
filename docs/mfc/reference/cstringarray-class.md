---
title: "CStringArray クラス | Microsoft Docs"
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
  - "CStringArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [C++], 文字列"
  - "CStringArray クラス"
  - "文字列配列"
  - "文字列 [C++], コレクション"
ms.assetid: 6c637e06-bba8-4c08-b0fc-cf8cb067ce34
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringArray クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CString](../../atl-mfc-shared/using-cstring.md) オブジェクトの配列をサポートします。  
  
## 構文  
  
```  
class CStringArray : public CObject  
```  
  
## メンバー  
 `CStringArray` のメンバー関数は、[CObArray](../../mfc/reference/cobarray-class.md) クラスのメンバー関数とほぼ同じです。  メンバー関数については `CObArray` クラスの説明を参照してください。  戻り値として `CObject` ポインターが使われている場合は、[CString](../../atl-mfc-shared/using-cstring.md) オブジェクトに置き換えます \([CString](../../atl-mfc-shared/using-cstring.md) ポインターではありません\)。  関数パラメーターとして `CObject` ポインターが使われている場合は、`LPCTSTR` に置き換えます。  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 たとえば、次のように変換します。  
  
 `CString CStringArray::GetAt( int <nIndex> ) const;`  
  
 および  
  
 `void SetAt( int <nIndex>, CObject* <newElement> )`  
  
 次のように変換します。  
  
 `void SetAt( int <nIndex>, LPCTSTR <newElement> )`  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|空の配列を生成します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CObArray::Add](../Topic/CObArray::Add.md)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|  
|[CObArray::Append](../Topic/CObArray::Append.md)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|  
|[CObArray::Copy](../Topic/CObArray::Copy.md)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|  
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|配列内の要素ポインターへの一時的な参照を返します。|  
|[CObArray::FreeExtra](../Topic/CObArray::FreeExtra.md)|現在の上限を超えている未使用のメモリをすべて解放します。|  
|[CObArray::GetAt](../Topic/CObArray::GetAt.md)|指定されたインデックス位置にある値を返します。|  
|[CObArray::GetCount](../Topic/CObArray::GetCount.md)|この配列内の要素の数を取得します。|  
|[CObArray::GetData](../Topic/CObArray::GetData.md)|配列内の要素へのアクセスを許可します。  **NULL** にすることができます。|  
|[CObArray::GetSize](../Topic/CObArray::GetSize.md)|この配列内の要素の数を取得します。|  
|[CObArray::GetUpperBound](../Topic/CObArray::GetUpperBound.md)|有効な最大のインデックスを返します。|  
|[CObArray::InsertAt](../Topic/CObArray::InsertAt.md)|指定されたインデックス位置に要素 \(または別の配列内のすべての要素\) を挿入します。|  
|[CObArray::IsEmpty](../Topic/CObArray::IsEmpty.md)|配列が空かどうかを判別します。|  
|[CObArray::RemoveAll](../Topic/CObArray::RemoveAll.md)|この配列からすべての要素を削除します。|  
|[CObArray::RemoveAt](../Topic/CObArray::RemoveAt.md)|特定のインデックス位置にある要素を削除します。|  
|[CObArray::SetAt](../Topic/CObArray::SetAt.md)|指定されたインデックスの値を設定します。配列は大きくできません。|  
|[CObArray::SetAtGrow](../Topic/CObArray::SetAtGrow.md)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|  
|[CObArray::SetSize](../Topic/CObArray::SetSize.md)|この配列に含まれる要素の数を設定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CObArray::operator](../Topic/CObArray::operator.md)|指定されたインデックス位置にある要素を設定または取得します。|  
  
## 解説  
 `CStringArray` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。  `CString` オブジェクトの配列がアーカイブに格納される場合、オーバーロードされた挿入演算子または `Serialize` メンバー関数によって、各要素は順にシリアル化されます。  
  
> [!NOTE]
>  配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。  `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。  頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。  
  
 配列内の個別の文字列要素をダンプする必要があるときは、ダンプ コンテキストの深さを 1 以上に設定する必要があります。  
  
 `CString` 配列が削除されたとき、またはその要素が削除されたときは、文字列メモリは状況に応じて解放されます。  
  
 `CStringArray` の使い方の詳細については、「[コレクション クラス](../../mfc/collections.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CStringArray`  
  
## 必要条件  
 **ヘッダー:** afxcoll.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)
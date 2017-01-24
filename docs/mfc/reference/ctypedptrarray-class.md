---
title: "CTypedPtrArray クラス | Microsoft Docs"
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
  - "CTypedPtrArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrArray クラス"
  - "ポインター配列"
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTypedPtrArray クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CPtrArray` クラスまたは `CObArray` クラスのオブジェクトに対してタイプセーフな "ラッパー" を提供します。  
  
## 構文  
  
```  
template< class BASE_CLASS, class TYPE >  
class CTypedPtrArray : public BASE_CLASS  
```  
  
#### パラメーター  
 `BASE_CLASS`  
 型指定されたポインターの配列クラスの基本クラス; 配列クラスはである必要があります \(`CObArray` か `CPtrArray`\)。  
  
 `TYPE`  
 基本クラスの配列に格納されている要素の型。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CTypedPtrArray::Add](../Topic/CTypedPtrArray::Add.md)|配列の末尾に新しい要素を追加します。  配列を必要に応じて|  
|[CTypedPtrArray::Append](../Topic/CTypedPtrArray::Append.md)|別の最後に 1 個の配列のコンテンツを追加します。  配列を必要に応じて|  
|[CTypedPtrArray::Copy](../Topic/CTypedPtrArray::Copy.md)|配列に別の配列をコピーします。必要に応じて配列を拡張します。|  
|[CTypedPtrArray::ElementAt](../Topic/CTypedPtrArray::ElementAt.md)|配列内のポインター要素への一時的な参照を返します。|  
|[CTypedPtrArray::GetAt](../Topic/CTypedPtrArray::GetAt.md)|指定したインデックス位置にある値を返します。|  
|[CTypedPtrArray::InsertAt](../Topic/CTypedPtrArray::InsertAt.md)|配列の指定したインデックス位置に要素 \(または別の配列のすべての要素\) を挿入します。|  
|[CTypedPtrArray::SetAt](../Topic/CTypedPtrArray::SetAt.md)|指定したインデックス位置に値を設定します。配列の拡張はできません。|  
|[CTypedPtrArray::SetAtGrow](../Topic/CTypedPtrArray::SetAtGrow.md)|指定したインデックス位置に値を設定します。必要に応じて配列を拡張します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CTypedPtrArray::operator](../Topic/CTypedPtrArray::operator.md)|指定したインデックス位置の要素を設定または取得します。|  
  
## 解説  
 `CPtrArray` か `CObArray`ではなく `CTypedPtrArray` を使用すると、C\+\+ の型チェック機能のヘルプには対応していないポインター型によるエラーがなくなります。  
  
 また、`CTypedPtrArray` ラッパーは `CObArray` か `CPtrArray`を使用して必要なキャストの多くを実行します。  
  
 `CTypedPtrArray` のすべての関数がインラインであるため、このテンプレートの使用は、コードのサイズや速度に影響を与えません。  
  
 `CTypedPtrArray`の使用の詳細については、" " [&#91;コレクション&#93;](../../mfc/collections.md) と [テンプレート ベースのクラス](../Topic/Template-Based%20Classes.md)を参照してください。  
  
## 継承階層  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## 必要条件  
 **Header:** afxtempl.h  
  
## 参照  
 [MFC のサンプルが収集されます](../../top/visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPtrArray クラス](../../mfc/reference/cptrarray-class.md)   
 [CObArray クラス](../../mfc/reference/cobarray-class.md)
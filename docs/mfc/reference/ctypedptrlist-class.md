---
title: "CTypedPtrList クラス | Microsoft Docs"
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
  - "CTypedPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrList クラス"
  - "リンクされたリスト [C++]"
  - "リスト [C++]"
  - "ポインター リスト"
  - "テンプレート クラス, CTypedPtrList クラス"
  - "タイプ セーフなコレクション"
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTypedPtrList クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CPtrList` クラスのオブジェクトに対してタイプ セーフな "ラップ" が用意されています。  
  
## 構文  
  
```  
template< class BASE_CLASS, class TYPE >  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### パラメーター  
 `BASE_CLASS`  
 型指定されたポインターのリスト クラスの基本クラス; ポインターのリスト クラスはである必要があります \(`CObList` か `CPtrList`\)。  
  
 `TYPE`  
 基本クラス リストに格納されている要素の型。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CTypedPtrList::AddHead](../Topic/CTypedPtrList::AddHead.md)|要素 \(またはほかのリストのすべての要素\) をリストの先頭に追加します \(その要素を新たに先頭とします\)。|  
|[CTypedPtrList::AddTail](../Topic/CTypedPtrList::AddTail.md)|要素 \(またはほかのリストのすべての要素\) をリストの末尾に追加します \(その要素を新たに末尾とします\)。|  
|[CTypedPtrList::GetAt](../Topic/CTypedPtrList::GetAt.md)|指定した位置の要素を取得します。|  
|[CTypedPtrList::GetHead](../Topic/CTypedPtrList::GetHead.md)|リストの先頭要素を返します。リストが空のときは使用できません。|  
|[CTypedPtrList::GetNext](../Topic/CTypedPtrList::GetNext.md)|次の要素を順番に取得します。|  
|[CTypedPtrList::GetPrev](../Topic/CTypedPtrList::GetPrev.md)|順次アクセスするときの直前の要素を取得します。|  
|[CTypedPtrList::GetTail](../Topic/CTypedPtrList::GetTail.md)|リストの末尾要素を返します。リストが空のときは使用できません。|  
|[CTypedPtrList::RemoveHead](../Topic/CTypedPtrList::RemoveHead.md)|リストの先頭にある要素を削除します。|  
|[CTypedPtrList::RemoveTail](../Topic/CTypedPtrList::RemoveTail.md)|リストの末尾にある要素を削除します。|  
|[CTypedPtrList::SetAt](../Topic/CTypedPtrList::SetAt.md)|指定した位置に要素を設定します。|  
  
## 解説  
 `CObList` か `CPtrList`ではなく `CTypedPtrList` を使用すると、C\+\+ の型チェック機能のヘルプには対応していないポインター型によるエラーがなくなります。  
  
 また、`CTypedPtrList` ラッパーは `CObList` か `CPtrList`を使用して必要なキャストの多くを実行します。  
  
 `CTypedPtrList` のすべての関数がインラインであるため、このテンプレートの使用は、コードのサイズや速度に影響を与えません。  
  
 `CObList` から派生したリストをシリアル化できますが `CPtrList` から派生したクラスはできません。  
  
 `CTypedPtrList` のオブジェクトを削除または要素が削除されたときに、ポインターだけが削除されます、参照する、エンティティです。  
  
 `CTypedPtrList`の使用の詳細については、" " [&#91;コレクション&#93;](../../mfc/collections.md) と [テンプレート ベースのクラス](../Topic/Template-Based%20Classes.md)を参照してください。  
  
## 使用例  
 この例では `CTypedPtrList`のインスタンスを作成し、オブジェクトを 1 つ追加し、ディスクにリストをシリアル化し、オブジェクトを削除します:  
  
 [!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/CPP/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/CPP/ctypedptrlist-class_2.cpp)]  
  
## 継承階層  
 `BASE_CLASS`  
  
 `_CTypedPtrList`  
  
 `CTypedPtrList`  
  
## 必要条件  
 **Header:** afxtempl.h  
  
## 参照  
 [MFC のサンプルが収集されます](../../top/visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPtrList クラス](../Topic/CPtrList%20Class.md)   
 [CObList クラス](../../mfc/reference/coblist-class.md)
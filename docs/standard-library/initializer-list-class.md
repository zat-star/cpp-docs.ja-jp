---
title: "initializer_list Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 1f2c0ff4-5636-4f79-b008-e75426e3d2ab
caps.latest.revision: 17
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# initializer_list Class
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

すべてのメンバーが指定された型である要素の配列にアクセスできます。  
  
## 構文  
  
```cpp  
template<  
    class Type >  
    class initializer_list  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`_Elem`|`initializer_list` に格納される要素のデータ型。|  
|`_First`|`initializer_list` の最初の要素へのポインター。|  
|`_Last`|`initializer_list` の最後の要素へのポインター。|  
  
## 解説  
 `initializer_list` は、中かっこで囲んだ初期化子リストを使用して構築できます。  
  
```cpp  
initializer_list<int> i1{ 1, 2, 3, 4 };  
```  
  
 関数のシグネチャで `initializer_list` が必要になる場合、コンパイラでは、中かっこで囲んだ初期化子リストが同種の要素を含んでいると、このリストは必ず `initializer_list` に変換されます。  `initializer_list` の使用に関する詳細については、「[均一な初期化とコンストラクターのデリゲート](../cpp/uniform-initialization-and-delegating-constructors.md)」をご覧ください。  
  
### コンストラクター  
  
|||  
|-|-|  
|[initializer\_list](../Topic/forward_list::forward_list.md)|`initializer_list` 型のオブジェクトを構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|value\_type|`initializer_list` 内の要素の型。|  
|参照|`initializer_list` 内の要素への参照を提供する型。|  
|const\_reference|`initializer_list` 内の要素への定数参照を提供する型。|  
|size\_type|`initializer_list` 内の要素の数を表す型。|  
|iterator|`initializer_list` に反復子を提供する型。|  
|const\_iterator|`initializer_list` に定数反復子を提供する型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[begin](../Topic/initializer_list::begin.md)|`initializer_list` 内の最初の要素へのポインターを返します。|  
|[End](../Topic/initializer_list::end.md)|`initializer_list` 内の最後の要素の 1 つ後ろへのポインターを返します。|  
|[size](../Topic/initializer_list::size.md)|`initializer_list` 内の要素数を返します。|  
  
## 必要条件  
 **ヘッダー:** \<initializer\_list\>  
  
 **名前空間:** std  
  
## 参照  
 [\<forward\_list\>](../standard-library/forward-list.md)
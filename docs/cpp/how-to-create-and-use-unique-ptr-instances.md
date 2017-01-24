---
title: "方法: unique_ptr インスタンスを作成して使用する | Microsoft Docs"
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
ms.assetid: 9a373030-e587-452f-b9a5-c5f9d58b7673
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: unique_ptr インスタンスを作成して使用する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[unique\_ptr](../standard-library/unique-ptr-class.md) は、ポインターを共有しません。  別の `unique_ptr` にコピーすることも、値によって関数に渡すことも、コピーの作成が必要な標準テンプレート ライブラリ \(STL: Standard Template Library\) のアルゴリズムで使用することもできません。  `unique_ptr` ができるのは移動だけです。  この場合、メモリ リソースの所有権は別の `unique_ptr` に移動し、元の `unique_ptr` はそれ以降、所有権を失います。  複数の所有者がオブジェクトを所有するとプログラム ロジックが複雑になるため、所有者を 1 人に制限することをお勧めします。  したがって、プレーンな C\+\+ オブジェクト用のスマート ポインターが必要な場合は `unique_ptr` を使用し、`unique_ptr` を構成する場合は [make\_unique](../Topic/make_unique.md) ヘルパー関数を使用します。  
  
 次の図では、2 つの `unique_ptr` のインスタンス間での所有権の移転を示します。  
  
 ![unique&#95;ptr の所有権の移動](../cpp/media/unique_ptr.png "unique\_ptr")  
  
 `unique_ptr` は、STL の `<memory>` ヘッダーで定義されます。  これは、生のポインターと同じくらい効率的で、STL コンテナーで使用できます。  STL コンテナーに `unique_ptr` インスタンスを追加すると、`unique_ptr` の移動コンストラクターによってコピー操作が不要になるため効率的です。  
  
## 使用例  
 次の例では、`unique_ptr` インスタンスを作成し、関数間で渡す方法を示します。  
  
 [!code-cpp[stl_smart_pointers#210](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_1.cpp)]  
  
 これらの例は、`unique_ptr` の基本的な機能として、移動はできるが、コピーはできないことを示しています。「移動」は `unique_ptr` に所有権を移転し、元の `unique_ptr` をリセットします。  
  
## 使用例  
 次の例では、`unique_ptr` インスタンスを作成し、ベクター内で使用する方法を示します。  
  
 [!code-cpp[stl_smart_pointers#211](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_2.cpp)]  
  
 ループの範囲で、`unique_ptr` が参照によって渡されることに注意してください。  ここで値によって渡そうとすると、`unique_ptr` コピー コンストラクターが削除されるため、コンパイラによってエラーがスローされます。  
  
## 使用例  
 次の例では、クラス メンバーである `unique_ptr` を初期化する方法を示しています。  
  
 [!code-cpp[stl_smart_pointers#212](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_3.cpp)]  
  
## 使用例  
 [make\_unique](../Topic/make_unique.md) を使用することで、配列への `unique_ptr` を作成できます。ただし、`make_unique` で配列要素を初期化することはできません。  
  
 [!code-cpp[stl_smart_pointers#213](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_4.cpp)]  
  
 その他の例については、「[make\_unique](../Topic/make_unique.md)」を参照してください。  
  
## 参照  
 [スマート ポインター](../cpp/smart-pointers-modern-cpp.md)   
 [make\_unique](../Topic/make_unique.md)
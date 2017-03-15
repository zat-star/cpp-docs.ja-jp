---
title: "リソースを所有するオブジェクト (RAII) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# リソースを所有するオブジェクト (RAII)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

所有されたリソース オブジェクトことを確認します。  この原則は、エイリアス「リソース取得。初期化」または「RAII」。  
  
## 例  
 スレッドが所有する個別の名前付きオブジェクトへのコンストラクター引数として、「new」オブジェクトを渡します \(ほぼ必ず unique\_ptr\)。  
  
```cpp  
void f() {  
  unique_ptr<widget> p( new widget(…) );  
  my_class x( new widget() );  
  …  
} // automatic destruction and deallocation for both widget objects  
  // automatic exception safety, as if “finally { p->dispose(); x.w.dispose(); }”  
  
```  
  
 常にすぐにそれを所有する別のオブジェクトに新しいリソースを渡します。  
  
```cpp  
void g() {  
  other_class y( OpenFile() );  
  …  
} // automatic closing and release for file resource  
  // automatic exception safety, as if “finally { y.file.dispose(); }”  
  
```  
  
## 参照  
 [C\+\+ へようこそ](../Topic/Welcome%20Back%20to%20C++%20\(Modern%20C++\).md)   
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)
---
title: "キャスト | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "キャスト"
  - "クラス [C++], ポリモーフィズム"
  - "強制変換"
  - "dynamic cast 演算子"
  - "polymorphic クラス"
  - "static cast 演算子"
  - "仮想関数, 派生クラス"
ms.assetid: 3dbeb06e-2f4b-4693-832d-624bc8ec95de
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# キャスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 言語では、仮想関数を含む基底クラスからクラスが派生している場合は、その基底クラスの型へのポインターを使用して、派生クラス オブジェクトに存在する仮想関数の実装を呼び出すことができると規定されています。  仮想関数を含むクラスは、"ポリモーフィックなクラス" と呼ばれます。  
  
 派生クラスには派生元のすべての基底クラスの定義が完全に含まれるため、ポインターをクラスの階層構造の任意の基底クラスにキャストしても、安全です。  基底クラスへのポインターの場合は、下の階層にポインターを安全にキャストできる場合もあります。  ポイントされているオブジェクトが実際に基底クラスから派生した型である場合は、安全です。  この場合、実際のオブジェクトは "完全なオブジェクト" と呼ばれます。 基底クラスへのポインターは完全なオブジェクトの "サブオブジェクト" をポイントすると表現されます。  たとえば、次の図に示すクラスの階層構造を考えます。  
  
 ![クラスの階層構造](../cpp/media/vc38zz1.png "vc38ZZ1")  
クラスの階層構造  
  
 `C` 型のオブジェクトは、次の図に示すように視覚化できます。  
  
 ![B サブオブジェクトと A サブオブジェクトを持つクラス C](../cpp/media/vc38zz2.png "vc38ZZ2")  
B サブオブジェクトと A サブオブジェクトを持つクラス C  
  
 `C` クラスのインスタンスには、`B` サブオブジェクトと `A` サブオブジェクトがあります。  `A` サブオブジェクトと `B` サブオブジェクトを含む `C` のインスタンスは、「完全なオブジェクト」です。  
  
 実行時の型情報を使用すると、ポインターが実際に完全なオブジェクトをポイントしていて、階層内の別のオブジェクトをポイントするように安全にキャストできるかどうかを調べることができます。  [dynamic\_cast](../cpp/dynamic-cast-operator.md) 演算子は、こうした型のキャストを実行するために使用できます。  また、操作を安全にするために必要なランタイム チェックも実行します。  
  
 非ポリモーフィックな型の変換については、[static\_cast](../cpp/static-cast-operator.md) 演算子を使用できます \(このトピックでは、静的および動的なキャスト変換の違いと、それぞれの使用に適した場合について説明します\)。  
  
 ここでは、次のトピックについて説明します。  
  
-   [キャスト演算子](../cpp/casting-operators.md)  
  
-   [Run\-time type information \(ランタイム型情報\)](../Topic/Run-Time%20Type%20Information.md)  
  
## 参照  
 [式](../cpp/expressions-cpp.md)
---
title: "戻り値 (C++) | Microsoft Docs"
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
ms.assetid: 53583524-b337-4228-a9c6-c9bf516babe8
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 戻り値 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

64 ビットに収まるスカラー戻り値は、RAX \(\_\_m64 型を含む\) を通じて返されます。  float 型、double 型、および [\_\_m128](../Topic/__m128.md)、[\_\_m128i](../Topic/__m128i.md)、[\_\_m128d](../cpp/m128d.md) などのベクター型を含む非スカラー型は、XMM0 で返されます。  RAX や XMM0 で返される値の未使用ビットの状態は未定義です。  
  
 ユーザー定義型は、グローバル関数や静的メンバー関数からの値で返すことができます。  RAX で値によって返すには、ユーザー定義型の長さが 1、2、4、8、16、32、または 64 ビットでなければなりません。ユーザー定義型のコンストラクター、デストラクター、またはコピー代入演算子ではなく、プライベートまたは保護された非静的データ メンバーではなく、参照型の非静的データ メンバーではなく、基底クラスではなく、仮想関数ではありません。これらの要件を満たさないデータ メンバーでもありません。  \(これは、実質的には C\+\+03 POD 型の定義です。  C\+\+11 規格ではこの定義は変更されているので、このテストに `std::is_pod` を使うことはお勧めしません。\) それ以外の場合は、呼び出し元が、メモリを割り当て、最初の引数として戻り値のポインターを渡す必要があります。  後続する引数は、引数 1 つ分だけ右にシフトされます。  RAX 内の呼び出し先は同じポインターを返す必要があります。  
  
 以下の例は、宣言を指定して関数に対してパラメーターと戻り値を渡す方法を示しています。  
  
## 戻り値 1 – 64 ビットの結果の例  
  **\_\_int64 func1\(int a, float b, int c, int d, int e\);**  
**\/\/ 呼び出し元は a を RCX、b を XMM1、c を R8、d を R9 で渡し、e はスタックでプッシュされ、**  
**\/\/ 呼び出し先は RAX で \_\_int64 の結果を返します。**   
## 戻り値 2 – 128 ビットの結果の例  
  **\_\_m128 func2\(float a, double b, int c, \_\_m64 d\);**   
**\/\/ 呼び出し元は a を XMM0、b を XMM1、c を R8、d を R9 で渡し、**  
**\/\/ 呼び出し先は XMM0 で \_\_m128 の結果を返します。**   
## 戻り値の例 3 – ポインターによるユーザー型の結果  
  **struct Struct1 {**  
 **int j, k, l;    \/\/ Struct1 は 64 ビットを超えています。  };**  
**Struct1 func3\(int a, double b, int c, float d\);**   
**\/\/ 呼び出し元は、返される Struct1 のメモリを割り当て、RCX でポインターを渡し、**  
**\/\/ a を RDX、b を XMM2、c を R9 で渡し、d はスタックでプッシュされ、**   
**\/\/ 呼び出し先は Struct1 の結果へのポインターを RAX で返します。**    
## 戻り値の例 4 – 値によるユーザー型の結果  
  **struct Struct2 {**  
 **int j, k;    \/\/ Struct2 は 64 ビットに収まり、値によって返すための要件を満たしています。  };**  
**Struct2 func4\(int a, double b, int c, float d\);**   
**\/\/ 呼び出し元は、a を RCX、b を XMM1、c を R8、d を XMM3 で渡し、**   
**\/\/ 呼び出し先は値による Struct2 の結果を RAX で返します。**    
## 参照  
 [呼び出し規約](../build/calling-convention.md)
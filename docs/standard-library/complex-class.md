---
title: "complex クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "complex"
  - "std::complex"
  - "std.complex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "complex クラス"
  - "複素数"
ms.assetid: d6492e1c-5eba-4bc5-835b-2a88001a5868
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# complex クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、オブジェクトを格納している複素数の実数部を表すと 1 について説明します。虚数部を表す型 **\[種類\]**、1 の 2 つがオブジェクト。  
  
## 構文  
  
```  
  
   template<class   
   Type  
   >  
class complex  
```  
  
## 解説  
 クラス **\[種類\]** オブジェクト:  
  
-   従来の動作にパブリックな既定のコンストラクター、デストラクター、コピー コンストラクターと代入演算子があります。  
  
-   従来の動作のこのような値は Integer または decimal 値は型キャストを割り当てることができます。  
  
-   従来の動作の浮動小数点型に対して定義された定義し、必要に応じて算術演算子と数値演算関数。  
  
 特に、微妙な違いは、代入に続くコピーの構築と既定の構築中にない場合があります。  クラス **\[種類\]** オブジェクトの操作はいずれも例外をスローしない場合があります。  
  
 テンプレート クラスの複合型の明示的な特殊化は 3 個の浮動小数点型の場合にあります。  この実装では、他の型 **\[種類\]** の場合は値型 **\[種類\]**`.`の格納されたオブジェクトが割り当てられて **double** の結果が実際の計算の **double** に、型にキャストします。  
  
### コンストラクター  
  
|||  
|-|-|  
|[複合](../Topic/complex::complex.md)|指定実際および虚数部を使用して、または他の複素数のコピーとして複素数を構築します。|  
  
### Typedef  
  
|||  
|-|-|  
|[value\_type](../Topic/complex::value_type.md)|複素数の実際と虚数部を表すために使用されるデータ型を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[imag](../Topic/complex::imag.md)|複合型の虚数部を取得します。|  
|[real](../Topic/complex::real.md)|複素数の実際のコンポーネントを取得します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\*\=](../Topic/complex::operator*=.md)|複素数の実際と虚数部と複雑かどうかが同じ型である要素によって、複合対象の数が増加しています。|  
|[operator\+\=](../Topic/complex::operator+=.md)|ファイルを追加する複素数の実際と虚数部と追加した数値が複雑な場合も同じ型の可能性のある複合対象の数に数値を追加します。|  
|[operator\-\=](../Topic/complex::operator-=1.md)|ファイルを追加する複素数の実際と虚数部と描画数が複雑な場合も同じ型の可能性のある複合対象の数から数を描画します。|  
|[operator\/\=](../Topic/complex::operator-=2.md)|複素数の実際と虚数部と複雑かどうかが同じ型である除数で複合対象の数を区切ります。|  
|[operator\=](../Topic/complex::operator=.md)|割り当てられている複素数の実際と虚数部と割り当てられた数が複雑な場合も同じ型の可能性のある複合対象の数に数値を割り当てます。|  
  
## 必要条件  
 **ヘッダー**: \<複雑\>  
  
 **名前空間:** std  
  
## 参照  
 [complex Members](http://msdn.microsoft.com/ja-jp/d5c4466c-43a0-4817-aca1-9a5d492dae28)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
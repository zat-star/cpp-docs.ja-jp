---
title: "SafeInt 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "関数, SafeInt"
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
caps.latest.revision: 13
caps.handback.revision: 13
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeInt 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

SafeInt ライブラリには、[SafeInt クラス](../windows/safeint-class.md)のインスタンスを作成せずに使用できるいくつかの関数が用意されています。  整数オーバーフローが発生しないように単一の数値演算を保護する場合に、これらの関数を使用します。  複数の数値演算を保護する場合は、`SafeInt` オブジェクトを作成する必要があります。  これらの関数を繰り返し使用するよりも、`SafeInt` オブジェクトを作成した方が効率的です。  
  
 これらの関数により、2 つの異なる型のパラメーターに対して、比較または数値演算の実行が可能です。事前に同じ型に変換する必要はありません。  
  
 これらの関数にはそれぞれ、`T` と `U` という 2 種類のテンプレートの型があります。  これらの型は、ブール型、文字型、整数型のいずれかになります。  整数型は signed 型または unsigned 型となり、8 ～ 64 ビットの任意のサイズを使用できます。  
  
## このセクションの内容  
  
|関数|説明|  
|--------|--------|  
|[SafeAdd](../windows/safeadd.md)|オーバーフローを避けながら、2 つの数値を加算します。|  
|[SafeCast](../windows/safecast.md)|パラメーターの型を別の型にキャストします。|  
|[SafeDivide](../windows/safedivide.md)|ゼロ除算を避けながら、2 つの数値を除算します。|  
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [SafeNotEquals](../Topic/SafeNotEquals.md)|2 つの数値を比較します。  これらの関数を使用すると、型を変換せずに 2 つの異なる型の数値を比較できます。|  
|[SafeModulus](../windows/safemodulus.md)|2 つの数値に対して剰余演算を実行します。|  
|[SafeMultiply](../Topic/SafeMultiply.md)|オーバーフローが生じないように 2 つの数値を乗算します。|  
|[SafeSubtract](../windows/safesubtract.md)|オーバーフローが生じないように 2 つの数値を減算します。|  
  
## 関連項目  
  
|セクション|説明|  
|-----------|--------|  
|[SafeInt クラス](../windows/safeint-class.md)|`SafeInt` クラス。|  
|[SafeIntException クラス](../windows/safeintexception-class.md)|SafeInt ライブラリに固有の例外クラス。|
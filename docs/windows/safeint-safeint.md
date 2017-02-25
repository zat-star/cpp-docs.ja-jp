---
title: "SafeInt::SafeInt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeInt::SafeInt"
  - "SafeInt"
  - "SafeInt.SafeInt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeInt クラス, コンストラクター"
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# SafeInt::SafeInt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`SafeInt` オブジェクトを構築します。  
  
## 構文  
  
```  
SafeInt() throw  
  
SafeInt (  
   const T& i  
) throw ()  
  
SafeInt (  
   bool b  
) throw ()  
  
template <typename U>  
SafeInt (  
   const SafeInt <U, E>& u  
)  
  
I template <typename U>  
SafeInt (  
   const U& i  
)  
```  
  
#### パラメーター  
 \[入力\] `i`  
 新しい `SafeInt` オブジェクトの値。  この値は、T 型または U 型 \(コンストラクターに応じて決まります\) のパラメーターである必要があります。  
  
 \[入力\] `b`  
 新しい `SafeInt` オブジェクトのブール値。  
  
 \[入力\] `u`  
 U 型の `SafeInt`。  新しい `SafeInt` オブジェクトの値は `u` の値と同じですが、T 型になります。  
  
 U  
 `SafeInt` に格納されるデータの型。  ブール型、文字型、整数型のいずれかになります。  整数型の場合、signed 型でも unsigned 型でも構わず、サイズは 8 ～ 64 ビットの範囲で選択できます。  
  
## 解説  
 テンプレートの種類である `T` と `E` の詳細については、「[SafeInt クラス](../windows/safeint-class.md)」を参照してください。  
  
 コンストラクターの入力パラメーターである `i` または `u` は、ブール型、文字列型、整数型のいずれかにする必要があります。  それ以外の型のパラメーターを使用した場合、`SafeInt` クラスにより [static\_assert](../cpp/static-assert.md) が呼び出され、入力パラメーターが無効であることが通知されます。  
  
 `U` のテンプレート型を使用するコンストラクターでは、入力パラメーターが `T` によって指定された型に自動的に変換されます。  `SafeInt` クラスによるデータ変換では、データが失われません。  データを `T` 型に変換するときにデータの損失が避けられない場合は、エラー ハンドラー `E` に対して報告されます。  
  
 ブール値パラメーターから `SafeInt` を作成した場合、すぐに値を初期化する必要があります。  `SafeInt<bool> sb;` というコードを使って `SafeInt` を作成することはできません。  このコードを使用した場合、コンパイル エラーが発生します。  
  
## 必要条件  
 **ヘッダー:** safeint.h  
  
 **名前空間:** msl::utilities  
  
## 参照  
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)   
 [SafeIntException クラス](../windows/safeintexception-class.md)
---
title: "致命的なエラー C1017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1017"
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 致命的なエラー C1017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

整数定数式が無効です。  
  
 この `#if` ディレクティブには、式が与えられていません。または、定数に評価できない式が与えられています。  
  
 `#define` を使用して定義された定数は、`#if`、`#elif`、`#else` の各ディレクティブで使用する場合、整数定数として評価される値を持つ必要があります。  
  
 次の例では警告 C1017 が生成されます。  
  
```  
// C1017.cpp  
#define CONSTANT_NAME "YES"  
#if CONSTANT_NAME   // C1017  
#endif  
```  
  
 解決方法 :  
  
```  
// C1017b.cpp  
// compile with: /c  
#define CONSTANT_NAME 1  
#if CONSTANT_NAME  
#endif  
```  
  
 `CONSTANT_NAME` は整数ではなく文字列として評価されるため、`#if` ディレクティブによって致命的なエラー C1017 が生成されます。  
  
 また、プリプロセスによって未定義の定数が 0 と評価された場合にも同じエラーが発生します。  この場合は、以下の例に示すように予期しない結果になることがあります。  `YES` は未定義であるため、0 と評価されます。  `#if` 式 `CONSTANT_NAME` は false になり、`YES` の場合に使用されるコードはプリプロセッサによって削除されます。  さらに、`NO` も未定義 \(0\) であるため、`#elif` 式 `CONSTANT_NAME==NO` は true \(`0 == 0`\) になり、結果としてプリプロセッサはステートメントの `#elif` 部分のコードを残します。これは、予測した動作とは正反対になります。  
  
```  
// C1017c.cpp  
// compile with: /c  
#define CONSTANT_NAME YES  
#if CONSTANT_NAME  
   // Code to use on YES...  
#elif CONSTANT_NAME==NO  
   // Code to use on NO...  
#endif  
```  
  
 コンパイラがプリプロセッサ ディレクティブを処理する方法を確認するには、[\/P](../../build/reference/p-preprocess-to-a-file.md)、[\/E](../../build/reference/e-preprocess-to-stdout.md)、または [\/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) を使用してください。
---
title: "__ud2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__ud2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UD2 命令"
  - "__ud2 組み込み"
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __ud2
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 未定義命令が生成されます。  
  
## 構文  
  
```  
void __ud2();  
```  
  
## 解説  
 プロセッサが未定義の手順を実行すると無効なオペコードの例外が発生します。  
  
 `__ud2` の関数は `UD2` のマシン語命令とカーネル モードでのみ使用できます。  詳細については文書の検索「 Intel アーキテクチャのソフトウェア開発者の手動Volume 2: サイトの命令セットの参照です [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) 」。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__ud2`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 使用例  
 次の例は例外を発生させる未定義手順を実行します。  例外ハンドラーはゼロから 1 つリターン コードを変更します。  
  
```  
// __ud2_intrinsic.cpp  
#include <stdio.h>  
#include <intrin.h>  
#include <excpt.h>  
// compile with /EHa  
  
int main() {  
  
// Initialize the return code to 0.  
 int ret = 0;  
  
// Attempt to execute an undefined instruction.  
  printf("Before __ud2(). Return code = %d.\n", ret);  
  __try {   
  __ud2();   
  }  
  
// Catch any exceptions and set the return code to 1.  
  __except(EXCEPTION_EXECUTE_HANDLER){  
  printf("  In the exception handler.\n");  
  ret = 1;  
  }  
  
// Report the value of the return code.   
  printf("After __ud2().  Return code = %d.\n", ret);  
  return ret;  
}  
```  
  
  **\_\_ud2 の前 \(\)。  リターン コード \= 0 です。  例外ハンドラー。  \_\_ud2 \(\) の後。  リターン コード \= 1。**    
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)
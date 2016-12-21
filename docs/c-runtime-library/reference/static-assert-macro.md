---
title: "_STATIC_ASSERT マクロ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_STATIC_ASSERT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_STATIC_ASSERT マクロ"
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _STATIC_ASSERT マクロ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

結果が `FALSE`のときに、式をコンパイル時に評価され、エラーが発生します。  
  
## 構文  
  
```  
_STATIC_ASSERT(  
    booleanExpression  
);  
```  
  
#### パラメーター  
 `booleanExpression`  
 0 以外の \(`TRUE`\) または 0 に評価される式を含むポインター \(\) \(`FALSE`\)。  
  
## 解説  
 このマクロは [\_ASSERT と\_ASSERTE マクロ](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)に似ていますが、`booleanExpression` は実行時ではなくコンパイル時に評価されます。  `booleanExpression` が `FALSE` \(0\) の場合は、[コンパイラ エラー C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) が生成されます。  
  
## 使用例  
 この例では、`sizeof` が `int` より大きいかどうかは、チェックインとチェック アウト 2 バイトに `sizeof` が `long` 1 バイトか。  プログラムはコンパイルされず、`long` が 1 バイトを超えるため [コンパイラ エラー C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) を生成します。  
  
```  
// crt__static_assert.c  
  
#include <crtdbg.h>  
#include <stdio.h>  
  
_STATIC_ASSERT(sizeof(int) >= 2);  
_STATIC_ASSERT(sizeof(long) == 1);  // C2466  
  
int main()  
{  
    printf("I am sure that sizeof(int) will be >= 2: %d\n",  
        sizeof(int));  
    printf("I am not so sure that sizeof(long) == 1: %d\n",  
        sizeof(long));  
}  
```  
  
## 必要条件  
  
|マクロ|必須ヘッダー|  
|---------|------------|  
|`_STATIC_ASSERT`|\<crtdbg.h\>|  
  
## 同等の .NET Framework 関数  
 [System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [\_ASSERT、\_ASSERTE、\_ASSERT\_EXPR マクロ](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)
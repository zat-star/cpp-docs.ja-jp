---
title: "コンパイラの警告 (レベル 1) C4532 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4532"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4532"
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベル 1) C4532
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'続行' : 終了処理時に、\_\_finally\/finally ブロックからのジャンプの動作が定義されていません  
  
 次のいずれかのキーワードが見つかりました。  
  
-   [continue](../../cpp/continue-statement-cpp.md)  
  
-   [break](../../cpp/break-statement-cpp.md)  
  
-   [goto](../../cpp/goto-statement-cpp.md)  
  
 異常終了時に [\_\_finally](../../cpp/try-finally-statement.md) ブロックまたは [finally](../../dotnet/finally.md) ブロックの外部にジャンプします。  
  
 終了ハンドラー \(`__finally` ブロックまたは finally ブロック\) の実行中にスタックが展開される間に例外が発生した場合は、`__finally` ブロックが終了する前にコードが `__finally` ブロックの外部にジャンプすると、動作は未定義になります。  制御が展開中のコードに戻らないことがあるため、例外が正しく処理されない可能性があります。  
  
 **\_\_finally**  ブロックの外部にジャンプする必要がある場合は、先に異常終了の有無をチェックしてください。  
  
 次の例では警告 C4532 が生成されます。この警告は、jump ステートメントをコメント アウトするだけで解決できます。  
  
```  
// C4532.cpp  
// compile with: /W1  
// C4532 expected  
int main() {  
   int i;  
   for (i = 0; i < 10; i++) {  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         continue;  
      }  
  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         break;  
      }  
   }  
}  
```
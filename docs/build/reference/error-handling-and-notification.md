---
title: "エラー処理と通知 | Microsoft Docs"
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
helpviewer_keywords: 
  - "エラー処理, and 通知"
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# エラー処理と通知
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エラー処理と通知の詳細については、「[ヘルパー関数について](http://msdn.microsoft.com/ja-jp/6279c12c-d908-4967-b0b3-cabfc3e91d3d)」を参照してください。  
  
 フック関数の詳細については、「[構造体と定数の定義](../../build/reference/structure-and-constant-definitions.md)」を参照してください。  
  
 プログラムで遅延読み込み DLL を使用する場合、プログラムの実行中に発生するエラーでは例外処理が行われないため、エラーを確実に処理する必要があります。  エラー処理は次の 2 か所で行います。  
  
 フックによる回復  
 エラー発生時に、コードで回復処理を行うか、または代替ライブラリやルーチンを提供する必要がある場合は、この回復処理を実行できるヘルパー関数にフックを設定できます。  フック ルーチンは、処理を継続するための値 \(HINSTANCE または FARPROC\) を返すか、例外のスローを指示する 0 を返す必要があります。  フックから **longjmp** することも、独自の例外をスローすることもできます。  フックには、通知フックとエラー フックがあります。  
  
 例外による通知  
 エラー処理がプロシージャの中止だけであり、ユーザー コードで例外を処理できる場合、フックは必要ありません。  
  
 エラー処理と通知の詳細については、次のトピックを参照してください。  
  
-   [通知フック](../../build/reference/notification-hooks.md)  
  
-   [エラー フック](../Topic/Failure%20Hooks.md)  
  
-   [例外](../../build/reference/exceptions-c-cpp.md)  
  
## 参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)
---
title: "Visual C++ での例外処理 | Microsoft Docs"
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
  - "try-catch キーワード [C++], 例外処理"
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++ での例外処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

例外とは、プログラムが通常の実行パスに沿って進むことを妨げるエラー状態のことであり、プログラムで制御できない可能性があります。  オブジェクトの作成、ファイルの入出力、および他のモジュールから行われる関数呼び出しを含む特定のアクションは、プログラムが正しく実行されている場合でも、すべて例外の潜在的な原因となります。  堅牢なコードは例外を予期し、それを処理します。  
  
 1 つのプログラムまたはモジュール内で論理エラーを検出するには、例外ではなくアサーションを使用します \(「[アサーションの使用](../Topic/C-C++%20Assertions.md)」を参照してください\)。  
  
 Visual C\+\+ は、3 種類の例外処理をサポートしています。  
  
-   [C\+\+ 例外処理](../cpp/cpp-exception-handling.md)  
  
     ほとんどの C\+\+ プログラムでは、タイプ セーフでオブジェクトのデストラクターがスタック アンワインド中に確実に呼び出されるようにする、C\+\+ 例外処理を使用する必要があります。  
  
-   [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)  
  
     Windows には、SEH と呼ばれる独自の例外機構が備わっています。  これは C\+\+ または MFC プログラミングには推奨されません。  SEH は非 MFC C プログラムでのみ使用します。  
  
-   [MFC 例外](../mfc/exception-handling-in-mfc.md)  
  
     MFC はバージョン 3.0 以降、C\+\+ 例外を使用していますが、フォームの C\+\+ 例外に似た古い例外処理マクロを引き続きサポートします。  これらのマクロは新しいプログラミングで推奨されませんが、下位互換性のために引き続きサポートされます。  既にマクロを使用しているプログラムでは、自由に C\+\+ の例外も使用できます。  プリプロセス時に、Visual C\+\+ Version 2.0 時点では、マクロは C\+\+ 言語の Visual C\+\+ の実装で定義されている例外処理キーワードに評価されます。  C\+\+ 例外処理の使用を開始するときは、既存の例外処理マクロをそのまま維持できます。  
  
 プロジェクトで使用する例外処理の種類を指定するには、[\/EH](../build/reference/eh-exception-handling-model.md) のコンパイラ オプションを使用します。C\+\+ 例外処理が既定です。  エラー処理機構を併用しないでください。たとえば、構造化例外処理で C\+\+ 例外を使用しないでください。  C\+\+ 例外処理を使用すると、コードの移植性が高くなり、すべての種類の例外を処理できるようになります。  構造化例外処理の欠点の詳細については、「[構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)」を参照してください。  MFC マクロと C\+\+ 例外の併用のアドバイスについては、「[例外: MFC マクロと C\+\+ の例外の使用](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)」を参照してください。  
  
 CLR アプリケーションの処理の例外の詳細については、「[Exception Handling](../windows/exception-handling-cpp-component-extensions.md)」を参照してください。  
  
 x64 プロセッサの例外処理の詳細については、「[例外処理 \(x64\)](../build/exception-handling-x64.md)」を参照してください。  
  
## 参照  
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)
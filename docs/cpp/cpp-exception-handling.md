---
title: "C++ 例外処理 | Microsoft Docs"
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
  - "C++ 例外処理"
  - "Visual C++, 例外処理"
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 例外処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 言語は、例外のスローおよびキャッチに関する組み込みサポートを提供します。  C\+\+ でプログラミングするときは、通常、このセクションで説明するように、組み込みの C\+\+ 例外サポートを使用する必要があります。  
  
 コードの C\+\+ 例外処理を有効にするには、[\/EHsc](../build/reference/eh-exception-handling-model.md) を使用します。  
  
## このセクションの内容  
 C\+\+ 例外処理についてのこの説明には、次の事項が含まれます。  
  
-   [try、catch、および throw ステートメント](../cpp/try-throw-and-catch-statements-cpp.md)  
  
-   [catch ブロックの評価方法](../Topic/How%20Catch%20Blocks%20are%20Evaluated%20\(C++\).md)  
  
-   [例外とスタック アンワインド](../cpp/exceptions-and-stack-unwinding-in-cpp.md)  
  
-   [例外の指定](../cpp/exception-specifications-throw-cpp.md)  
  
-   [noexcept](../Topic/noexcept%20\(C++\).md)  
  
-   [未処理の C\+\+ 例外](../cpp/unhandled-cpp-exceptions.md)  
  
-   [C \(構造化\) と C\+\+ の混合例外](../Topic/Mixing%20C%20\(Structured\)%20and%20C++%20Exceptions.md)  
  
## MFC の以前のバージョンの例外のサポート  
 バージョン 4.0 の時点で、MFC は C\+\+ 例外処理メカニズムの使用を開始しました。  新しいコードで C\+\+ 例外処理を使用するように推奨されますが、古いコードが壊れないように、MFC のバージョン 4.0 以降では MFC の以前のバージョンのマクロを保持します。  マクロと新しいメカニズムも組み合わせることができます。  マクロと C\+\+ 例外処理を使用する方法と古いコードを変換して新しいメカニズムを使用する方法については、「[例外: MFC マクロと C\+\+ の例外の使用](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)」および「[例外: MFC 例外マクロからの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)」を参照してください。  以前の MFC 例外マクロを使用している場合、これは C\+\+ の例外のキーワードに評価されます。  「[例外: Version 3.0 での例外マクロの変更点](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)」を参照してください。  
  
## 参照  
 [例外処理](../cpp/exception-handling-in-visual-cpp.md)
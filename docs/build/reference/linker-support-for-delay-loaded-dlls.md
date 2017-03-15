---
title: "リンカーによる DLL の遅延読み込み | Microsoft Docs"
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
  - "遅延読み込み (DLL を), リンカー サポート"
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# リンカーによる DLL の遅延読み込み
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ のリンカーは DLL の遅延読み込みをサポートするようになりました。  このため、[!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] の関数 **LoadLibrary** と **GetProcAddress** を使用して DLL の遅延読み込みを実装する必要がなくなりました。  
  
 Visual C\+\+ 6.0 以前のバージョンでは、実行時に DLL を読み込む方法は、**LoadLibrary** と **GetProcAddress** を使用する方法だけでした。DLL は、その DLL を使用する実行可能ファイルまたは DLL が読み込まれたたときに、オペレーティング システムによって読み込まれました。  
  
 Visual C\+\+ 6.0 からは、DLL との静的なリンクの場合に、DLL の関数の呼び出し時に初めて DLL が遅延読み込みされるようにするオプションをリンカーで選択できるようになりました。  
  
 アプリケーションでは、[\/DELAYLOAD \(遅延読み込みインポート\)](../../build/reference/delayload-delay-load-import.md) リンカー オプションとヘルパー関数 \(Visual C\+\+ では既定の実装\) を使用して、DLL の読み込みを遅延できます。  ヘルパー関数は、**LoadLibrary** と **GetProcAddress** を呼び出して、実行時に DLL を読み込みます。  
  
 以下の場合は、DLL の遅延読み込みをお勧めします。  
  
-   プログラムで DLL の関数を呼び出さない可能性がある。  
  
-   プログラムの実行の後半まで DLL の関数を呼び出さない可能性がある。  
  
 DLL の遅延読み込みは、.EXE プロジェクトまたは .DLL プロジェクトのビルド時に指定できます。  DLL の遅延読み込みを行う .DLL プロジェクトの場合、それ自体では **Dllmain** で遅延読み込みエントリ ポイントを呼び出しません。  
  
 DLL の遅延読み込みの詳細については、次のトピックを参照してください。  
  
-   [遅延読み込みする DLL の指定](../../build/reference/specifying-dlls-to-delay-load.md)  
  
-   [遅延読み込みした DLL の明示的なアンロード](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
-   [遅延読み込みされた DLL に対するすべてのインポートの読み込み](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)  
  
-   [インポートのバインド](../../build/reference/binding-imports.md)  
  
-   [エラー処理と通知](../../build/reference/error-handling-and-notification.md)  
  
-   [遅延読み込みしたインポートのダンプ](../../build/reference/dumping-delay-loaded-imports.md)  
  
-   [DLL の遅延読み込みの制約](../../build/reference/constraints-of-delay-loading-dlls.md)  
  
-   [ヘルパー関数について](http://msdn.microsoft.com/ja-jp/6279c12c-d908-4967-b0b3-cabfc3e91d3d)  
  
-   [独自のヘルパー関数の作成](../../build/reference/developing-your-own-helper-function.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../../build/dlls-in-visual-cpp.md)   
 [リンク](../Topic/Linking.md)
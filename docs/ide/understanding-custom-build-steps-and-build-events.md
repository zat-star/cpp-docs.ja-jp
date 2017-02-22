---
title: "カスタム ビルド ステップとビルド イベントについて | Microsoft Docs"
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
  - "ビルド イベント [C++], 順序 (イベントとビルド ステップ)"
  - "ビルド ステップ [C++]"
  - "ビルド ステップ [C++], ビルド イベント"
  - "ビルド [C++], カスタム ビルド ステップ"
  - "ビルド [C++], イベント"
  - "カスタム ビルド ステップ [C++]"
  - "カスタム ビルド ステップ [C++], カスタマイズ (ビルドを)"
  - "イベント [C++], ビルド"
ms.assetid: beb2f017-3e9f-4b2c-9b57-2572fd2628e4
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# カスタム ビルド ステップとビルド イベントについて
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 開発環境では、ビルド処理をカスタマイズする基本的な方法が 3 つあります。  
  
 **カスタム ビルド ステップ**  
 カスタム ビルド ステップは、プロジェクトに関連付けられたビルド規則です。  カスタム ビルド ステップでは、実行するコマンド ライン、追加の入力または出力ファイル、および表示するメッセージを指定できます。  詳細については、「[方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する](../Topic/How%20to:%20Add%20a%20Custom%20Build%20Step%20to%20MSBuild%20Projects.md)」を参照してください。  
  
 **カスタム ビルド ツール**  
 カスタム ビルド ツールは、1 つ以上のファイルに関連付けられているビルド規則です。  カスタム ビルド ステップは、入力ファイルをカスタム ビルド ツールに渡すことができ、その結果、1 つ以上の出力ファイルが生成されます。  たとえば、MFC アプリケーションのヘルプ ファイルは、カスタム ビルド ツールを使用してビルドされます。  詳細については、「[方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)」および「[カスタム ビルド ツールの指定](../ide/specifying-custom-build-tools.md)」を参照してください。  
  
 **\[ビルド イベント\]**  
 ビルド イベントでは、プロジェクトのビルドをカスタマイズできます。  *ビルド前*、*リンク前*、*ビルド後*の 3 つのビルド イベントがあります。  ビルド イベントでは、ビルド処理の特定の時点で発生するアクションを指定します。  たとえば、ビルド イベントを使用して、プロジェクトのビルドが終了した後でファイルを **regsvr32.exe** で登録できます。  詳細については、「[ビルド イベントの指定](../ide/specifying-build-events.md)」を参照してください。  
  
 「[ビルドのカスタマイズのトラブルシューティング](../ide/troubleshooting-build-customizations.md)」は、カスタム ビルド ステップとビルド イベントを意図したとおりに実行するために役立ちます。  
  
 カスタム ビルド ステップまたはビルド イベントの出力書式により、ツールの操作性を向上させることもできます。  詳細については、「[カスタム ビルド ステップまたはビルド イベントの出力の書式設定](../ide/formatting-the-output-of-a-custom-build-step-or-build-event.md)」を参照してください。  
  
 ビルド イベントとカスタム ビルド ステップは、ほかのビルド ステップと共に次の順序で実行されます。  
  
1.  ビルド前のイベント。  
  
2.  各ファイルに対するカスタム ビルド ツール。  
  
3.  MIDL。  
  
4.  リソース コンパイラ。  
  
5.  C\/C\+\+ コンパイラ。  
  
6.  リンク前の イベント。  
  
7.  リンカーまたはライブラリアン。  
  
8.  マニフェスト ツール。  
  
9. BSCMake。  
  
10. プロジェクトに対するカスタム ビルド ステップ。  
  
11. ビルド後のイベント。  
  
 `custom build step on the project` および `post-build event` は、他のすべてのビルド処理が完了した後に連続して実行されます。  
  
## 参照  
 [Visual Studio での C\+\+ プロジェクトのビルド](../ide/building-cpp-projects-in-visual-studio.md)   
 [ビルドのコマンドとプロパティのマクロ](../ide/common-macros-for-build-commands-and-properties.md)   
 [Tool Build Order Dialog Box](http://msdn.microsoft.com/ja-jp/6204c5b1-7ce9-4948-9ff6-0268642ee14c)
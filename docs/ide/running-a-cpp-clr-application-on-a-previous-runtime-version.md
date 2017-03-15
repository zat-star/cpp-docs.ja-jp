---
title: "以前のランタイム バージョンでの C++ /clr アプリケーションの実行 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "app.config ファイル, ランタイム バージョンの指定"
  - "アプリケーションの配置 [C++], ランタイム バージョンの指定"
  - "アプリケーション [C++], ランタイム バージョンの指定"
  - "下位互換性 [C++], ランタイム バージョンの指定"
  - "共通言語ランタイム [C++], バージョン指定"
  - "互換性 [C++], ランタイム バージョンの指定"
  - "配置 (アプリケーションを) [C++], ランタイム バージョンの指定"
  - "バージョン [C++]"
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 以前のランタイム バージョンでの C++ /clr アプリケーションの実行
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

他に特に指定しない限り、Visual C\+\+ .NET Framework アプリケーションは、コンパイラがアプリケーションのビルドに使用する共通言語ランタイムの \(CLR\) のバージョンで実行されるビルドします。  ただし、ランタイムの 1 種類のバージョンに必要な機能を提供する他のバージョンでも実行するようにビルドされたアプリケーションに対してできます。  
  
 これを行うには、`supportedRuntime` タグではランタイム バージョン情報を含む app.config ファイルを提供します。  
  
 実行時には、app.config ファイルは *filename.ext* がアプリケーションを起動し、実行可能ファイルと同じディレクトリにある実行可能ファイルの名前です。フォーム *filename.ext*.config の名前で。  たとえば、アプリケーションが TestApp.exe である場合、app.config ファイルの名前は TestApp.exe.config になります。  
  
 複数のランタイム バージョンをアプリケーションが複数のランタイム バージョンがインストールされているコンピューターで実行する場合、アプリケーションは構成ファイルに指定され、インストール、最初のバージョンを使用します。  
  
 詳細については、「[How to: Configure an App to Target a .NET Framework Version](http://msdn.microsoft.com/ja-jp/5247b307-89ca-417b-8dd0-e8f9bd2f4717)」を参照してください。  
  
 にバージョン 1.0 または CLR バージョン 1.1 で実行するには、Visual C\+\+ コンパイラでビルドされたアプリケーションは [\/clr:initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md)を使用してコンパイルする必要があります。  
  
## 参照  
 [デスクトップ アプリケーションの配置](../Topic/Deploying%20Native%20Desktop%20Applications%20\(Visual%20C++\).md)
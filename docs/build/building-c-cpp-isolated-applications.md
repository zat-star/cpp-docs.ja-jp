---
title: "C/C++ 分離アプリケーションのビルド | Microsoft Docs"
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
  - "分離アプリケーション [C++]"
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ 分離アプリケーションのビルド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

分離アプリケーションは、side\-by\-side アセンブリだけに依存し、その依存関係をマニフェストを使用してバインドします。  アプリケーションを完全に分離しなくても Windows で正常に動作しますが、アプリケーションを完全に分離しておくことにより、将来アプリケーションにサービスを提供する必要がある場合に時間を短縮できます。  アプリケーションを完全に分離する利点の詳細については、「[分離アプリケーション](http://msdn.microsoft.com/library/aa375190)」を参照してください。  
  
 Visual C\+\+ を使用してネイティブな C\/C\+\+ アプリケーションをビルドする場合、Visual Studio プロジェクト システムは、既定でアプリケーションの Visual C\+\+ への依存関係を記述したマニフェスト ファイルを生成します。  アプリケーションが持つ依存関係がこれだけである場合、アプリケーションは、Visual C\+\+ で再ビルドされると分離アプリケーションになります。  実行時にアプリケーションが他のライブラリを使用している場合は、これらのライブラリを「[C\/C\+\+ side\-by\-side アセンブリのビルド](../build/building-c-cpp-side-by-side-assemblies.md)」で説明されている手順に従って side\-by\-side アセンブリとして再ビルドすることが必要になる場合があります。  
  
## 参照  
 [分離アプリケーションおよび side\-by\-side アセンブリの概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C\/C\+\+ 分離アプリケーションおよび side\-by\-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
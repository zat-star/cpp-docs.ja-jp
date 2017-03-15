---
title: "C/C++ プログラムのビルド | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vcbuilding"
  - "buildingaprogramVC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ビルド [C++]"
  - "ビルド [C++], オプション"
  - "プロジェクト [C++], ビルド"
  - "Visual C++ プロジェクト, ビルド"
  - "Visual C++, ビルド オプション"
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ プログラムのビルド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ プロジェクトは、Visual Studio またはコマンド ラインでビルドできます。  Visual Studio IDE は、[MSBuild](../Topic/MSBuild%20\(Visual%20C++\).md) を使用してプロジェクトやソリューションをビルドします。  コマンド ラインでは、C\/C\+\+ コンパイラ \(cl.exe\) と リンカー \(link.exe\) を使用して単純なプロジェクトをビルドできます。  コマンド ラインでより複雑なプロジェクトをビルドするには、MSBuild または [NMAKE](../build/nmake-reference.md) を使用できます。  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] を使用してプロジェクトとソリューションをビルドする方法の概要については、「[Visual Studio でのアプリケーションのビルド](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)」を参照してください。  
  
## このセクションの内容  
 [Visual Studio での C\+\+ プロジェクトのビルド](../ide/building-cpp-projects-in-visual-studio.md)  
 Visual Studio IDE を使用して C\/C\+\+ プロジェクトをビルドする方法について説明します。  
  
 [コマンド ラインでのビルド](../Topic/Building%20on%20the%20Command%20Line.md)  
 Visual Studio に含まれている C\/C\+\+ コマンド ライン コンパイラおよびビルド ツールの使用方法について説明します。  
  
 [C\/C\+\+ 分離アプリケーションおよび side\-by\-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
 アプリケーションの分離、side\-by\-side アセンブリなどの考え方に基づいた Windows デスクトップ アプリケーションの配置モデルについて説明します。  
  
 [C\/C\+\+ ビルドのリファレンス](../Topic/C-C++%20Building%20Reference.md)  
 C\+\+ でのプログラムのビルド、コンパイラ オプションとリンカー オプション、およびさまざまなビルド ツールに関する参照記事へのリンクがあります。  
  
 [64 ビット用プログラムの構成](../build/configuring-programs-for-64-bit-visual-cpp.md)  
 64 ビット ツール セットを使用し、64 ビット アーキテクチャをターゲットとして Visual Studio とコマンド ラインを設定する方法について説明し、コードを 64 ビット アーキテクチャに移行するときに一般的に発生する、移行に関する問題について説明します。  
  
 [ARM プロセッサ用プログラムの構成](../Topic/Configuring%20Programs%20for%20ARM%20Processors%20\(Visual%20C++\).md)  
 ARM プロセッサで使用される用語について説明し、コードを ARM アーキテクチャに移行するときに一般的に発生する、移行に関する問題について説明します。  
  
 [Windows XP 用 C\+\+ 11 プログラムの構成](../build/configuring-programs-for-windows-xp.md)  
 Windows XP 開発をターゲットとしてプラットフォーム ツールセットを設定する方法について説明します。  
  
## 関連項目  
 [NIB: Samples Included in Visual C\+\+](http://msdn.microsoft.com/ja-jp/c9ec56b3-2bbd-49b4-8a4c-9ed4b78b7a84)  
 Visual C\+\+ の機能や、Visual C\+\+ がサポートするライブラリとテクノロジを示すサンプル コードへのリンクがあります。  
  
 [Visual Studio でのアプリケーションのビルド](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)  
 Visual Studio のビルド システムとツールについて説明します。
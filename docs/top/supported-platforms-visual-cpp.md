---
title: "サポートされるプラットフォーム (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "プラットフォーム [C++]"
  - "Visual C++, プラットフォーム (サポートされている)"
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# サポートされるプラットフォーム (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] を使用してビルドしたアプリケーションは、次のようにさまざまなプラットフォームを対象にすることができます。  
  
|オペレーティング システム|x86|x64|ARM|  
|-------------------|---------|---------|---------|  
|Windows XP|X\*|X\*||  
|[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]|X\*|X\*||  
|Windows Vista|X|X||  
|Windows Server 2008|X|X||  
|Windows 7|X|X||  
|Windows Server 2012 R2|X|X||  
|Windows 8|X|X|X|  
|Windows 8.1|X|X|X|  
|Windows 10|X|X|X|  
|Android \*\*|X|X|X|  
|iOS \*\*|X|X|X|  
  
 \* Visual Studio 2015、Visual Studio 2013、および Visual Studio 2012 Update 1 以降に含まれている Windows XP プラットフォーム ツールセットを使用して、Windows XP および [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]プロジェクトに設定できます。  このプラットフォーム ツールセットを使用する方法については、「[Windows XP 用 C\+\+ 11 プログラムの構成](../build/configuring-programs-for-windows-xp.md)」を参照してください。  プラットフォーム ツールセットの変更に関する詳細については、「[方法: ターゲット フレームワークおよびプラットフォームのツールセットを変更する](../build/how-to-modify-the-target-framework-and-platform-toolset.md)」を参照してください。  
  
 \*\* Visual Studio 2015 セットアップでオプションの Visual C\+\+ for Cross Platform Mobile Development コンポーネントをインストールして、iOS または Android プラットフォームをターゲットにすることができます。  手順については、「[Visual C\+\+ for Cross\-Platform Mobile Development のインストール](../Topic/Install%20Visual%20C++%20for%20Cross-Platform%20Mobile%20Development.md)」を参照してください。  iOS コードをビルドするには、Mac コンピューターがあり、他の要件を満たしている必要があります。  前提条件とインストール手順については、「[iOS を使用してビルドするためのツールのインストールおよび構成](../Topic/Install%20And%20Configure%20Tools%20to%20Build%20using%20iOS.md)」を参照してください。  ターゲット ハードウェアに合わせて、x86 または ARM コードをビルドできます。  iOS シミュレーター、Microsoft Visual Studio Emulator for Android、一部の Android デバイスのビルドには x86 構成を使用します。  iOS デバイスとほとんどのデバイスのビルドには ARM 構成を使用します。  
  
 ターゲット プラットフォームの構成を設定する方法については、「[方法 : Visual C\+\+ プロジェクトを 64 ビット プラットフォーム用に設定する](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)」を参照してください。  
  
## 参照  
 [Visual Studio エディションでの Visual C\+\+ ツールおよびテンプレート](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)   
 [作業の開始](../misc/getting-started-with-visual-cpp-in-visual-studio-2015.md)
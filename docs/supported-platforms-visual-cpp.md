---
title: "サポートされるプラットフォーム (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 0192e9bd6ef9d93e274c43c24137a27e5aa53dab
ms.openlocfilehash: c0c209c16ad4a264b851321a2879104112da81f2
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="supported-platforms-visual-c"></a>サポートされるプラットフォーム (Visual C++)
[!INCLUDE[vsprvs](assembler/masm/includes/vsprvs_md.md)] を使用してビルドしたアプリケーションは、次のようにさまざまなプラットフォームを対象にすることができます。  
  
|オペレーティング システム|x86|x64|ARM|  
|----------------------|---------|---------|---------|  
|Windows XP|X*|X*||  
|[!INCLUDE[WinXPSvr](build/includes/winxpsvr_md.md)]|X*|X*||  
|Windows Vista|X|X||  
|Windows Server 2008|X|X||  
|Windows 7|X|X||  
|Windows Server 2012 R2|X|X||  
|Windows 8|X|X|X|  
|Windows 8.1|X|X|X|  
|Windows 10|X|X|X|  
|Android **|X|X|X|  
|iOS **|X|X|x|  
  
 \* Visual Studio 2015、Visual Studio 2013、および Visual Studio 2012 Update 1 以降に含まれている Windows XP プラットフォーム ツールセットを使用して、Windows XP および [!INCLUDE[WinXPSvr](build/includes/winxpsvr_md.md)] プロジェクトに設定できます。 このプラットフォーム ツールセットを使用する方法については、「[Windows XP 用プログラムの構成](build/configuring-programs-for-windows-xp.md)」を参照してください。 プラットフォーム ツールセットの変更に関する詳細については、「[方法: ターゲット フレームワークおよびプラットフォームのツールセットを変更する](build/how-to-modify-the-target-framework-and-platform-toolset.md)」を参照してください。  
  
 ** Visual Studio 2015 セットアップでオプションの Visual C++ for Cross Platform Mobile Development コンポーネントをインストールして、iOS または Android プラットフォームをターゲットにすることができます。 手順については、「[クロス プラットフォーム モバイル開発用の Visual C++ のインストール](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development)」を参照してください。 iOS コードをビルドするには、Mac コンピューターがあり、他の要件を満たしている必要があります。 前提条件とインストール手順については、「[iOS を使用してビルドするためのツールのインストールおよび構成](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios)」を参照してください。 ターゲット ハードウェアに合わせて、x86 または ARM コードをビルドできます。 iOS シミュレーター、Microsoft Visual Studio Emulator for Android、一部の Android デバイスのビルドには x86 構成を使用します。 iOS デバイスとほとんどのデバイスのビルドには ARM 構成を使用します。  
  
 ターゲット プラットフォームの構成を設定する方法については、「[方法 : Visual C++ プロジェクトを 64 ビット プラットフォーム用に設定する](build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [さまざまな Visual Studio エディションの Visual C++ ツールおよび機能](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)   
 [はじめに](/visualstudio/ide/getting-started-with-visual-cpp-in-visual-studio)

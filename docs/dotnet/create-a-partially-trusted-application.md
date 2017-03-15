---
title: "方法: CRT ライブラリ DLL との依存関係を削除して部分信頼アプリケーションを作成する | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr コンパイラ オプション [C++], 部分的に信頼されたアプリケーション"
  - "相互運用 [C++], 部分的に信頼されたアプリケーション"
  - "相互運用性 [C++], 部分的に信頼されたアプリケーション"
  - "混在アセンブリ [C++], 部分的に信頼されたアプリケーション"
  - "msvcm90[d].dll"
  - "部分的に信頼されたアプリケーション [C++]"
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: CRT ライブラリ DLL との依存関係を削除して部分信頼アプリケーションを作成する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、msvcm90.dll との依存関係を削除することで、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] を使用して部分信頼の共通言語ランタイム アプリケーションを作成する方法について説明します。  
  
 **\/clr** で構築する Visual C\+\+ アプリケーションは、C ランタイム ライブラリの一部である msvcm90.dll との依存関係を持ちます。  アプリケーションを部分信頼環境で使用する場合、CLR は特定のコード アクセス セキュリティ規則を DLL に強制的に適用します。  msvcm90.dll にはその DLL に強制的に適用できないネイティブ コードとコード アクセス セキュリティ ポリシーが含まれているため、この依存関係を削除する必要があります。  
  
 アプリケーションが C ランタイム ライブラリの機能を使用していないときに、このライブラリとの依存関係をコードから削除する場合は、**\/NODEFAULTLIB:msvcmrt.lib** リンカー オプションを使用して、ptrustm.lib または ptrustmd.lib のいずれかとリンクする必要があります。  これらのライブラリには、アプリケーションの初期化と初期化解除用のオブジェクト ファイル、初期化コードで使用される例外クラス、およびマネージ例外処理コードが含まれています。  これらのいずれかのライブラリにリンクすることで、msvcm90.dll とのすべての依存関係が削除されます。  
  
> [!NOTE]
>  アセンブリの初期化解除の順序は、ptrust ライブラリを使用するアプリケーション間で異なる場合があります。  標準的なアプリケーションの場合、アセンブリは通常読み込まれた順序とは逆の順序でアンロードされますが、これが保証されるわけではありません。  部分信頼アプリケーションの場合、アセンブリは通常読み込まれた順序と同じ順序でアンロードされます。  これも保証されるわけではありません。  
  
### 部分信頼混合 \(\/clr\) アプリケーションを作成するには  
  
1.  msvcm90.dll との依存関係を削除するには、**\/NODEFAULTLIB:msvcmrt.lib** リンカー オプションを使用して、このライブラリを含めないことをリンカーに指定する必要があります。  これを Visual Studio 開発環境またはプログラムで実行する方法については、「[\/NODEFAULTLIB \(ライブラリを無視する\)](../build/reference/nodefaultlib-ignore-libraries.md)」を参照してください。  
  
2.  リンカー入力依存関係にいずれかの ptrustm ライブラリを追加します。  リリース モードでアプリケーションを構築する場合は、ptrustm.lib を使用します。  デバッグ モードの場合は、ptrustmd.lib を使用します。  これを Visual Studio 開発環境またはプログラムで実行する方法については、「[リンカー入力としての .lib ファイル](../build/reference/dot-lib-files-as-linker-input.md)」を参照してください。  
  
## 参照  
 [混在 \(ネイティブおよびマネージ\) アセンブリ](../Topic/Mixed%20\(Native%20and%20Managed\)%20Assemblies.md)   
 [混在アセンブリの初期化](../Topic/Initialization%20of%20Mixed%20Assemblies.md)   
 [混在アセンブリのためのライブラリ サポート](../dotnet/library-support-for-mixed-assemblies.md)   
 [\/link \(リンカーにオプションを渡す\)](../Topic/-link%20\(Pass%20Options%20to%20Linker\).md)   
 [PAVE Security in Native and .NET Framework Code](http://msdn.microsoft.com/ja-jp/bd61be84-c143-409a-a75a-44253724f784)
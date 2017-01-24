---
title: "ユニバーサル Windows アプリ (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ユニバーサル Windows アプリ (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユニバーサル Windows プラットフォーム \(UWP\) アプリは、さまざまなデバイス上のさまざまな画面サイズに合わせて自動的に調整されるコンテンツを中心とした、シンプルなユーザー インターフェイスを強調する、一連のデザイン原則を具体化します。 XAML マークアップで UI を作成し、ネイティブ C\+\+ で分離コードを作成します。 さらに他の言語で記述された UWP アプリケーションで使用可能なコンポーネント \(DLL\) を作成できます。 UWP アプリケーションの API サーフェスは [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] であり、これはさまざまなオペレーティング システム サービスを提供するための十分に考慮されたライブラリです。  
  
> [!NOTE]
>  C\+\+ の UWP アプリケーションの開発に関するドキュメントの多くは、[Windows デベロッパー センター](http://go.microsoft.com/fwlink/p/?LinkId=255563) の Web サイトにあります。 この記事のリンクの一部は、その Web サイトに移動します。  
  
## C\+\+\/CX を使用する UWP アプリ  
  
|||  
|-|-|  
|[Visual C\+\+ の言語リファレンス \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=255561)|C\+\+ の [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] API の使用を簡単にし、また例外が原因のエラー処理を可能にする、拡張機能のセットについて説明します。|  
|[アプリケーションとライブラリのビルド \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=264858)|C \+\+\/CX アプリケーションまたはコンポーネントからアクセスできるスタティック ライブラリと DLL を作成する方法について説明します。|  
|[チュートリアル: C\+\+ を使った初めての Windows ストア アプリの作成](http://go.microsoft.com/fwlink/p/?LinkId=255556)|C\+\+ での [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリケーションの開発における基本概念を説明するチュートリアルです。 \(Windows 10 での UWP 開発に関してはまだ更新されていません。\)|  
|[C\+\+ を使った Windows ストア アプリのためのロードマップ](http://go.microsoft.com/fwlink/p/?LinkId=255553)|C\+\+ での [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリケーションおよびゲームの開発に関する記事へのリンクを提供します。|  
|[C\+\+ で Windows ランタイム コンポーネントを作成する](http://go.microsoft.com/fwlink/p/?LinkId=255559)|他の [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリケーションおよびコンポーネントが使用できる DLL を作成する方法について説明します。|  
|[ゲームの開発](http://go.microsoft.com/fwlink/p/?LinkId=255554)|DirectX および C\+\+ を使ってゲームを作成する方法について説明します。|  
  
## [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] \([!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)]\) を使用する [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] アプリ  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] は下位レベルの COM インターフェイスを提供し、これによって ISO C\+\+ コードは例外制御不要の環境で [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] にアクセスできます。 ほとんどの場合、[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] アプリ開発には、[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] ではなく C\+\+\/CX を使用することをお勧めします。[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] の詳細については、「[Windows ランタイム C\+\+ テンプレート ライブラリ \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)」を参照してください。  
  
## 参照  
 [Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)
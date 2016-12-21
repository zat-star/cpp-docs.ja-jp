---
title: "Windows デスクトップ アプリケーション (Visual C++) | Microsoft Docs"
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
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
caps.latest.revision: 17
caps.handback.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Windows デスクトップ アプリケーション (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィンドウ ベースのユーザー インターフェイスを持ち、Windows XP から Windows 10 のバージョンの Windows デスクトップで実行できるネイティブなデスクトップ アプリケーションを作成する必要がある場合は、Windows デスクトップ アプリケーションを作成できます。  
  
 *Windows デスクトップ アプリケーション* \(古い文献では Win32 アプリケーションと呼ばれている場合がある\) は、Microsoft Foundation Class \(MFC\)、Active Template Library \(ATL\)、NET Framework などのフレームワークを使用する代わりに、Windows メッセージを直接処理するためにメッセージ ループを使用するアプリケーションを指す従来の用語です。 C\+\+ の Windows デスクトップ アプリケーションは、C ランタイム \(CRT\) と標準テンプレート ライブラリ \(STL\) のクラスと関数、COM オブジェクト、公開されているすべての Windows 関数 \(これらを合わせて Windows API と呼ぶ\) を使用できます。 C\+\+ の Windows デスクトップ アプリケーションの概要については、「[C\+\+ による Windows プログラミングの学習](http://go.microsoft.com/fwlink/p/?LinkId=262281)」を参照してください。  
  
 Windows デスクトップ アプリケーションは、Windows 用のネイティブなデスクトップ アプリケーションを作成するための 1 つの方法です。もう 1 つの方法は MFC アプリケーションです。 MFC は、多数のユーザー インターフェイス コントロールまたはカスタム ユーザー コントロールがあるアプリ \(特にエンタープライズ型のアプリ\) のための既定の選択肢です。 また、MFC は、シリアル化、テキスト操作、印刷、および最新のユーザー インターフェイス要素 \(リボンなど\) のための便利なヘルパー クラスを提供します。 これらのクラスは Windows デスクトップ アプリケーションでは使用できません。  
  
## 関連トピック  
  
|タイトル|説明|  
|----------|--------|  
|[Windows 開発](http://go.microsoft.com/fwlink/p/?LinkId=262282)|Windows API と COM に関する情報が含まれています  \(一部の Windows API とサードパーティ製 DLL は、COM オブジェクトとして実装されています\)。|  
|[Hilo: Windows 7 対応 C\+\+ アプリケーションの開発](http://go.microsoft.com/fwlink/p/?LinkId=262284)|手荷物の受け取り場所に基づくユーザー インターフェイスを作成するために、Windows Animation と Direct2D を使用するリッチ クライアントの Windows デスクトップ アプリケーションを作成する方法について説明します。|  
|[コンソール アプリケーション](../Topic/Console%20Applications%20in%20Visual%20C++.md)|コンソール アプリに関する情報が含まれています。 Win32 \(または Win64\) コンソール アプリケーションには、独自のウィンドウとメッセージ ループはありません。 コンソール ウィンドウで動作し、入出力はコマンド ラインを使用して扱われます。|  
|[Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)|Visual Studio での Visual C\+\+ の主な機能について説明し、他の Visual C\+\+ ドキュメントへのリンクを示します。|  
|MSDN Web サイトの [Visual C\+\+ デベロッパー センター](http://go.microsoft.com/fwlink/p/?LinkId=252885)|Windows デスクトップ アプリケーションに関連するチュートリアル、ブログの投稿と記事が含まれています。|  
|[方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK を使用してビルドするプロジェクトの設定手順が示されています。|
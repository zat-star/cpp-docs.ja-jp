---
title: "Visual C++ の言語リファレンス (C++-CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
caps.latest.revision: 27
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 27
---
# Visual C++ の言語リファレンス (C++-CX)
[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) は、最新 C\+\+ にできるだけ近い表現での Windows アプリと [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントの作成を可能にする、C\+\+ 言語への一連の拡張です。[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] を使用すると、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] をサポートする Visual C\#、Visual Basic、JavaScript などの言語と簡単にやり取りできる Windows アプリやコンポーネントをネイティブ コードで記述できます。 生の COM インターフェイスへの直接アクセスを必要とするようなまれなケースや、例外的ではないコードでは、[Windows ランタイム C\+\+ テンプレート ライブラリ \(WRL\)](http://msdn.microsoft.com/library/b915afce-553b-44a7-b8dc-0ab601758eb0) を使用できます。  
  
 新しいモデルは、Windows での次世代のネイティブ C\+\+ プログラミングを表します。 これを使用すると、次のものを作成できます。  
  
-   XAML を使用してユーザー インターフェイスを定義し、ネイティブ スタックを使用する C\+\+ Windows アプリケーション。 詳細については、「[C\+\+ を使った "hello world" アプリの作成 \(Windows 10\)](http://msdn.microsoft.com/library/windows/apps/dn996906.aspx)」をご参照ください。  
  
-   JavaScript ベースの Windows アプリで利用できる C\+\+ [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネント。 詳細については、「[C\+\+ での Windows ランタイム コンポーネントの作成](http://msdn.microsoft.com/library/hh441569.aspx)[C\+\+ で Windows ランタイム コンポーネントを作成する](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)」をご参照ください。  
  
-   Windows DirectX ゲームやグラフィックス処理の多いアプリ。 詳細については、「[DirectX を使った単純なユニバーサル Windows プラットフォーム \(UWP\) ゲームの作成](http://msdn.microsoft.com/library/windows/apps/xaml/mt210793.aspx)」をご参照ください。  
  
## 関連記事  
  
|||  
|-|-|  
|[クイック リファレンス](../cppcx/quick-reference-c-cx.md)|[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) のキーワードと演算子の表。|  
|[型システム](../cppcx/type-system-c-cx.md)|[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] の基本的な型とプログラミング構成要素、および [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] を使用して [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] の型を利用および作成する方法について説明します。|  
|[アプリケーションとライブラリのビルド](../cppcx/building-apps-and-libraries-c-cx.md)|IDE を使用してアプリケーションをビルドし、スタティック ライブラリおよび DLL にリンクする方法について説明します。|  
|[その他の言語との相互運用](../cppcx/interoperating-with-other-languages-c-cx.md)|[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] で記述されたコンポーネントを、JavaScript、マネージ言語、または [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)] で記述されたコンポーネントと共に使用する方法について説明します。|  
|[スレッドとマーシャリング](../cppcx/threading-and-marshaling-c-cx.md)|作成するコンポーネントのスレッドとマーシャリングの動作を指定する方法について説明します。|  
|[名前空間参照](../cppcx/namespaces-reference-c-cx.md)|既定の名前空間、Platform 名前空間、Platform::Collections、および関連する名前空間の参照ドキュメント。|  
|[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Windows ランタイム アプリでは使用できない CRT 関数の一覧を示します。|  
|[Windows 10 アプリに関するハウツー ガイド](http://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Windows 10 アプリについての全般的な概要と、詳細情報へのリンクがあります。|  
  
1.  [C\+\+\/CX パート 0\/\[n\]: はじめに](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
2.  [C\+\+\/CX パート 0\/\[n\]: はじめに](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
3.  [C\+\+\/CX パート 2\/\[n\]: ハット記号が付いた型](http://blogs.msdn.com/b/vcblog/archive/2012/09/17/cxxcxpart02typesthatwearhats.aspx)  
  
4.  [C\+\+\/CX パート 3\/\[n\]: 作成中](http://blogs.msdn.com/b/vcblog/archive/2012/10/05/cxxcxpart03underconstruction.aspx)  
  
5.  [C\+\+\/CX パート 4\/\[n\]: 静的メンバー関数](http://blogs.msdn.com/b/vcblog/archive/2012/10/19/cxxcxpart04staticmemberfunctions.aspx)
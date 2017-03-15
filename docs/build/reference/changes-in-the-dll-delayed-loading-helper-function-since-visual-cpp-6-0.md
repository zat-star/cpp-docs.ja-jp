---
title: "Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点 | Microsoft Docs"
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
  - "__delayLoadHelper2 関数"
  - "遅延読み込み (DLL を), 変更点"
  - "ヘルパー関数, 変更点"
  - "PFromRva メソッド"
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンピューターに複数バージョンの Visual C\+\+ がインストールされている場合、または独自のヘルパー関数が定義されている場合は、DLL 遅延読み込みヘルパー関数に加えられた変更の影響を受ける可能性があります。  たとえば、次のようになります。  
  
-   **\_\_delayLoadHelper** は **\_\_delayLoadHelper2** に変更されています。  
  
-   **\_\_pfnDliNotifyHook** は **\_\_pfnDliNotifyHook2** に変更されています。  
  
-   **\_\_pfnDliFailureHook** は **\_\_pfnDliFailureHook2** に変更されています。  
  
-   **\_\_FUnloadDelayLoadedDLL** は **\_\_FUnloadDelayLoadedDLL2** に変更されています。  
  
> [!NOTE]
>  既定のヘルパー関数を使用する場合は、変更点に注意する必要はありません。  リンカーの起動方法に変更はありません。  
  
## 複数バージョンの Visual C\+\+  
 コンピューターに複数バージョンの Visual C\+\+ がインストールされている場合は、リンカーが delayimp.lib と一致しているかどうかを確認してください。  一致していない場合は、`___delayLoadHelper2@8` または `___delayLoadHelper@8` を未解決の外部シンボルとして報告するリンカー エラーが発生します。  前者は新しいリンカーと古い delayimp.lib の組み合わせ、後者は古いリンカーと新しい delayimp.lib の組み合わせを意味します。  
  
 未解決のリンカー エラーが発生した場合は、ヘルパー関数が格納される delayimp.lib で [dumpbin \/linkermember](../../build/reference/linkermember.md):1 を実行して、どちらのヘルパー関数が代わりに定義されているのかを確認します。  ヘルパー関数は、オブジェクト ファイルで定義されている場合もあります。その場合は、[dumpbin \/symbols](../../build/reference/symbols.md) を実行して `delayLoadHelper(2)` を探します。  
  
 Visual C\+\+ 6.0 のリンカーを使用していることがわかっている場合は、次の操作を行います。  
  
-   遅延読み込みヘルパーの .lib ファイルまたは .obj ファイルで **dumpbin** を実行して、**\_\_delayLoadHelper2** が定義されているかどうかを確認します。  定義されていない場合、リンクは失敗します。  
  
-   遅延読み込みヘルパーの .lib ファイルまたは .obj ファイルで **\_\_delayLoadHelper** を定義します。  
  
## ユーザー定義のヘルパー関数  
 独自のヘルパー関数を定義していて、現在のバージョンの Visual C\+\+ を使用する場合は、次の操作を行います。  
  
-   ヘルパー関数の名前を **\_\_delayLoadHelper2** に変更します。  
  
-   遅延記述子 \(delayimp.h 内の ImgDelayDescr\) のポインターが、32 ビットのプログラムと 64 ビットのプログラムの両方で適切に機能するように、絶対アドレス \(VA\) から相対アドレス \(RVA\) に変更されています。このため、それらのアドレスをポインターに変換し直す必要があります。  新しい関数として、PFromRva \(delayhlp.cpp 内\) が導入されています。  記述子の各フィールドでこの関数を使用すると、32 ビットのポインターまたは 64 ビットのポインターに変換し直すことができます。  既定の遅延読み込みヘルパー関数は、従来と同じようにテンプレートとして利用できます。  
  
## 遅延読み込みされた DLL に対するすべてのインポートの読み込み  
 リンカーは、遅延読み込みをするように指定した DLL から、すべてのインポートを読み込むことができます。  詳細については、「[遅延読み込みされた DLL に対するすべてのインポートの読み込み](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)」を参照してください。  
  
## 参照  
 [Understanding the Helper Function](http://msdn.microsoft.com/ja-jp/6279c12c-d908-4967-b0b3-cabfc3e91d3d)
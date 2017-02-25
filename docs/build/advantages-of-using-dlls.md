---
title: "DLL の利点 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL [C++], 利点"
  - "動的リンク [C++]"
  - "動的読み込みリンク [C++]"
  - "リンク [C++], 動的と静的"
  - "リンク [C++], 動的と静的"
ms.assetid: 8956c8ee-e7b3-446f-a0c6-462381747690
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# DLL の利点
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

動的リンクには、以下の利点があります。  
  
-   メモリを節約し、スワップ処理を抑制します。  メモリ内の 1 つの DLL を複数のプロセス間で共有することにより、複数のプロセスが 1 つの DLL を同時に使うことができます。  スタティック リンク ライブラリでビルドされたアプリケーションの場合は、Windows が各アプリケーション用のライブラリ コードをメモリに読み込む必要があります。  
  
-   ディスク容量を節約します。  複数のアプリケーションが、ディスク上の DLL を共有できます。  スタティック リンク ライブラリでビルドされたアプリケーションの場合は、実行可能イメージにリンクされたライブラリ コードを別コピーとして持っています。  
  
-   DLL のアップグレードが簡単です。  DLL 内の関数が変更されても、引数や戻り値が変わらない限り、その関数を利用するアプリケーションの再コンパイルや再リンクの必要はありません。  静的リンクのオブジェクト コードの場合は、関数が変更されると、アプリケーションをリンクし直す必要があります。  
  
-   出荷後のサポートが可能です。  たとえば、アプリケーションの出荷時には利用できなかったディスプレイをサポートするよう、ディスプレイ ドライバー DLL を後から変更することもできます。  
  
-   複数言語対応のプログラムをサポートします。  異なるプログラミング言語で書かれたプログラムでも、関数の呼び出し規約に従う限り、同じ DLL 関数を呼び出すことができます。  ただし、引数がスタックにプッシュされる順序、スタックのクリアをアプリケーションと関数のどちらが行うか、引数のレジスタ渡しの有無に関しては、使用する側のプログラムと DLL 関数の間に互換性が成立している必要があります。  
  
-   MFC ライブラリ クラスを拡張する機構を提供します。  既存の MFC クラスの派生クラスを作成し、MFC アプリケーションから使用可能な MFC 拡張 DLL に配置できます。  
  
-   アプリケーションの各国語バージョンの作成が簡単になります。  リソースを DLL に配置することによって、アプリケーションの各国語バージョンの作成は大幅に簡略可されます。  アプリケーションの各言語バージョンで使用する文字列を異なるリソース DLL に配置することによって、各言語バージョンがそれぞれに適切なリソースを読み込みます。  
  
 DLL を使った場合に逆に欠点となり得るのは、アプリケーションが単体では使えない点です。アプリケーションは、別個の DLL モジュールなしには動作しません。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [DLL からのエクスポート](../build/exporting-from-a-dll.md)  
  
-   [DLL と実行形式のリンク](../build/linking-an-executable-to-a-dll.md)  
  
-   [DLL の初期化](../build/initializing-a-dll.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [非 MFC DLL: 概要](../Topic/Non-MFC%20DLLs:%20Overview.md)  
  
-   [MFC と静的にリンクされるレギュラー DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [MFC と動的にリンクされるレギュラー DLL](../Topic/Regular%20DLLs%20Dynamically%20Linked%20to%20MFC.md)  
  
-   [拡張 DLL : 概要](../build/extension-dlls-overview.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)
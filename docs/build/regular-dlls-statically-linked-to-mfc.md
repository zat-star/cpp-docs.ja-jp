---
title: "MFC と静的にリンクされるレギュラー DLL | Microsoft Docs"
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
  - "DLL [C++], 標準"
  - "標準 DLL [C++]"
  - "標準 DLL [C++], 静的リンク (MFC に)"
  - "静的にリンクされる DLL [C++]"
  - "USRDLL"
  - "USRDLL, 静的リンク (MFC に)"
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MFC と静的にリンクされるレギュラー DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC と静的にリンクするレギュラー DLL は、MFC を内部的に使用します。このレギュラー DLL のエクスポート関数は、MFC、非 MFC のどちらの実行可能ファイルからも呼び出すことができます。  名前からもわかるように、この種の DLL は MFC のスタティック リンク ライブラリ バージョンを使ってビルドされます。  通常、関数は C 言語の標準インターフェイスを使ってレギュラー DLL からエクスポートされます。  レギュラー DLL の記述、ビルド、使用方法の例については、サンプルの [DLLScreenCap](http://msdn.microsoft.com/ja-jp/2171291d-3a50-403b-90a1-d93c2acb4f4a) を参照してください。  
  
 USRDLL という用語は、Visual C\+\+ ドキュメントでは使用されなくなりました。  MFC に静的にリンクしたライブラリが以前の USRDLL に相当します。  
  
 MFC と静的にリンクされるレギュラー DLL の特徴は、以下のとおりです。  
  
-   クライアントの実行可能ファイルは、DLL を使用できる任意の言語 \(C、C\+\+、Pascal、Visual Basic など\) で記述できます。MFC アプリケーションでなくてもかまいません。  
  
-   複数のアプリケーションで使用される MFC のスタティック リンク ライブラリとリンクできます。  DLL のスタティック リンク バージョンのライブラリは、今後使用されなくなります。  
  
-   MFC のバージョン 4.0 以前では、MFC と静的にリンクされるレギュラー DLL と同じ種類の機能を各種の USRDLL が提供していました。  しかし、Visual C\+\+ バージョン 4.0 では USRDLL という用語は使用しません。  
  
 MFC と静的にリンクされるレギュラー DLL の必要条件は、以下のとおりです。  
  
-   `CWinApp` 派生クラスをインスタンス化します。  
  
-   MFC から提供される `DllMain` を使用します。  通常の MFC アプリケーションと同じく、DLL 固有のすべての初期化コードを `InitInstance` メンバー関数に配置し、終了コードを `ExitInstance` メンバー関数に配置します。  
  
-   USRDLL という用語は使用されませんが、コンパイラのコマンド ラインではまだ "**\_USRDLL**" を定義する必要があります。  この定義により、MFC ヘッダーファイルから取り込まれる宣言が決まります。  
  
 レギュラー DLL には、MFC アプリケーションの場合と同じく、`CWinApp` 派生クラスと、そのアプリケーション クラスの 1 つのオブジェクトの存在が必要です。  ただし、アプリケーションの `CWinApp` オブジェクトはメイン メッセージ ポンプを備えていますが、DLL の `CWinApp` オブジェクトは備えていません。  
  
 `CWinApp::Run` の機構は DLL では使用できません。これは、アプリケーションがメイン メッセージ ポンプを所有しているためです。  DLL 側でモードレス ダイアログを開いたり、独自のメイン フレーム ウィンドウを備える場合には、まず DLL によりエクスポートされたルーチンをアプリケーションのメイン メッセージ ポンプから呼び出して、次にここから DLL のアプリケーション オブジェクトの `CWinApp::PreTranslateMessage` メンバー関数を呼び出す必要があります。  
  
 この関数の例については、DLLScreenCap サンプルを参照してください。  
  
 シンボルは、通常、標準 C インターフェイスを使ってレギュラー DLL からエクスポートされます。  レギュラー DLL からエクスポートされた関数の宣言は、次のようになります。  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 レギュラー DLL 内のメモリ割り当てはすべて、DLL の範囲内に収める必要があります。したがって、以下のポインターを呼び出し側の実行可能ファイルとやり取りすることはできません。  
  
-   MFC オブジェクトへのポインター  
  
-   MFC によって割り当てられたメモリへのポインター  
  
 呼び出し元の実行可能ファイルと DLL との間で上のポインターや MFC 派生オブジェクトをやり取りする場合は、拡張 DLL を作成する必要があります。  
  
 アプリケーションと DLL の間で、C ランタイム ライブラリによって割り当てられたメモリへのポインターをやり取りする場合は、そのデータのコピーを作成しておくと安全です。  これらのポインターを削除したり、サイズを変更しないでください。また、これらのポインターを使用する場合は、メモリのコピーを必ず作成してください。  
  
 MFC と静的にリンクされた DLL は、MFC 共有 DLL と動的にリンクすることはできません。  MFC と静的にリンクされた DLL は、その他の DLL と同じようにアプリケーションと動的に関連付けされ、アプリケーションはその他の DLL と同じようにリンクされます。  
  
 標準 MFC スタティック リンク ライブラリの名前は、「[MFC DLL の名前付け規約](../build/naming-conventions-for-mfc-dlls.md)」で説明される名前付け規約に従って付けられます。  ただし、MFC バージョン 3.0 以降では、リンクする MFC ライブラリのバージョンを手作業で指定する必要がなくなりました。  その代わりに、プリプロセッサの定義に基づいて、**\_DEBUG** や **\_UNICODE** などのように、MFC ヘッダーファイルが正しいバージョンを自動的に決定します。  MFC ヘッダー ファイルには、\/DEFAULTLIB ディレクティブが追加され、リンカーはこのディレクティブを参照してリンク先の MFC ライブラリのバージョンを判断します。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [レギュラー DLL の初期化](../Topic/Initializing%20Regular%20DLLs.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [DLL の構成要素としての MFC](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [レギュラー DLL でのデータベース、OLE、およびソケット拡張 DLL の使用](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [MFC DLL ウィザード](../mfc/reference/mfc-dll-wizard.md)  
  
-   [MFC と動的にリンクされるレギュラー DLL](../Topic/Regular%20DLLs%20Dynamically%20Linked%20to%20MFC.md)  
  
-   [拡張 DLLs](../build/extension-dlls-overview.md)  
  
## 参照  
 [DLL の種類](../build/kinds-of-dlls.md)
---
title: "拡張 DLL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afxdll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFXDLL ライブラリ"
  - "DLL [C++], 拡張機能"
  - "拡張 DLL [C++]"
  - "拡張 DLL [C++], 拡張 DLL の概要"
  - "メモリ [C++], DLL"
  - "MFC DLL [C++], 拡張 DLL"
  - "MFC 拡張 DLL [C++]"
  - "リソースの共有 [C++]"
  - "共有 DLL バージョン [C++]"
  - "共有リソース [C++]"
ms.assetid: f69ac3d4-e474-4b1c-87a1-6738843a135c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 拡張 DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC 拡張 DLL は、既存の MFC ライブラリ クラスから派生した再利用可能なクラスを主に実装する DLL です。  
  
 MFC 拡張 DLL の特長と必要条件は、以下のとおりです。  
  
-   **\_AFXDLL** を定義してコンパイルした MFC アプリケーションをクライアント実行可能ファイルにします。  
  
-   拡張 DLL は、MFC と動的にリンクされるレギュラー DLL から使用することもできます。  
  
-   拡張 DLL のコンパイルは、`_AFXEXT` を定義して行います。  この結果、**\_AFXDLL** が強制的に定義され、正しい宣言が MFC ヘッダー ファイルから引き出されます。  また、DLL のビルド時に **AFX\_EXT\_CLASS** が **\_\_declspec\(dllexport\)** として定義されます。この定義は、このマクロを使って拡張 DLL 内のクラスを宣言する場合に必要です。  
  
-   拡張 DLL では、`CWinApp` の派生クラスをインスタンス化はしないでください。その代わりに、このオブジェクトの提供をクライアント アプリケーション \(または DLL\) に依存します。  
  
-   拡張 DLL では、`DllMain` 関数を提供し、その関数内で必要な初期化を行う必要があります。  
  
 拡張 DLL は、MFC のダイナミック リンク ライブラリ バージョン \(MFC の共有バージョン\) を使ってビルドされます。  ただし、拡張 DLL を使用できるのは、MFC の共有バージョンを使ってビルドされた MFC の実行可能ファイル \(アプリケーションまたはレギュラー DLL\) だけです。  クライアント アプリケーションおよび拡張 DLL の両方で、同じバージョンの MFCx0.dll を使用する必要があります。  拡張 DLL を使うと、MFC から新しいカスタム クラスを派生し、この拡張バージョンの MFC を、DLL を呼び出すアプリケーションに提供できます。  
  
 また、拡張 DLL を使うと、アプリケーションと DLL の間で MFC の派生オブジェクトをやり取りすることもできます。  やり取りされるオブジェクトに関連付けられたメンバー関数は、そのオブジェクトが作成されたモジュール内にあります。  これらの関数は MFC の共有 DLL バージョンの使用時に正しくエクスポートされるので、MFC のポインターまたは MFC の派生オブジェクトのポインターをアプリケーションと拡張 DLL との間で自由にやり取りできます。  
  
 MFC の拡張 DLL で MFC の共有バージョンを使う方法は、アプリケーションで MFC の共有バージョンを使う方法と同じです。ただし、考慮が必要な点がいくつかあります。  
  
-   拡張 DLL には `CWinApp` 派生オブジェクトがありません。  したがって、クライアント アプリケーションの `CWinApp` 派生オブジェクトを使用する必要があります。  クライアント アプリケーションには、メイン メッセージ ポンプ、アイドル ループなどが備わっています。  
  
-   MFC の拡張 DLL は、`DllMain` 関数内の `AfxInitExtensionModule` を呼び出します。  この関数の戻り値をチェックする必要があります。  `AfxInitExtensionModule` から 0 が返されると、`DllMain` 関数から 0 が返されます。  
  
-   拡張 DLL がアプリケーションに `CRuntimeClass` オブジェクトまたはリソースをエクスポートする場合、MFC の拡張 DLL は初期化中に **CDynLinkLibrary** オブジェクトを作成します。  
  
 MFC のバージョン 4.0 以前では、このような特徴を持つ DLL を AFXDLL と呼んでいました。  AFXDLL は、DLL のビルド中に定義された **\_AFXDLL** プリプロセッサ シンボルを参照します。  
  
 MFC の共有バージョン用のインポート ライブラリの名前は、「[MFC DLL の名前付け規則](../build/naming-conventions-for-mfc-dlls.md)」で説明される名前付け規約に従って付けられます。  Visual C\+\+ は、MFC DLL のプレビルド バージョンのほか、いくつかの非 MFC DLL も提供します。これらの DLL は、アプリケーションで使用したり、アプリケーションと共に頒布できます。  また、Program Files\\Microsoft Visual Studio フォルダーにインストールされている Redist.txt に説明があります。  
  
 .def ファイルを使ってエクスポートする場合は、以下のコードをヘッダー ファイルの先頭と末尾に記述します。  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 上の 4 行によって、コードは拡張 DLL 用に正しくコンパイルされます。  この行を追加しなかった場合は、DLL のコンパイルまたはリンクが正常に処理されない場合があります。  
  
 MFC へのポインターまたは MFC の派生オブジェクトを MFC DLL とやり取りする必要がある場合、その DLL は拡張 DLL である必要があります。  やり取りされるオブジェクトに関連付けられたメンバー関数は、そのオブジェクトが作成されたモジュール内にあります。  これらの関数は MFC の共有 DLL バージョンの使用時に正しくエクスポートされるので、MFC のポインターまたは MFC の派生オブジェクトのポインターをアプリケーションと拡張 DLL との間で自由にやり取りできます。  
  
 C\+\+ の名前の混乱を避け、またエクスポート問題に対処するために、拡張 DLL のエクスポート リストは同じ DLL のデバッグ バージョンとリテール版では異なる場合があります。また、対応するプラットフォームが異なる DLL の間でも異なる場合があります。  リテール版の MFCx0.dll には、約 2,000 のエクスポート エントリ ポイントがあります。また、デバッグ バージョンの MFCx0.dll には、約 3,000 のエクスポート エントリ ポイントがあります。  
  
## メモリ管理  
 MFCxx.dll やすべての拡張 DLL は、クライアント アプリケーションのアドレス空間に読み込まれ、同じアプリケーション内にあるかのように、同じメモリ アロケーターを使用し、同じ方法でリソースを読み込み、MFC のグローバル状態も共有します。  この点が重要になるのは、非 MFC DLL ライブラリやレギュラー DLL ではこれとまったく逆のことが行われ、各 DLL が独自のメモリ プールから割り当てられるためです。  
  
 拡張 DLL に割り当てられたメモリは、アプリケーションが確保した他のオブジェクトも自由に使用できます。  また、MFC と動的にリンクされたアプリケーションにエラーが発生しても、オペレーティング システムの保護機能によって、DLL を共有している他の MFC アプリケーションの整合性が保持されます。  
  
 同じように、リソースの読み込み元である現在の実行可能ファイルなど、他のグローバルな MFC の状態も、クライアント アプリケーションとすべての MFC 拡張 DLL の間および MFCx0.dll 自体の間で共有されます。  
  
## リソースやクラスの共有  
 リソースのエクスポートには、リソース リストを使います。  各アプリケーションには、**CDynLinkLibrary** オブジェクトの一方向リストが含まれています。  リソースを読み込む標準的な MFC 実装では、リソースを検索するとき、まず現在のリソース モジュール \(`AfxGetResourceHandle`\) を探します。ここで見つからないときは、**CDynLinkLibrary** オブジェクトのリストを順に探して必要なリストを読み込みます。  
  
 リストを検索する場合、多少速度が低下することとリソース ID 範囲の管理が必要なことが欠点です。  複数の拡張 DLL にリンクされるクライアント アプリケーション側で、DLL のインスタンス ハンドルを指定しなくても、DLL が提供する任意のリソースを使用できるという利点もあります。  `AfxFindResourceHandle` は、リソース リストを検索して一致するリソースを見つけるのに使われる API です。  リソースの名前と型を受け取り、最初に一致したリソース ハンドル \(または NULL\) を返します。  
  
 リソース リストを検索せず、特定の場所からリソースを読み込む場合は、`AfxGetResourceHandle` 関数を使って古いハンドルを保存し、`AfxSetResourceHandle` 関数を使って新規ハンドルを設定します。  クライアント アプリケーションに戻る前に、元のリソース ハンドルを必ず復元してください。  メニューを明示的に読み込む例については、MFC サンプル [DLLHUSK](http://msdn.microsoft.com/ja-jp/dfcaa6ff-b8e2-4efd-8100-ee3650071f90) にある Testdll2.cpp を参照してください。  
  
 MFC の名前を指定して、MFC オブジェクトを動的に作成する場合も同じです。  MFC オブジェクトの逆シリアル化機構を利用するには、`CRuntimeClass` の全オブジェクトを登録する必要があります。この機構では、要求された型の C\+\+ オブジェクトを、以前に格納された型に基づいて動的に作成し、MFC オブジェクトを再構築します。  
  
 MFC サンプル [DLLHUSK](http://msdn.microsoft.com/ja-jp/dfcaa6ff-b8e2-4efd-8100-ee3650071f90) の場合、リソース リストは次のようになります。  
  
```  
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE  
               |                      |  
          TESTDLL2.DLL           TESTDLL2.DLL  
               |                      |  
          TESTDLL1.DLL           TESTDLL1.DLL  
               |                      |  
           MFCOxxD.DLL                |  
               |                      |  
           MFCDxxD.DLL                |  
               |                      |  
            MFCxxD.DLL            MFCxx.DLL  
```  
  
 *xx* はバージョン番号です。たとえば、42 はバージョン 4.2 を表します。  
  
 MFCxx.dll は、通常、リソース リストやクラス リストの最後にあります。  MFCxx.dll には、標準コマンド ID に対応するプロンプト文字列など、すべての標準 MFC リソースが含まれています。  したがって、この DLL をリストの最後に置くと、DLL とクライアント アプリケーションでは標準 MFC リソースの独自のコピーを持つ必要がなくなり、MFCxx.dll 内の共有リソースに依存できるようになります。  
  
 すべての DLL のリソース名とクラス名をクライアント アプリケーションの名前空間に結合した場合は、ID や名前を選択するときに注意が必要です。  
  
 [DLLHUSK](http://msdn.microsoft.com/ja-jp/dfcaa6ff-b8e2-4efd-8100-ee3650071f90) サンプルでは、複数のヘッダー ファイルを使って、共有リソースの名前空間を管理します。  
  
 MFC 拡張 DLL が各アプリケーション用の追加データを保持する必要がある場合は、**CDynLinkLibrary** から新しいクラスを派生させ、そのクラスを `DllMain` 内に作成できます。  DLL は、実行時に現在のアプリケーションの **CDynLinkLibrary** オブジェクト リストから特定の拡張 DLL 用のオブジェクトを探し出します。  
  
### 目的に合ったトピックをクリックしてください  
  
-   [拡張 DLL の初期化](../build/initializing-extension-dlls.md)  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [テクニカル ノート 35: Visual C\+\+ における複数のリソース ファイルとヘッダー ファイルの使用](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)  
  
-   [テクニカル ノート 33: MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)  
  
-   [MFC と静的にリンクされるレギュラー DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [MFC と動的にリンクされるレギュラー DLL](../Topic/Regular%20DLLs%20Dynamically%20Linked%20to%20MFC.md)  
  
-   [レギュラー DLL でのデータベース、OLE、およびソケット拡張 DLL の使用](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)
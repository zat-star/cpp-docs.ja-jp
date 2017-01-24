---
title: "テクニカル ノート 11: DLL の構成要素としての MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.dll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_USRDLL シンボル"
  - "DLL [C++], リンク"
  - "MFC DLL [C++], リンク (MFC への通常の DLL の)"
  - "TN011"
  - "USRDLL, コンパイラ スイッチ"
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
caps.latest.revision: 20
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 11: DLL の構成要素としての MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、MFC ライブラリを Windows ダイナミック リンク ライブラリ \(DLL\) の一部として使えるようにする標準 DLL について説明します。  このテクニカル ノートは、Windows DLL とそのビルド方法に精通したプログラマを対象としています。  MFC ライブラリの拡張機能を作成するための MFC 拡張 DLL の詳細については、「[テクニカル ノート 33: MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)」を参照してください。  
  
## DLL インターフェイス  
 標準 DLL では、アプリケーションと DLL の間のインターフェイスは、C スタイルの関数または明示的にエクスポートしたクラスで指定されることが前提となります。  MFC のクラス インターフェイスはエクスポートできません。  
  
 DLL とアプリケーションの両方で MFC を使用する場合は、共有バージョンの MFC ライブラリを使用するか、ライブラリのコピーに静的にリンクするかをそれぞれが選択できます。  アプリケーションと DLL の両方が、標準バージョンの MFC ライブラリの 1 つを使用することもあります。  
  
 標準 DLL には次のような利点があります。  
  
-   DLL を使用するアプリケーションは、MFC を使用する必要がありません。また、Visual C\+\+ アプリケーションでなくてもかまいません。  
  
-   MFC と静的にリンクする標準 DLL のサイズは、使用されてリンクされる MFC と C のランタイム ルーチンにのみ依存します。  
  
-   MFC と動的にリンクする標準 DLL では、MFC の共有バージョンを使用することで大幅なメモリの節約を期待できます。  ただし、DLL と共有 DLL、Mfc*\<version\>*.dll や Msvvcrt*\<version\>*、.dll を配布する必要があります。  
  
-   DLL のデザインはクラスの実装方法に依存しません。  独自のデザインの DLL では、必要な API だけをエクスポートします。  そのため、実装が変わっても、標準 DLL は同じように使用できます。  
  
-   MFC と静的にリンクする標準 DLL では、DLL とアプリケーションの両方で MFC を使用する場合に、MFC のバージョンがアプリケーションと DLL で異なっていても問題はありません。  MFC ライブラリは各 DLL または EXE と静的にリンクされるので、どのバージョンを使っても問題はありません。  
  
## API の制約  
 MFC の機能には、DLL バージョンでは使用できないものがあります。これは、技術上の制約による場合と、そのサービスが通常はアプリケーションから提供されるためという理由による場合があります。  現在のバージョンの MFC では、使用できない関数は `CWinApp::SetDialogBkColor` だけです。  
  
## 独自の DLL のビルド  
 MFC と静的にリンクする標準 DLL をコンパイルするときは、シンボル `_USRDLL` と `_WINDLL` を定義する必要があります。  また、独自の DLL のコードは次のコンパイラ スイッチを使ってコンパイルする必要があります。  
  
-   **\/D\_WINDLL** は DLL のコンパイルを意味します。  
  
-   **\/D\_USRDLL** は標準 DLL のビルドを意味します。  
  
 MFC と動的にリンクする標準 DLL をコンパイルするときも、これらのシンボルを定義し、コンパイラ スイッチを使用する必要があります。  さらに、シンボル `_AFXDLL` を定義し、次のコンパイラ スイッチを使用して DLL のコードをコンパイルする必要があります。  
  
-   **\/D\_AFXDLL** は、MFC と動的にリンクする標準 DLL のビルドを意味します。  
  
 アプリケーションと DLL 間のインターフェイス \(API\) は明示的にエクスポートしてください。  独自のインターフェイスは低帯域に定義して、できるだけ C インターフェイスを使うことをお勧めします。  直接的な C インターフェイスの方が、複雑な C\+\+ クラスより保守が簡単です。  
  
 独自の API は別のヘッダー ファイルに記述し、C と C\+\+ の両方のファイルにインクルードできるようにします。  例については、" MFC サンプル [DLLScreenCap](../top/visual-cpp-samples.md) のヘッダー ファイル ScreenCap.h を参照してください。  独自の関数をエクスポートするには、関数をモジュール定義 \(.DEF\) ファイルの `EXPORTS` セクションに入れるか、関数定義に `__declspec(dllexport)` を含めます。  これらの関数をクライアント実行可能ファイルにインポートするには、`__declspec(dllimport)` を使用します。  
  
 MFC と動的にリンクする標準 DLL では、エクスポートされるすべての関数の先頭に `AFX_MANAGE_STATE` マクロを追加する必要があります。  このマクロは、現在のモジュール ステートを DLL 用に設定します。  このマクロを使用するには、DLL からエクスポートされる関数の先頭に次のコード行を追加します。  
  
 `AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`  
  
## WinMain \-\> DllMain  
 MFC ライブラリでは、Win32 の標準の `DllMain` エントリ ポイントが定義され、[CWinApp](../mfc/reference/cwinapp-class.md) からの派生オブジェクトが通常の MFC アプリケーションと同じように初期化されます。  DLL 固有の初期化処理はすべて、通常の MFC アプリケーションと同様に [InitInstance](../Topic/CWinApp::InitInstance.md) メソッドに記述します。  
  
 [CWinApp::Run](../Topic/CWinApp::Run.md) の機構は DLL では使用できません。これは、アプリケーションがメイン メッセージ ポンプを所有しているためです。  DLL でモードレス ダイアログを表示したり、独自のメイン フレーム ウィンドウを作成したりする場合は、まず DLL によってエクスポートされたルーチンをアプリケーションのメイン メッセージ ポンプから呼び出し、次にそのルーチンから [CWinApp::PreTranslateMessage](../Topic/CWinApp::PreTranslateMessage.md) を呼び出す必要があります。  
  
 この関数の使い方については、DLLScreenCap サンプルを参照してください。  
  
 MFC の提供する `DllMain` 関数は、DLL がアンロードされる前に、`CWinApp`  から派生したクラスの [CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md) メソッドを呼び出します。  
  
## 独自の DLL のリンク  
 MFC と静的にリンクする標準 DLL では、独自の DLL を Nafxcwd.lib または Nafxcw.lib とリンクし、C ランタイム ライブラリの Libcmt.lib ともリンクする必要があります。  これらのライブラリは既にビルドされており、Visual C\+\+ のセットアップの実行時に指定してインストールできます。  
  
## サンプル コード  
 サンプル全体については、「MFC サンプル」のサンプル プログラム DLLScreenCap を参照してください。  このサンプルでは、次の点に注目してください。  
  
-   コンパイラ フラグは、DLL とアプリケーションの間で異なります。  
  
-   リンク行と .DEF ファイルは、DLL とアプリケーションの間で異なります。  
  
-   DLL を使用するアプリケーションは、C\+\+ で作成されていなくてもかまいません。  
  
-   アプリケーションと DLL の間のインターフェイスは、C または C\+\+ で使用できる API であり、DLLScreenCap.def でエクスポートされます。  
  
 次の例では、MFC と静的にリンクする標準 DLL で定義される API を示します。  この例では、C\+\+ ユーザーのために宣言を `extern "C" { }` ブロックで囲んでいます。  この方法は、いくつかの利点があります。  まず、DLL API を非 C\+\+ クライアント アプリケーションでも使えます。  第 2 の利点として、C\+\+ の名前修飾がエクスポート名に適用されないため、DLL のオーバーロードが減ります。  第 3 の利点として、.DEF ファイルへの明示的な追加がさらに簡単になり \(序数によるエクスポート\)、名前の変更を心配する必要がなくなります。  
  
```  
#ifdef __cplusplus  
extern "C" {  
#endif  /* __cplusplus */  
  
struct TracerData  
{  
    BOOL    bEnabled;  
    UINT    flags;  
};  
  
BOOL PromptTraceFlags(TracerData FAR* lpData);  
  
#ifdef __cplusplus  
}  
#endif  
```  
  
 API で使用する構造体は、MFC クラスから派生するのではなく、API ヘッダーで定義します。  これにより、DLL とアプリケーションの間のインターフェイスが複雑になるのを避けられるほか、C プログラムからも DLL を使用できるようになります。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
---
title: "DEF ファイルを使った DLL からのエクスポート | Microsoft Docs"
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
  - ".def ファイル [C++], エクスポート (DLL から)"
  - "def ファイル [C++], エクスポート (DLL から)"
  - "エクスポート (DLL を) [C++], DEF ファイル"
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DEF ファイルを使った DLL からのエクスポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

モジュール定義ファイル \(.def\) は、テキスト ファイルです。DLL のさまざまな属性を記述する 1 つ以上のモジュール文が含まれています。  DLL の関数をエクスポートする **\_\_declspec\(dllexport\)** キーワードを使わない場合は、DLL に .def ファイルが必要です。  
  
 .def ファイルには、最低限でも以下のモジュール定義文を記述する必要があります。  
  
-   ファイルの先頭には、必ず LIBRARY 文を記述します。  LIBRARY 文は、その .def ファイルが所属する DLL を特定します。  LIBRARY 文の引数には、DLL の名前を指定します。  リンカーは、この名前を DLL のインポート ライブラリに配置します。  
  
-   EXPORTS 文には、DLL のエクスポート関数の名前と、オプションで序数値を指定します。  序数値を関数に割り当てるには、アット マーク \(@\) と数字の後に関数名を記述します。  序数値の場合は、1 から N の範囲で指定する必要があります。N は DLL のエクスポート関数の数字です。  関数を序数値でエクスポートする場合は、「[名前ではなく序数値による DLL 関数のエクスポート](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)」も参照してください。  
  
 たとえば、バイナリ サーチ ツリーを実装するコードを含む DLL は、以下のようになります。  
  
```  
LIBRARY   BTREE  
EXPORTS  
   Insert   @1  
   Delete   @2  
   Member   @3  
   Min   @4  
```  
  
 [MFC DLL ウィザード](../mfc/reference/mfc-dll-wizard.md)を使って MFC DLL を作成する場合、ウィザードはスケルトンの .def ファイルを作成し、プロジェクトに自動的に追加します。  エクスポートされる関数の名前は、このファイルに追加します。  非 MFC DLL の場合、.def ファイルをプログラマ自身が作成してプロジェクトに追加する必要があります。  
  
 C\+\+ ファイル内の関数をエクスポートする場合は、装飾名を .def ファイルに配置するか、標準の C リンケージで extern "C" を使ってエクスポート関数を定義する必要があります。  .def ファイル内に装飾名を配置する場合、装飾名を取得するには、[DUMPBIN](../build/reference/dumpbin-reference.md) ツールまたは [\/MAP](../build/reference/map-generate-mapfile.md) リンカー オプションを使います。  コンパイラが作成した装飾名は、コンパイラ独自のものであることに注意してください。  Visual C\+\+ コンパイラが作成した装飾名を .def ファイルに配置する場合は、DLL とリンクするアプリケーションは、同じバージョンの Visual C\+\+ を使ってビルドする必要があります。これは、呼び出しアプリケーション内の装飾名と、DLL の .def ファイル内のエクスポート名を一致させるためです。  
  
 [拡張 DLL](../build/extension-dlls-overview.md) をビルドする場合、および .def ファイルを使ってエクスポートする場合、エクスポート クラスを含むヘッダー ファイルの先頭と末尾に以下のコードを追加します。  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 上の行によって、内部で使用される MFC 変数やクラスに追加される MFC 変数が、拡張 DLL から確実にエクスポートされます。  たとえば、`DECLARE_DYNAMIC` を使って派生クラスを作成する場合、このマクロが展開して、`CRuntimeClass` メンバー関数をクラスに追加します。  上の 4 行をコードに追加しないと、DLL の不正なコンパイルまたはリンクが行われたり、クライアント アプリケーションが DLL とリンクするときにエラーが発生することになります。  
  
 DLL のビルド時に、リンカーは .def ファイルを使って、エクスポート ファイル \(.exp\) とインポート ライブラリ ファイル \(.lib\) を作成します。  次にリンカーはエクスポート ファイルを使って、.DLL ファイルを作成します。  DLL と暗黙的にリンクする実行形式は、ビルド時にインポート ライブラリと DLL をリンクします。  
  
 MFC 自体は、.def ファイルを使用して MFCx0.dll のクラスと関数をエクスポートします。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [\_\_declspec\(dllexport\) を使った DLL からのエクスポート](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS を使ったエクスポート\/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 言語の実行形式で使う C\+\+ 関数のエクスポート](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C\/C\+\+ 言語の実行形式で使う C 関数のエクスポート](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [エクスポート方式の使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\) を使ったアプリケーションへのインポート](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL の初期化](../build/initializing-a-dll.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [.def ファイル](../Topic/Module-Definition%20\(.Def\)%20Files.md)  
  
-   [モジュール定義ステートメントに関する規則](../build/reference/rules-for-module-definition-statements.md)  
  
-   [装飾名](../Topic/Decorated%20Names.md)  
  
-   [インライン関数のインポートとエクスポート](../Topic/Importing%20and%20Exporting%20Inline%20Functions.md)  
  
-   [相互インポート](../Topic/Mutual%20Imports.md)  
  
## 参照  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)
---
title: "__declspec(dllexport) を使った DLL からのエクスポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "dllexport"
  - "__declspec"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllexport) キーワード [C++]"
  - "エクスポート ディレクティブ [C++]"
  - "エクスポート (DLL を) [C++], __declspec(dllexport) キーワード"
  - "名前 [C++], DLL (によるエクスポート)"
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __declspec(dllexport) を使った DLL からのエクスポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft は、Visual C\+\+ の 16 ビット版のコンパイラに **\_\_export** を導入しました。この機能を使うと、エクスポート名が自動的に生成され、.lib ファイル内に配置されます。  この .lib ファイルは、DLL とリンクするスタティック ライブラリと同じように使用できます。  
  
 新しいバージョンのコンパイラでは、**\_\_declspec\(dllexport\)** キーワードを使うと、データ、関数、クラス、クラスのメンバー関数を DLL からエクスポートできます。  **\_\_declspec\(dllexport\)** は、オブジェクト ファイルにエクスポート ディレクティブを追加するので、.def ファイルは不要です。  
  
 この機能は、C\+\+ 関数の装飾名をエクスポートする場合に特に便利です。  名前の装飾には標準仕様がないので、エクスポート関数の名前は、コンパイラのバージョン間で変わる場合があります。  **\_\_declspec\(dllexport\)** を使用する場合は、名前付け規約の変更に対応するためだけに、DLL とその従属する .exe ファイルを再コンパイルする必要があります。  
  
 序数、NONAME、PRIVATE など、多くのエクスポート ディレクティブは、.def ファイル内にしか作成されないので、これらの属性を .def ファイルを使用せずに指定することはできません。  ただし、.def ファイルに加えて **\_\_declspec\(dllexport\)** を使うと、ビルド エラーが発生しません。  
  
 関数をエクスポートするには、呼び出し規約キーワードが指定されている場合、**\_\_declspec\(dllexport\)** キーワードは呼び出し規約キーワードの左に記述します。  たとえば、次のようになります。  
  
```  
__declspec(dllexport) void __cdecl Function1(void);  
```  
  
 クラス内のすべてのパブリック データ メンバーおよびメンバー関数をエクスポートするには、次のように、クラス名の左にキーワードを記述します。  
  
```  
class __declspec(dllexport) CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
> [!NOTE]
>  `__declspec(dllexport)` は、`__clrcall` 呼び出し規約を伴う関数には適用できません。  
  
 DLL のビルド時には通常、エクスポートする関数のプロトタイプやクラスを含むヘッダー ファイルを作成し、そのヘッダー ファイル内の宣言に **\_\_declspec\(dllexport\)** を追加します。  コードを読みやすくするために、次のように **\_\_declspec\(dllexport\)** 用のマクロを定義して、そのマクロをエクスポートする各シンボルに使います。  
  
```  
#define DllExport   __declspec( dllexport )   
```  
  
 **\_\_declspec\(dllexport\)** は、関数名を DLL のエクスポート テーブルに格納します。  テーブル サイズの最適化方法については、「[名前ではなく序数値による DLL 関数のエクスポート](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)」を参照してください。  
  
> [!NOTE]
>  DLL のソース コードを Win16 から Win32 に移植する場合は、**\_\_export** の各インスタンスを **\_\_declspec\(dllexport\)** に置き換えます。  
  
 参考として、Win32 の Winbase.h ヘッダー ファイルを検索してください。  **\_\_declspec\(dllimport\)** の使用例があります。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [.def ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [AFX\_EXT\_CLASS を使ったエクスポート\/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 言語の実行形式で使う C\+\+ 関数のエクスポート](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C\/C\+\+ 言語の実行形式で使う C 関数のエクスポート](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [エクスポート方式の使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\) を使ったアプリケーションへのインポート](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL の初期化](../build/initializing-a-dll.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [\_\_declspec キーワード](../cpp/declspec.md)  
  
-   [インライン関数のインポートとエクスポート](../Topic/Importing%20and%20Exporting%20Inline%20Functions.md)  
  
-   [相互インポート](../Topic/Mutual%20Imports.md)  
  
## 参照  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)
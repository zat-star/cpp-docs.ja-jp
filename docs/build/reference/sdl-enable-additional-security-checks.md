---
title: "/sdl (追加のセキュリティ チェックの有効化) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.SDLCheck"
dev_langs: 
  - "C++"
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /sdl (追加のセキュリティ チェックの有効化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

推奨される Security Development Lifecycle \(SDL\) のチェックを追加します。  これらのチェックには、エラーとしての追加のセキュリティ関連の警告、および追加の安全なコード生成機能が含まれます。  
  
## 構文  
  
```  
/sdl[-]  
```  
  
## 解説  
 **\/sdl** を指定すると、[\/GS](../Topic/-GS%20\(Buffer%20Security%20Check\).md) で提供されるベースライン セキュリティ チェックのスーパーセットが有効になり、**\/GS\-** がオーバーライドされます。  既定では、**\/sdl** は無効になっています。  **\/sdl\-** を指定すると、追加のセキュリティ チェックが無効になります。  
  
## コンパイル時のチェック  
 **\/sdl** を指定すると、次の警告がエラーとして有効になります。  
  
|\/sdl で有効になる警告|同等のコマンド ラインスイッチ|説明|  
|--------------------|---------------------|--------|  
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|\/we4146|単項マイナス演算子が符号なしの型に適用され、符号なしの結果になります。|  
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|\/we4308|負の整数定数が符号なしの型に変換されて、多くの場合は意味のない結果になります。|  
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|\/we4532|`continue`、`break`、または `goto` を `__finally`\/`finally` ブロック内に使用すると、異常終了時、未定義の動作になります。|  
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|\/we4533|変数の初期化コードが実行されません。|  
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|\/we4700|初期化されていないローカル変数が使用されます。|  
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|\/we4703|初期化されていない可能性のあるローカル ポインター変数が使用されます。|  
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|\/we4789|特定の C ランタイム \(CRT\) 関数の使用時にバッファー オーバーランが発生します。|  
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|\/we4995|[deprecated](../Topic/deprecated%20\(C-C++\).md) プラグマでマークされた関数が使用されます。|  
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|\/we4996|[deprecated](../../cpp/deprecated-cpp.md) でマークされた関数が使用されます。|  
  
## 実行時のチェック  
 **\/sdl** を有効にすると、実行時に次のチェックを実行するコードがコンパイラによって生成されます。  
  
-   **\/GS** の実行時バッファー オーバーラン検出の strict モードを有効にします。`#pragma strict_gs_check(push, on)` を使用したコンパイルと同等です。  
  
-   制限付きでポインターのサニタイズを行います。  逆参照がない式でも、ユーザー定義のデストラクターがない型でも、ポインターの参照は、`delete` の呼び出し後、無効なアドレスに設定されます。  これは、古いポインター参照の再使用を防止するために役立ちます。  
  
-   クラス メンバーの初期化を実行します。  すべてのクラス メンバーをオブジェクトのインスタンス化時にゼロに自動的に初期化します \(コンストラクターの実行前\)。  これは、コンストラクターが明示的に初期化しないクラス メンバーに関連付けられた、初期化されていないデータの使用を防止するために役立ちます。  
  
## コメント  
 詳細については、[警告、\/sdl、および初期化されていない変数の検出の向上](http://go.microsoft.com/fwlink/p/?LinkId=331012)に関するページを参照してください。  
  
#### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[全般\]** ページで、**\[SDL チェック\]** ドロップダウン リストからオプションを選択します。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)
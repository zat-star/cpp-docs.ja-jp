---
title: "/VERBOSE (進行状況メッセージの出力) | Microsoft Docs"
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
  - "/verbose"
  - "VC.Project.VCLinkerTool.ShowProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/VERBOSE リンカー オプション"
  - "依存関係 [C++], 依存関係の情報 (リンカー出力の)"
  - "リンカー [C++], 出力依存情報"
  - "リンク [C++], セッションの進行状況"
  - "進行状況メッセージの出力リンカー オプション"
  - "VERBOSE リンカー オプション"
  - "-VERBOSE リンカー オプション"
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /VERBOSE (進行状況メッセージの出力)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]  
```  
  
## 解説  
 リンカーは、リンク セッションの進行状況に関する情報を **\[出力\]** ウィンドウに送ります。  コマンド ラインでリンクを実行すると、この情報は標準出力に送られるため、ファイルにリダイレクトできます。  
  
|オプション|説明|  
|-----------|--------|  
|\/VERBOSE|リンク プロセスに関する詳細情報を表示します。|  
|\/VERBOSE:ICF|[\/OPT:ICF](../../build/reference/opt-optimizations.md) を使用した結果実行されたリンカー動作についての情報を表示します。|  
|\/VERBOSE:INCR|インクリメンタル リンク プロセスに関する情報を表示します。|  
|\/VERBOSE:LIB|検索されたライブラリだけを示す進行状況メッセージを表示します。<br /><br /> 表示される情報は、ライブラリ検索の進行状況、各ライブラリとオブジェクト名 \(完全パス\)、そのライブラリで解決されたシンボル、およびそのシンボルを参照しているオブジェクトの一覧です。|  
|\/VERBOSE:REF|[\/OPT:REF](../../build/reference/opt-optimizations.md) を使用した結果実行されたリンカー動作についての情報を表示します。|  
|\/VERBOSE:SAFESEH|[\/SAFESEH](../Topic/-SAFESEH%20\(Image%20has%20Safe%20Exception%20Handlers\).md) が指定されていない場合に、安全な例外処理との互換性がないモジュールの情報を表示します。|  
|\/VERBOSE:UNUSEDLIBS|イメージの作成時に使用されていないライブラリ ファイルに関する情報を表示します。|  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーを展開します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\[追加オプション\]** ボックスにオプションを入力します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)
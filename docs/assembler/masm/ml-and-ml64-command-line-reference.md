---
title: "ML and ML64 Command-Line Reference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ML"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/W* MASM compiler option"
  - "/c MASM compiler option"
  - "/EP MASM compiler option"
  - "/Fe MASM compiler option"
  - "/Zp MASM compiler option"
  - "/AT MASM compiler option"
  - "/Zm MASM compiler option"
  - "/Sf MASM compiler option"
  - "/Sp MASM compiler option"
  - "/w MASM compiler option"
  - "/Fl MASM compiler option"
  - "/coff MASM compiler option"
  - "/St MASM compiler option"
  - "/Cx MASM compiler option"
  - "/Sl MASM compiler option"
  - "/Cu MASM compiler option"
  - "MASM (Microsoft Macro Assembler), ML command-line reference"
  - "/FPi MASM compiler option"
  - "/Zf MASM compiler option"
  - "ML environment variable"
  - "/Fr MASM compiler option"
  - "/help MASM compiler option"
  - "/Sa MASM compiler option"
  - "/Zd MASM compiler option"
  - "/I MASM compiler option"
  - "/? MASM compiler option"
  - "/Bl MASM compiler option"
  - "/Fm MASM compiler option"
  - "/Fo MASM compiler option"
  - "command-line reference [ML]"
  - "/Sn MASM compiler option"
  - "/Gd MASM compiler option"
  - "/D* MASM compiler option"
  - "environment variables, ML"
  - "/Gc MASM compiler option"
  - "/F* MASM compiler option"
  - "/Sc MASM compiler option"
  - "/H MASM compiler option"
  - "/Zs MASM compiler option"
  - "/omf MASM compiler option"
  - "/Sg MASM compiler option"
  - "/Cp MASM compiler option"
  - "/Zi MASM compiler option"
  - "/nologo MASM compiler option"
  - "/Sx MASM compiler option"
  - "/WX MASM compiler option"
  - "/Ss MASM compiler option"
  - "command line, reference [ML]"
  - "/Ta MASM compiler option"
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# ML and ML64 Command-Line Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一つ以上のアセンブリ言語のソース ファイルをアセンブルしてリンクします。  コマンド ライン オプションでは大文字と小文字が区別されます。  
  
 ml64.exe の詳細については[MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md) を参照してください。  
  
## 構文  
  
```  
ML [[options]] filename [[ [[options]]  filename]]  
ML64 [[options]] filename [[ [[options]]  filename]]  
...  
[[/link linkoptions]]  
```  
  
#### パラメーター  
 `options`  
 次の表に示すオプション。  
  
|オプション|動作|  
|-----------|--------|  
|**\/AT**|有効な小さメモリ モデル修飾子のサポート。  .com ファイルの書式の要件に違反するコード コンストラクターのエラー メッセージを有効にします。  これは [.MODEL](../../assembler/masm/dot-model.md) **TINY** のディレクティブと同じではないことに注意してください。<br /><br /> ml64.exe 使用できません。|  
|**\/Bl** `filename`|別のリンカーを選択します。|  
|**\/c**|のみアセンブルします。  リンクします。|  
|**\/coff**|オブジェクト モジュール \(COFF\) \(Common Object File Format\) 形式の型が生成されます。  通常Win32 アセンブリ言語の開発に必要な余白サイズ。<br /><br /> ml64.exe 使用できません。|  
|**\/Cp**|すべてのユーザー id を保存する場合。|  
|**\/Cu**|大文字 \(既定値\) にすべての識別子を割り当てます。<br /><br /> ml64.exe 使用できません。|  
|**\/Cx**|保存はパブリック使用と外部シンボルにパッケージ化します。|  
|**\/D** `symbol`\[\[\=`value`\]\]|指定した名前のテキスト マクロを定義します。  `value` がない場合は null になります。  スペースで区切られた複数のトークンは引用符で囲む必要があります。|  
|**\/EP**|前処理されたソースの一覧を生成します \(STDOUT に送信\)。  「**\/Sf**」を参照してください。|  
|**\/ERRORREPORT** \[ **NONE** &#124; **PROMPT** &#124; **QUEUE** &#124;**SEND** \]|ml.exe または ml64.exe が実行時に失敗した場合これらの内部エラーに関する情報を Microsoft に送信するために **\/ERRORREPORT** を使用できます。<br /><br /> **\/ERRORREPORT** の詳細については、「[\/errorReport \(内部コンパイラ エラーの報告\)](../Topic/-errorReport%20\(Report%20Internal%20Compiler%20Errors\).md)」を参照してください。|  
|**\/F** `hexnum`|`hexnum` バイトのスタック サイズを設定します。これは **\/link\/STACK** と同じです :`number`\)。  値 16 は16 進数で指定する必要があります。  **\/F** と `hexnum` 間には空白が必要です。|  
|**\/Fe** `filename`|実行可能ファイルを付けます。|  
|**\/Fl**\[\[`filename`\]\]|アセンブルしたコード リストを生成します。  「**\/Sf**」を参照してください。|  
|**\/Fm**\[\[`filename`\]\]|リンカーのマップ ファイルを作成します。|  
|**\/Fo** `filename`|オブジェクト ファイルを付けます。  詳細については" 解説 " を参照してください。|  
|**\/FPi**|エミュレーター内を修正する浮動小数点演算 \(混合言語のみ\) に対して生成します。<br /><br /> ml64.exe 使用できません。|  
|**\/Fr**\[\[`filename`\]\]|ソース ブラウザーの .sbr ファイルを生成します。|  
|**\/FR**\[\[`filename`\]\]|ソース ブラウザーの .sbr ファイルの拡張フォームが生成されます。|  
|**\/Gc**|FORTRAN または Pascal 形式の関数を呼び出し名前付け規則を使用して指定します。  **OPTION LANGUAGE:PASCAL** と同じです。<br /><br /> ml64.exe 使用できません。|  
|**\/Gd**|C スタイルの関数を呼び出し名前付け規則を使用して指定します。  **OPTION LANGUAGE:C** と同じです。<br /><br /> ml64.exe 使用できません。|  
|**\/GZ**|\_\_stdcall の関数を呼び出し名前付け規則を使用して指定します。  **OPTION LANGUAGE:STCALL** と同じです。<br /><br /> ml64.exe 使用できません。|  
|**\/H** `number`|外部名が重要な文字にラベルを付けるに制限します。  既定値は 31 文字です。<br /><br /> ml64.exe 使用できません。|  
|**\/help**|ML の呼び出し QuickHelp。|  
|**\/I** `pathname`|パスを示します。ファイルを設定します。  最大 10 **\/I** のオプションを使用できます。|  
|**\/nologo**|成功したアセンブリのメッセージを抑制します。|  
|**\/omf**|オブジェクト モジュールのオブジェクト \(OMF\) モジュール形式の型が生成されます。  **\/omf** は **\/c** を意味します ; ML.exe は OMF オブジェクトのリンクをサポートしていません。<br /><br /> ml64.exe 使用できません。|  
|**\/Sa**|使用可能なすべての情報を表示します。|  
|**\/safeseh**|例外ハンドラーがないかすべて [.SAFESEH](../Topic/.SAFESEH.md) で宣言された例外ハンドラーを含むものとしてオブジェクトを指定します。<br /><br /> ml64.exe 使用できません。|  
|**\/Sf**|リスティング ファイルに最初のパスリストを追加します。|  
|**\/Sl** `width`|各行の文字のソースの一覧の線の幅を設定します。  範囲は 60 ~ 255 または 0 です。  既定値は 0 です。  [ページ](../../assembler/masm/page.md) の幅と同じです。|  
|**\/Sn**|リストを生成するときにシンボル テーブルをオフにします。|  
|**\/Sp** `length`|ページあたりの行のソースの一覧ページの長さを設定します。  範囲は 10 ~ 255 または 0 です。  既定値は 0 です。  [ページ](../../assembler/masm/page.md) の長さと同じです。|  
|**\/Ss** `text`|ソースの一覧に表示するテキストを指定します。  [SUBTITLE](../../assembler/masm/subtitle.md) のテキストと同じです。|  
|**\/St** `text`|ソースの一覧のタイトルを指定します。  [タイトル](../../assembler/masm/title.md) のテキストと同じです。|  
|**\/Sx**|リストの有効性の条件をオンにします。|  
|**\/Ta** `filename`|名前から .asm の拡張子で終わるソース ファイルをアセンブルします。|  
|**\/w**|**\/W0 \/WX** と同じです。|  
|**\/W** `level`|警告レベルをここで `level` \= 012または 3. 設定します。|  
|**\/WX**|警告が生成されたエラー コードを返します。|  
|**\/X**|Ignore は環境のパスが含まれます。|  
|**\/Zd**|オブジェクト ファイルの行番号情報を生成します。|  
|**\/Zf**|すべてのシンボルをパブリックになります。|  
|**\/Zi**|オブジェクト ファイルの CodeView 情報を生成します。|  
|**\/Zm**|MASM5.1 の互換性を最大にするための **M510** オプションが有効になります。<br /><br /> ml64.exe 使用できません。|  
|**\/Zp**\[\[`alignment`\]\]|指定したバイト境界上にパックの構造体。  `alignment` は12または 4. などがあります。|  
|**\/Zs**|構文だけをチェックを実行します。|  
|**\/?**|ML のコマンド ライン構文の簡単な説明を表示します。|  
  
 `filename`  
 ファイルの名前。  
  
 `linkoptions`  
 LINK オプション。  詳細については、「[リンカー オプション](../../build/reference/linker-options.md)」を参照してください。  
  
## 解説  
 ML と ML64 に対してコマンド ライン オプションは配置に依存します。  たとえばML と ML64 が **\/c** 複数のオプションを使用できるため **\/Fo** 対応するオプションが **\/c** の前に指定する必要があります。  次のコマンド ラインの例はアセンブリ ファイルの指定のオブジェクト ファイルの仕様を示します :  
  
 **ml.exe \/Fo a1.obj \/c a.asm \/Fo b1.obj \/c b.asm**  
  
## 環境変数  
  
|変数|Description|  
|--------|-----------------|  
|INCLUDE|検索パスを含むファイルを指定します。|  
|ML|既定のコマンド ライン オプションを指定します。|  
|複数|一時ファイルのパスを指定します。|  
  
## 参照  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)   
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)
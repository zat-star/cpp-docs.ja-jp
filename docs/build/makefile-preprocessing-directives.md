---
title: "メイクファイルのプリプロセス ディレクティブ | Microsoft Docs"
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
  - "!UNDEF"
  - "!INCLUDE"
  - "!IFNDEF"
  - "!MESSAGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!CMDSWITCHES ディレクティブ"
  - "!ELSE ディレクティブ"
  - "!ELSEIF ディレクティブ"
  - "!ELSEIFDEF ディレクティブ"
  - "!ELSEIFNDEF ディレクティブ"
  - "!ENDIF ディレクティブ"
  - "!ERROR ディレクティブ"
  - "!IF ディレクティブ"
  - "!IFDEF ディレクティブ"
  - "!IFNDEF ディレクティブ"
  - "!INCLUDE ディレクティブ"
  - "!MESSAGE ディレクティブ"
  - "!UNDEF ディレクティブ"
  - "CMDSWITCHES ディレクティブ"
  - "ディレクティブ, メイクファイル処理"
  - "ELSE ディレクティブ"
  - "ELSEIF ディレクティブ"
  - "ELSEIFDEF ディレクティブ"
  - "ELSEIFNDEF ディレクティブ"
  - "ENDIF ディレクティブ"
  - "ERROR ディレクティブ"
  - "IF ディレクティブ"
  - "IFDEF ディレクティブ"
  - "IFNDEF ディレクティブ"
  - "INCLUDE ディレクティブ"
  - "メイクファイル, プリプロセス ディレクティブ"
  - "MESSAGE ディレクティブ"
  - "NMAKE プログラム, 式"
  - "NMAKE プログラム, プリプロセス ディレクティブ"
  - "プリプロセス ディレクティブ, メイクファイル"
  - "UNDEF ディレクティブ"
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# メイクファイルのプリプロセス ディレクティブ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プリプロセス ディレクティブの表記では、大文字と小文字が区別されません。  先頭の感嘆符 \(\!\) は、行の先頭で指定する必要があります。  感嘆符の後には、インデントのために 0 個以上の空白またはタブを配置できます。  
  
 **\!CMDSWITCHES**  
 {**\+**&#124;**–**}*option*...  リストにある各 *option* をオンまたはオフにします。  空白やタブは、\+ 演算子または – 演算子の前に配置する必要があります。演算子と[オプション文字](../Topic/NMAKE%20Options.md)の間には何も配置できません。  文字では大文字と小文字が区別されず、スラッシュ \(\/\) なしで指定します。  一部のオプションをオンにし、残りのオプションをオフにするには、それぞれに **\!CMDSWITCHES** を指定します。  
  
 メイクファイルで使用できるのは、\/D、\/I、\/N、および \/S だけです。  Tools.ini では、\/F、\/HELP、\/NOLOGO、\/X、および \/? を除くすべてのオプションを使用できます。  記述ブロックで指定された変更は、次の記述ブロックまで有効にはなりません。  このディレクティブでは、**MAKEFLAGS** が更新されます。**MAKEFLAGS** が指定されている場合は、変更が再帰時に継承されます。  
  
 **\!ERROR**  *text*  
 エラー U1050 で *text* を表示し、\/K、\/I、**.IGNORE**、**\!CMDSWITCHES**、またはダッシュ \(–\) コマンド修飾子が使用されている場合でも、NMAKE を中断します。  *text* の前の空白やタブは無視されます。  
  
 **\!MESSAGE**  *text*  
 *text* を標準出力に表示します。  *text* の前の空白やタブは無視されます。  
  
 **\!INCLUDE**\[\] **\<***ファイル名***\>**\[\]  
 *filename* をメイクファイルとして読み取り、現在のメイクファイルで処理を続けます。  NMAKE は、指定されたディレクトリまたは現在のディレクトリの、再帰的に親メイクファイルのディレクトリを通じて filename *が* 山かっこで囲まれている\)、INCLUDE 環境変数\<  \>に初期設定された **INCLUDE** マクロで指定されたディレクトリで囲まれている場合は、最初に、検索します。  **.SUFFIXES** 設定、**.PRECIOUS**、および推論規則を再帰的なメイクファイルに渡すために使用すると便利です。  
  
 **\!IF**  `constantexpression`  
 `constantexpression` が 0 以外の値に評価される場合に、**\!IF** と次の **\!ELSE** または `!ENDIF` の間のステートメントを処理します。  
  
 **\!IFDEF**  *macroname*  
 *macroname* が定義されている場合に、`!IFDEF` と次の **\!ELSE** または `!ENDIF` の間のステートメントを処理します。  null マクロは、定義されているものと判断されます。  
  
 **\!IFNDEF**  *macroname*  
 *macroname* が定義されていない場合に、**\!IFNDEF** と次の **\!ELSE** または `!ENDIF` の間のステートメントを処理します。  
  
 **\!ELSE**\[**IF** *constantexpression* &#124; **IFDEF** *macroname*&#124; **IFNDEF** *macroname*\]  
 前の **\!IF** ステートメント、`!IFDEF` ステートメント、または **\!IFNDEF** ステートメントが 0 に評価された場合に、**\!ELSE** と次の `!ENDIF` の間のステートメントを処理します。  省略可能なキーワードを使用すると、プリプロセスをさらに細かく制御できます。  
  
 **\!ELSEIF**  
 **\!ELSE IF** と同義です。  
  
 **\!ELSEIFDEF**  
 **\!ELSE IFDEF** と同義です。  
  
 **\!ELSEIFNDEF**  
 **\!ELSE IFNDEF** と同義です。  
  
 `!ENDIF`  
 **\!IF**、`!IFDEF`、**\!IFNDEF** の各ブロックの終了を示します。  同じ行の `!ENDIF` の後のテキストは無視されます。  
  
 **\!UNDEF**  *macroname*  
 *macroname* を未定義にします。  
  
## 参照  
 [メイクファイルのプリプロセス](../Topic/Makefile%20Preprocessing.md)
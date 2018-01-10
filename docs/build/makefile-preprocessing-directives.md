---
title: "メイクファイルのプリプロセス ディレクティブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
dev_langs: C++
helpviewer_keywords:
- ERROR directive
- '!MESSAGE directive'
- IF directive
- '!UNDEF directive'
- IFDEF directive
- '!ELSEIF directive'
- '!IFDEF directive'
- '!IF directive'
- UNDEF directive
- '!CMDSWITCHES directive'
- ENDIF directive
- directives, makefile preprocessing
- INCLUDE directive
- IFNDEF directive
- preprocessing directives, makefiles
- '!IFNDEF directive'
- ELSEIFNDEF directive
- NMAKE program, expressions
- ELSEIF directive
- '!ERROR directive'
- '!ENDIF directive'
- MESSAGE directive
- '!INCLUDE directive'
- '!ELSEIFNDEF directive'
- CMDSWITCHES directive
- '!ELSEIFDEF directive'
- '!ELSE directive'
- NMAKE program, preprocessor directives
- makefiles, preprocessing directives
- ELSE directive
- ELSEIFDEF directive
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1bc73a86b0772b13731aaf7ac4e2ef0760caa8a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="makefile-preprocessing-directives"></a>メイクファイルのプリプロセス ディレクティブ
前処理ディレクティブは、大文字小文字が区別されません。 初期の感嘆符 (!) は必要があります、行の先頭に表示されます。 ゼロ以上のスペースまたはタブは、インデント、感嘆符の後に表示できます。  
  
 **!CMDSWITCHES**  
 {**+**&#124;です。 **-** }*オプション*しています.各をオンに*オプション*オンまたはオフを一覧表示します。 スペースまたはタブは、前に指定する必要があります、+ または - 演算子です。演算子の間では何も配置と[文字をオプション](../build/nmake-options.md)です。 文字は、大文字小文字は区別されません、スラッシュ (/) せず指定されます。 一部のオプションおよび他のユーザーを無効にする場合の別の仕様を使用して**!CMDSWITCHES**です。  
  
 のみの/D/メイクファイルでは、/N、および/S を使用できます。 Tools.ini、すべてのオプションは/F、/HELP、/NOLOGO を除く許可/X、および/ください。 記述ブロックで指定された変更では、次の記述ブロックされるまで有効になりません。 このディレクティブを更新**MAKEFLAGS**; 場合、再帰の中に変更が継承された**MAKEFLAGS**を指定します。  
  
 **!エラー***テキスト*   
 表示*テキスト*エラー U1050 が停止した、(nmake の) 場合でもで/K、/、**です。無視**、 **!CMDSWITCHES**、またはダッシュ (-) のコマンド修飾子を使用します。 スペースまたはタブで前に*テキスト*は無視されます。  
  
 **!メッセージ***テキスト*   
 表示*テキスト*を標準出力にします。 スペースまたはタブで前に*テキスト*は無視されます。  
  
 **!含める**[  **\<** ] *filename*[  **>** ]  
 読み取り*filename*メイクファイルでし、続けて現在のメイクファイルを使用します。 (Nmake の) 検索*filename*指定されているか、現在のディレクトリに次のいずれかのディレクトリを再帰的に親メイクファイルを次に場合、 *filename*が山かっこで囲まれている (\<>)、によって指定されたディレクトリで、 **INCLUDE**マクロで、最初は INCLUDE 環境変数に設定します。 渡す便利**です。サフィックス**設定、**です。貴重な**、および再帰的なメイクファイルを推論規則。  
  
 **!もし**  `constantexpression`  
 間でステートメントを処理**!IF**と次の**!ELSE**または`!ENDIF`場合`constantexpression`0 以外の値に評価します。  
  
 **!IFDEF***マクロ名*   
 間でステートメントを処理`!IFDEF`と次の**!ELSE**または`!ENDIF`場合*macroname*が定義されています。 Null マクロは、定義すると見なされます。  
  
 **!IFNDEF***マクロ名*   
 間でステートメントを処理**!IFNDEF**と次の**!ELSE**または`!ENDIF`場合*macroname*が定義されていません。  
  
 **!ELSE**[**IF** *constantexpression* &#124;です。**IFDEF** *macroname*&#124;です。**IFNDEF** *macroname*]  
 間でステートメントを処理**!ELSE**と次の`!ENDIF`場合は、前に**!IF**、 `!IFDEF`、または**!IFNDEF**ステートメントが 0 に評価されます。 省略可能なキーワードは、さらに前処理を制御できるようにします。  
  
 **!ELSEIF**  
 シノニム**!ELSE IF**です。  
  
 **!ELSEIFDEF**  
 シノニム**!他の IFDEF**です。  
  
 **!ELSEIFNDEF**  
 シノニム**!ELSE IFNDEF**です。  
  
 `!ENDIF`  
 末尾を示す、 **!IF**、 `!IFDEF`、または**!IFNDEF**ブロックします。 任意のテキストの後に`!ENDIF`同じ行には無視されます。  
  
 **!UNDEF***マクロ名*   
 未定義に*macroname*です。  
  
## <a name="see-also"></a>参照  
 [メイクファイルのプリプロセス](../build/makefile-preprocessing.md)
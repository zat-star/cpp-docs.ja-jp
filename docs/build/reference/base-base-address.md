---
title: "/BASE (ベース アドレス) | Microsoft Docs"
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
  - "/base"
  - "VC.Project.VCLinkerTool.BaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/BASE リンカー オプション"
  - "@ シンボル (ベース アドレスの)"
  - "アット マーク シンボル (ベース アドレスの)"
  - "ベース アドレス [C++]"
  - "BASE リンカー オプション"
  - "-BASE リンカー オプション"
  - "DLL [C++], リンク"
  - "環境変数 [C++], LIB"
  - "実行可能ファイル [C++], ベース アドレス"
  - "キー アドレス サイズ"
  - "LIB 環境変数"
  - "プログラム [C++], ベース アドレス"
  - "プログラム [C++], 防止 (再配置を)"
  - "セミコロン [C++], 指定子"
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
caps.latest.revision: 15
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /BASE (ベース アドレス)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/BASE:{address[,size] | @filename,key}  
```  
  
 \/BASE オプションでは、プログラムのベース アドレスを設定して、.exe ファイルの既定の配置場所 \(0x400000\) または DLL の既定の配置場所 \(0x10000000\) をオーバーライドします。  オペレーティング システムでは、プログラムをまず指定されたベース アドレスか既定のベース アドレスに読み込みます。  このとき、読み込み先に十分なメモリがないと、プログラムを別の場所に配置し直します。  この再配置を防ぐには、[\/FIXED](../../build/reference/fixed-fixed-base-address.md) オプションを指定します。  
  
 *address* が 64 KB の倍数でない場合、リンカーはエラーを生成します。オプションとしてプログラムのサイズを指定して、プログラムが指定したサイズに収まらない場合にリンカーが警告を出すようにできます。  
  
 コマンド ラインでは、別の方法でベース アドレスを指定できます。つまり、アット マーク \(@\) の後ろにファイル名 \(*filename*\) と *filename* ファイルの中のキー \(`key`\) を指定します。  この *filename* ファイルはテキスト ファイルとし、この中にプログラムが使うすべての DLL の場所とサイズを記述します。  リンカーは指定されているパスで *filename* を探します。パスが指定されていない場合は、環境変数 LIB で指定されているディレクトリを検索します。  *filename* ファイルでは、次の構文で 1 行につき DLL を 1 つ指定します。  
  
```  
  
key address [size] ;comment  
```  
  
 `key` は英数字から成る文字列です。key の大文字小文字は区別されません。  key では通常は DLL ファイル名を指定しますが、ほかの名前も指定できます。  `key` の後ろには、ベース *address* を C 言語の表記法、16 進表記法、または 10 進表記法で指定し、最後にオプションとして最大 `size` を指定します。  3 つの引数はすべて、スペースまたはタブで区切ります。  指定した `size` がプログラムに必要な仮想アドレス空間より小さい場合は、リンク時に警告が出力されます。  コメント `comment` は、セミコロン \(;\) で指定します。コメントは、アドレスやサイズ指定と同じ行に置くことも、独立した別の行に置くこともできます。  セミコロンから行の終わりまでの内容はすべて無視されます。  次は、ベース アドレス指定を示すファイルの一部です。  
  
```  
main   0x00010000    0x08000000    ; for PROJECT.exe  
one    0x28000000    0x00100000    ; for DLLONE.DLL  
two    0x28100000    0x00300000    ; for DLLTWO.DLL  
```  
  
 このファイル名を DLLS.txt とします。この情報を適用するためのコマンドを次に示します。  
  
```  
link dlltwo.obj /dll /base:@dlls.txt,two  
```  
  
## 解説  
 それぞれの DLL がアドレス空間内で重ならないようにベース アドレスを割り当てると、実行時のページングが軽減され、パフォーマンスが向上します。  
  
 別の方法としては、[NAME](../Topic/NAME%20\(C-C++\).md) ステートメントまたは [LIBRARY](../../build/reference/library.md) ステートメントの引数 *BASE* で、ベース アドレスを設定できます。  \/BASE オプションと [\/DLL](../../build/reference/dll-build-a-dll.md) オプションを併用すると、**LIBRARY** ステートメントと等価になります。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  **\[詳細\]** プロパティ ページをクリックします。  
  
4.  \[ベース アドレス\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)
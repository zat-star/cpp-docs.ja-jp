---
title: "/SECTION (セクション属性の指定) | Microsoft Docs"
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
  - "/section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SECTION リンカー オプション"
  - "セクション属性"
  - "SECTION リンカー オプション"
  - "-SECTION リンカー オプション"
ms.assetid: 92b69d81-e421-462e-b46f-7d0dff9b9d16
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SECTION (セクション属性の指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SECTION:name,[[!]{DEKPRSW}][,ALIGN=#]  
```  
  
## 解説  
 \/SECTION オプションは、セクション属性を変更します。そのセクションの .obj ファイルをコンパイルしたときに設定した属性はオーバーライドされます。  
  
 移植性が高い実行可能 \(PE\) ファイルのセクションは、新しい実行可能 \(NE\) ファイルのセグメントまたはリソースとほぼ同じです。  セクションには、コードまたはデータが含まれています。  セグメントと異なり、セクションは、サイズの制限がない連続メモリのブロックです。  一部のセクションには、プログラムが宣言したり、直接使用したりするコードまたはデータが含まれ、リンカーとライブラリ マネージャー \(lib.exe\) が作成するほかのデータ セクションには、オペレーティング システムに必須の情報が含まれます。  NE ファイルの詳細については、サポート技術情報の「Executable\-File Header Format \(Q65122\)」を参照してください。  MSDN ライブラリのサポート技術情報の文書"、または"を参照してください。[http:\/\/support.microsoft.com](http://support.microsoft.com)  
  
 引数 *name* は、コロン \(:\) の後ろに指定します。  *name* は、大文字と小文字が区別されます。  
  
 標準名との競合を避けるため、次の名前は使用しないでください。  たとえば、.sdata は RISC プラットフォームで使用されています。  
  
-   .arch  
  
-   .bss  
  
-   .data  
  
-   .edata  
  
-   .idata  
  
-   .pdata  
  
-   .rdata  
  
-   .reloc  
  
-   .rsrc  
  
-   .sbss  
  
-   .sdata  
  
-   .srdata  
  
-   .text  
  
-   .xdata  
  
 指定したセクションに対して属性を指定します。  属性は、次の表に示す文字で指定します。大文字と小文字は区別されません。  指定したセクションに必要なすべての属性を指定する必要があります。属性を指定する文字を省略すると、該当する属性ビットが無効になります。  R、W、または E を指定しない場合は、現在の読み込み、書き込み、または実行可能ファイルの状態がそのまま維持されます。  
  
 属性を無効にするには、その属性文字の前に感嘆符 \(\!\) を付けます。  表には、属性を指定する文字の意味も示してあります。  
  
|文字|Attribute|説明|  
|--------|---------------|--------|  
|E|実行|実行可能なセクションです。|  
|R|Read|データの読み取り操作を有効にします。|  
|W|Write|データの書き込み操作を有効にします。|  
|S|Shared|イメージを読み込んだすべてのプロセス間でセクションを共有します。|  
|D|Discardable|セクションを破棄可能としてマークします。|  
|K|Cacheable|セクションをキャッシュ不可としてマークします。|  
|P|Pageable|セクションをページング不可としてマークします。|  
  
 K と P では、対応するセクション フラグが否定の意味を持つという特徴があります。  [\/HEADERS](../../build/reference/headers.md) オプションを使って [DUMPBIN](../../build/reference/dumpbin-options.md) を実行するときに、いずれかの属性を .text セクションで指定した場合 \(\/SECTION:.text,K\)、セクションは既にキャッシュされているため、セクション フラグでの変化はありません。  既定値を取り除くには、\/SECTION:.text,\!K と指定します。\/SECTION:.text,\!K と指定すると、DUMPBIN は「キャッシュ不可」も含めてセクションの特徴を明らかにします。  
  
 E、R、または W のどの属性も設定されていない PE ファイルのセクションは、ほとんどの場合無効です。  
  
 ALIGN*\=\#* を使用して、特定のセクションの配置の値を指定できます。  詳細については、「[\/ALIGN \(セクションの配置\)](../../build/reference/align-section-alignment.md)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにオプションを入力します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)
---
title: "/ORDER (関数の順序) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.FunctionOrder"
  - "/order"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ORDER リンカー オプション"
  - "LINK ツール [C++], プログラムの最適化"
  - "LINK ツール [C++], スワップ調整"
  - "ORDER リンカー オプション"
  - "-ORDER リンカー オプション"
  - "ページング, 最適化"
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ORDER (関数の順序)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ORDER:@filename  
```  
  
## パラメーター  
 *filename*  
 COMDAT 関数のリンク順序を指定するテキスト ファイル。  
  
## 解説  
 \/ORDER オプションは、特定の COMDAT を指定された順序でイメージに取り込み、プログラムを最適化します。  指定された関数は、イメージの各セクションに指定された順序で配置されます。  
  
 引数 *filename* で指定するテキスト ファイル \(応答ファイル\) には、COMDAT をリンクする順に記述します。  *filename* ファイルには、1 行ごとに COMDAT の名前を 1 つ記述します。  COMDAT は、\/Gy オプションでコンパイルしたオブジェクト ファイルに入っています。  関数名は、大文字と小文字が区別されます。  
  
 LINK は、装飾された形式の識別子を使用します。  .obj ファイルの作成時に、コンパイラが識別子を装飾します。  リンカーに対して装飾形式で識別子を指定する必要がある場合は、[DUMPBIN](../../build/reference/dumpbin-reference.md) ツールでその装飾形式を確認できます。  装飾名の詳細については、「[装飾名](../Topic/Decorated%20Names.md)」を参照してください。  
  
 \/ORDER オプションを複数指定すると、最後の指定が有効になります。  
  
 関数の順序を指定すると、プログラムのページング動作を最適化できます。呼び出し元の関数と呼び出し先の関数を同じグループにまとめることにより、スワップを調整できるからです。  また、頻繁に呼び出される関数を同じグループにまとめることもできます。  このような手法を使うと、関数を呼び出したときにその関数がメモリ内にあるため、ディスクからページングする必要がなくなる場合が増えます。  
  
 名前が疑問符 \(?\) またはアット マーク \(@\) で始まる場合を除いて、*filename* 内のすべての修飾名の先頭にアンダースコア \(\_\) が付加されます。  たとえば、オブジェクト ファイル内に `extern "C" int func(int)` および `int main(void)` が含まれる場合、DUMPBIN [\/SYMBOLS](../../build/reference/symbols.md) では次のように修飾された名前が表示されます。  
  
```  
009 00000000 SECT3  notype ()    External     | _func  
00A 00000008 SECT3  notype ()    External     | _main  
```  
  
 ただし、オーダー ファイルに指定する関数名は、`func` および `main` です。  
  
 この \/ORDER オプションを使うと、インクリメンタル リンクが行われなくなります。  
  
> [!NOTE]
>  LINK では、静的関数の順序を指定できません。静的関数の名前はパブリック シンボル名ではないためです。  \/ORDER が指定された場合、オーダー ファイル中の、静的あるいは見つからないシンボルごとにリンカー警告 LNK4037 が生成されます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[最適化\] プロパティ ページをクリックします。  
  
4.  \[関数の順序\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)
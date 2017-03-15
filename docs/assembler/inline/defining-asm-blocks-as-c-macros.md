---
title: "__asm ブロックの C マクロとしての定義 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm キーワード [C++], C のマクロとして"
  - "マクロ, __asm ブロック"
  - "Visual C, マクロ"
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# __asm ブロックの C マクロとしての定義
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 C のマクロはソース・コードとアセンブリ コードを挿入できる便利な方法を提供しますがマクロが一つの論理行に配置するため特別な注意が必要です。  " " では無料のマクロを作成するには次の規則に従います。:  
  
-   中かっこで `__asm` ブロックに記述します。  
  
-   各アセンブリ命令の前の `__asm` のキーワードを配置します。  
  
-   アセンブリのスタイル `; comment` コメント \(\) または単一行の C のコメント `// comment`\(\) ではなく 15 旧形式の C のコメント `/* comment */`\(\) を使用します。  
  
 示すために次の例では単純なマクロを定義したものです :  
  
```  
#define PORTIO __asm      \  
/* Port output */         \  
{                         \  
   __asm mov al, 2        \  
   __asm mov dx, 0xD007   \  
   __asm out dx, al       \  
}  
```  
  
 一見すると`__asm` の最後の 3 回のキーワードは過度な方法です。  がマクロが単一行に配置するためです :  
  
```  
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }  
```  
  
 `__asm` の 3 番目と 4 番目のキーワードはステートメントの区切り記号として指定する必要があります。  `__asm` ブロックで認識される唯一のステートメントの区切り記号は`__asm` の改行文字やキーワードです。  マクロで定義されたブロックが 1 台の論理行であるため`__asm` の各命令を区切る必要があります。  
  
 中かっこが必要です。  これらを省略するとコンパイラはマクロ呼び出しの右側にある行 15 ので C または C\+\+ のステートメントとは異なるできます。  右中かっこがあるとコンパイラはアセンブリとアセンブリ命令終了コードとして C または C\+\+ のステートメントの後 `__asm` ブロック内に表示したかを通知することはできません。  
  
 アセンブリ スタイルは開始行の末尾にセミコロン \(\)**;** 次のコードはコメント アウトします。  これはマクロ内のコンパイラが論理行の末尾まですべて後コメントを無視するため問題が発生します。  これは単一行 15 ので C または C\+\+ のコメント \(`// comment`\) にも当てはまります。  エラーを回避するにはマクロで定義された `__asm` ブロックで 15 旧形式の C のコメント `/* comment */`\(\) を使用します。  
  
 C. マクロとして記述 `__asm` ブロックに引数を受け取ることができます。  ただし通常の C のマクロとは異なり `__asm` マクロは値を返すことができません。  つまりC または C\+\+ の式にこれらのマクロを使用できません。  
  
 この種類のマクロを差別に起動しないように注意してください。  たとえば`__fastcall` の規約で宣言された関数のアセンブリ言語マクロを呼び出すと予期しない結果になることがあります。  \([登録をインライン アセンブリで使用および管理する](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md) を参照してください\)。  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)
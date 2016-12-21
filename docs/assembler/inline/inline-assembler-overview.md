---
title: "インライン アセンブラーの概要 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm キーワード [C++], インライン アセンブラーの呼び出し"
  - "インライン アセンブラー"
  - "インライン アセンブラー, インライン アセンブラー"
  - "インライン アセンブラーの呼び出し"
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# インライン アセンブラーの概要
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 インライン アセンブラーは追加のアセンブリとリンク ステップのない C および C\+\+ プログラムの作成元のアセンブリ言語命令を埋め込むことができます。  インライン アセンブラーはコンパイラにビルド — MASM \(Microsoft Macro Assembler\) などの別のアセンブラーは必要ではありません。  
  
 インライン アセンブラーが別のアセンブリとリンク ステップを必要としないため別のアセンブラー方が便利です。  スコープ内にあるためプログラムの C および C\+\+ コードと統合する方が簡単なインライン アセンブラー コードで C または C\+\+ の変数または関数名を使用できます。  アセンブリ コードおよび C および C\+\+ のステートメントを混在させることができるため単独で C または C\+\+ で使いにくくまたは不可能なタスクを実行できます。  
  
 [\_\_asm](../../assembler/inline/asm.md) のキーワードはインライン アセンブラーを起動してC. または C\+\+ のステートメントを実行できる場所ならどこでも指定できます。  これは単独では使用できません。  これは命令のアセンブリ命令中かっこで囲まれた少なくともグループ空のかっこのペアを指定する必要があります。  用語 `__asm` 「ブロック」ここについての命令またはグループを中かっこでかどうかを示します。  
  
 次のコードは中かっこ \(\) で囲んだ `__asm` の単純なブロックです。  \(コードはカスタム関数プロローグのシーケンスです\)。  
  
```  
// asm_overview.cpp  
// processor: x86  
void __declspec(naked) main()  
{  
    // Naked functions must provide their own prolog...  
    __asm {  
        push ebp  
        mov ebp, esp  
        sub esp, __LOCAL_SIZE  
    }  
  
    // ... and epilog  
    __asm {  
        pop ebp  
        ret  
    }  
}  
```  
  
 また各アセンブリ命令の前の `__asm` を配置できます :  
  
```  
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE  
```  
  
 `__asm` のキーワードがステートメントの区分線であるため同じ行または命令にアセンブリを配置する :  
  
```  
__asm push ebp  
__asm mov  ebp, esp  
__asm sub  esp, __LOCAL_SIZE  
```  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)
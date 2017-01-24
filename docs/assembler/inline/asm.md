---
title: "__asm | Microsoft Docs"
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
  - "__asm"
  - "__asm_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm キーワード [C++]"
  - "__asm キーワード [C++], asm ブロックとの比較"
ms.assetid: 77ff3bc9-a492-4b5e-85e1-fa4e414e79cd
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __asm
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `__asm` キーワードは、インライン アセンブラーを呼び出し、C ステートメントまたは C\+\+ ステートメントが有効である任意の場所に使用できます。  これは、単独では使用できません。  アセンブリ命令、中かっこで囲まれた命令グループ、または少なくとも空の中かっこの後で指定する必要があります。  "`__asm` ブロック" という用語は、ここでは、中かっこに囲まれているかどうかを問わず、命令または命令のグループを示します。  
  
> [!NOTE]
>  Visual C\+\+ による標準 C\+\+ の `asm` キーワードのサポートには、コンパイラがキーワードに関するエラーを生成しないという制限があります。  ただし、`asm` ブロックは意味のあるコードを生成しません。  `asm` の代わりに `__asm` を使用します。  
  
 構文:  
  
 \_\_asm *assembly\-instruction* \[ ; \]  
  
 \_\_asm { *assembly\-instruction\-list* } \[ ; \]  
  
## 文法  
 `__asm`  `assembly-instruction`  `;` opt  
  
 `__asm {`  `assembly-instruction-list`  `};` opt  
  
 *assembly\-instruction\-list*:  
 `assembly-instruction` `;` opt  
  
 `assembly-instruction` `;` `assembly-instruction-list` `;` opt  
  
 中かっこを付けないで使用する場合、`__asm` キーワードは、行の残りの部分がアセンブリ言語のステートメントであることを意味します。  中かっこを付けて使用する場合、中かっこの間の各行がアセンブリ言語のステートメントであることを意味します。  以前のバージョンとの互換性を維持するため、`_asm` は `__asm` のシノニムとなっています。  
  
 `__asm` キーワードはステートメント区切り文字であるため、アセンブリ命令も同じ行に記述できます。  
  
 Visual C\+\+ 2005 以前で、次の命令が実行されたとします。  
  
```  
__asm int 3  
```  
  
 この命令では、**\/clr** を指定してコンパイルしても、ネイティブ コードが生成されることはありませんでした。コンパイラはその命令を CLR break 命令と解釈しました。  
  
 `__asm int 3` により現在は、関数のネイティブ コードが生成されるようになりました。  コード内で関数にブレーク ポイントを設定する場合や、その関数を MSIL にコンパイルする場合は、[\_\_debugbreak](../../intrinsics/debugbreak.md) を使用します。  
  
## 使用例  
 次のコード片は、中かっこで囲まれた単純な `__asm` ブロックです。  
  
```  
__asm {  
   mov al, 2  
   mov dx, 0xD007  
   out dx, al  
}  
```  
  
 または、各アセンブリ命令の前に `__asm` を置くことができます。  
  
```  
__asm mov al, 2  
__asm mov dx, 0xD007  
__asm out dx, al  
```  
  
 `__asm` キーワードはステートメント区切り文字であるため、アセンブリ命令も同じ行に記述できます。  
  
```  
__asm mov al, 2   __asm mov dx, 0xD007   __asm out dx, al  
```  
  
 これらの 3 つの例ではいずれも同じコードが生成されますが、最初のスタイル \(中かっこで `__asm` ブロックを囲む\) にはいくつかの利点があります。  中かっこにより、C または C\+\+ コードからアセンブリ コードが明確に分離され、`__asm` キーワードの不要な繰り返しが避けられます。  中かっこにより、あいまいさを防ぐこともできます。  C または C\+\+ ステートメントを `__asm` ブロックと同じ行に記述する場合は、そのブロックを中かっこで囲む必要があります。  中かっこで囲まないと、コンパイラはどこでアセンブリ コードが終わって C または C\+\+ ステートメントが始まるかがわかりません。  最後に、中かっこ内のテキストは、通常の MASM テキストと同じ形式であるため、既存の MASM ソース ファイルからテキストを簡単に切り取って貼り付けることができます。  
  
 C および C\+\+ での中かっこと異なり、`__asm` ブロックを囲む中かっこは、変数のスコープに影響を与えません。  また、`__asm` ブロックを入れ子にすることもできます。入れ子にしても、変数のスコープは影響を受けません。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [C\+\+ キーワード](../../cpp/keywords-cpp.md)   
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)
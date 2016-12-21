---
title: ".MODEL | Microsoft Docs"
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
  - ".MODEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".MODEL directive"
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .MODEL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラムのメモリ モデルを初期化します。  
  
## 構文  
  
```  
.MODEL memorymodel [[, langtype]] [[, stackoption]]  
```  
  
#### パラメーター  
 `memorymodel`  
 コードとデータのポインターのサイズを指定する必須のパラメーターです。  
  
 `langtype`  
 プロシージャおよびパブリック シンボルの呼び出しと名前付け規則を設定するオプションのパラメーター。  
  
 `stackoption`  
 省略可能なパラメーターです。  
  
 `stackoption`is not used if `memorymodel` is `FLAT`.  
  
 指定`NEARSTACK` 、スタック セグメントは、1 つの物理セグメントにグループ化 \(`DGROUP`\) データと共に。  スタック セグメント レジスタ \(`SS`） と同じアドレスにデータ セグメント レジスタを保持する前提としています \(`DS`\)。  `FARSTACK`スタックではグループ化されません`DGROUP`。 したがって`SS`等しくない`DS`。  
  
## 解説  
 .`MODEL`使用されない[MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md)。  
  
 次の表は、16 ビットおよび 32 ビット プラットフォームを対象とすると各パラメーターの値を示します。  
  
|パラメーター|32 ビットの値|16 ビットの値 \(以前の 16 ビット開発のサポート\)|  
|------------|--------------|------------------------------------|  
|`memorymodel`|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|  
|`langtype`|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|  
|`stackoption`|未使用|`NEARSTACK`, `FARSTACK`|  
  
## コード  
 コンパイラのサンプルから MASM に関連するサンプルについてをダウンロード[Visual Studio 2010年用 Visual の C\+\+ サンプルおよび関連](http://go.microsoft.com/fwlink/?LinkID=178749)。  
  
 次の例の使用、 `.MODEL`ディレクティブ。  
  
## 使用例  
  
```  
; file simple.asm  
; For x86 (32-bit), assemble with debug information:   
;   ml -c -Zi simple.asm  
; For x64 (64-bit), assemble with debug information:   
;   ml64 -c -DX64 -Zi simple.asm  
;  
; In this sample, the 'X64' define excludes source not used   
;  when targeting the x64 architecture  
  
ifndef X64  
.686p  
.XMM  
.model flat, C  
endif  
  
.data  
; user data  
  
.code  
; user code  
  
fxn PROC public  
  xor eax, eax ; zero function return value  
  ret  
fxn ENDP  
  
end  
```  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)   
 [Visual C のサンプルおよび関連ドキュメントの Visual Studio の 2010年](http://go.microsoft.com/fwlink/?LinkID=178749)
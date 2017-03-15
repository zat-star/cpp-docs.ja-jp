---
title: "MASM for x64 (ml64.exe) | Microsoft Docs"
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
  - "ml64.exe"
  - "ml"
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MASM for x64 (ml64.exe)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ml64.exe は [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] のアセンブリ言語を受け入れるアセンブラーです。  ml64.exe コンパイラ オプションの詳細については[ML and ML64 Command\-Line Reference](../../assembler/masm/ml-and-ml64-command-line-reference.md) を参照してください。  
  
 インライン中心は [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] ではサポートされません。  MASM またはコンパイラ組み込み関数 [x64 Intrinsics](http://msdn.microsoft.com/ja-jp/5d1f5d3e-156e-4ebf-932e-fd09be7ced62)\(\) を使用します。  
  
 2 個の代替手段があります \(x64 を完全にサポートします\) のアセンブリ MASM コンパイラ組み込み関数です。  ここでは顧客にとって関数の命令を利用するための組み込みを追加します \(たとえば。  特権のビットかみ合う走査テストなど\) または… クロス プラットフォームにできるだけ近い使用方法。  
  
## ml64 固有のディレクティブ  
 ml64.exe の次のディレクティブの使用 :  
  
-   [.ALLOCSTACK](../Topic/.ALLOCSTACK.md)  
  
-   [.ENDPROLOG](../Topic/.ENDPROLOG.md)  
  
-   [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)  
  
-   [.PUSHREG](../Topic/.PUSHREG.md)  
  
-   [.SAVEREG](../../assembler/masm/dot-savereg.md)  
  
-   [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)  
  
-   [.SETFRAME](../../assembler/masm/dot-setframe.md)  
  
 また[PROC](../../assembler/masm/proc.md) のディレクティブは ml64.exe で使用するために更新されました。  
  
## 32 ビット アドレス モード \(アドレスのサイズの優先\)  
 MASM はメモリ オペランドは 32 ビットのレジスタが含まれる場合 0x67 アドレスのサイズのオーバーライドを生成します。  たとえば次の例はアドレスのサイズのオーバーライドを生成します :  
  
```  
mov rax, QWORD PTR [ecx]  
mov eax, DWORD PTR [ecx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10d+0100h]  
prefetch [eax]  
movnti rax, QWORD PTR [r8d]  
```  
  
 MASM は 32 ビット位置がメモリ オペランドとして単独では64 ビット アドレスに意図していることを前提としています。  現在このようなオペランドと 32 ビットのアドレスのサポートはありません。  
  
 最後にメモリ オペランド内の複合登録のサイズは次のコードに示すようにエラーが発生します。  
  
```  
mov eax, DWORD PTR [rcx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10+0100h]  
```  
  
## 参照  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)
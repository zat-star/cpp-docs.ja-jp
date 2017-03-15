---
title: "__debugbreak | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__debugbreak_cpp"
  - "__debugbreak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__debugbreak 組み込み"
  - "ブレークポイント, __debugbreak 組み込み"
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# __debugbreak
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 コードのブレークポイントを発生させます。ここで、デバッガーを実行するように求めるメッセージがユーザーに表示されます。  
  
## 構文  
  
```  
void __debugbreak();  
```  
  
## 必要条件  
  
|組み込み|アーキテクチャ|Header|  
|----------|-------------|------------|  
|`__debugbreak`|x86、ARM、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<intrin.h\>|  
  
## 解説  
 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297.aspx) に似た `__debugbreak` コンパイラ組み込みは、移植性の高い Win32 手法でブレークポイントを発生させます。  
  
> [!NOTE]
>  **\/clr** でコンパイルする場合は、`__debugbreak` を含む関数が MSIL にコンパイルされます。  `asm int 3` により、関数がネイティブにコンパイルされます。  詳細については、「[\_\_asm](../assembler/inline/asm.md)」を参照してください。  
  
 次に例を示します。  
  
```  
main() {  
   __debugbreak();  
}  
```  
  
 上記のコードは、以下と似ています。  
  
```  
main() {  
   __asm {  
      int 3  
   }  
}  
```  
  
 このコードは x86 コンピューターにあります。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)
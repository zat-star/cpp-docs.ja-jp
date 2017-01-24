---
title: "リンカ ツール エラー LNK1237 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1237"
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コード生成中に、コンパイラは、\/GL と共にコンパイルされたモジュール 'モジュール' で定義された 'シンボル' への参照を導入しました  
  
 コードの生成中、コンパイラは、**\/GL** でコンパイルされる定義に後で解決されるシンボルを導入するべきではありません。  `symbol` は既に導入されており、後で **\/GL** を指定してコンパイルされ、定義に解決されるシンボルです。  
  
 詳細については、「[\/GL \(プログラム全体の最適化\)](../../build/reference/gl-whole-program-optimization.md)」を参照してください。  
  
 LNK1237 を解決するには、シンボルのコンパイルで **\/GL** を指定しないか、[\/INCLUDE \(シンボルの明示的な参照\)](../../build/reference/include-force-symbol-references.md) を使用してシンボルへの参照を強制します。  
  
## 使用例  
 次の例では LNK1237 エラーが生成されます。  このエラーを解決するには、LNK1237\_a.cpp 内の配列を初期化したり、リンク コマンドに **\/include:\_\_chkstk** を追加したりしないでください。  
  
```  
// LNK1237_a.cpp  
int main() {  
   char c[5000] = {0};  
}  
```  
  
```  
// LNK1237_b.cpp  
// compile with: /GS- /GL /c LNK1237_a.cpp  
// processor: x86  
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)  
extern "C" void _chkstk(size_t s) {}  
```
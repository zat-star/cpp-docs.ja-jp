---
title: "リンカ ツール エラー LNK2028 | Microsoft Docs"
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
  - "LNK2028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2028"
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK2028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"exported\_function" \(decorated\_name\) が関数 "function\_containing\_function\_call" \(decorated\_name\) で参照されました。  
  
 ネイティブ関数を純粋なイメージにインポートしようとするときは、ネイティブ コンパイルと純粋なコンパイルで暗黙の呼び出し規約が異なることに注意してください。  
  
## 使用例  
 次のコード例は、呼び出し規約が暗黙的に [\_\_cdecl](../Topic/__cdecl.md) である、エクスポートされたネイティブ関数を持つコンポーネントを生成します。  
  
```  
// LNK2028.cpp  
// compile with: /LD  
__declspec(dllexport) int func() {  
   return 3;  
}  
```  
  
## 使用例  
 次の例は、ネイティブ関数を使用する純粋なクライアントを作成します。  ただし、**\/clr:pure** の呼び出し規約は [\_\_clrcall](../../cpp/clrcall.md) です。  次の例では LNK2028 エラーが生成されます。  
  
```  
// LNK2028_b.cpp  
// compile with: /clr:pure lnk2028.lib  
// LNK2028 expected  
int func();  
  
int main() {  
   return func();  
}  
```
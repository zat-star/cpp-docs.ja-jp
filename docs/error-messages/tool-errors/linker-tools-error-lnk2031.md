---
title: "リンカ ツール エラー LNK2031 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2031"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2031"
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# リンカ ツール エラー LNK2031
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"function\_declaration" の p\/invoke を生成できませんでした。呼び出し規約がメタデータに見つかりません。  
  
 ネイティブ関数を純粋なイメージにインポートしようとするときは、ネイティブ コンパイルと純粋なコンパイルで暗黙の呼び出し規約が異なることに注意してください。  純粋なイメージの詳細については、「[純粋なコードと検証可能なコード](../../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。  
  
## 使用例  
 次のコード例は、呼び出し規約が暗黙的に [\_\_cdecl](../Topic/__cdecl.md) である、エクスポートされたネイティブ関数を持つコンポーネントを生成します。  
  
```  
// LNK2031.cpp  
// compile with: /LD  
extern "C" {  
   __declspec(dllexport) int func() { return 3; }  
};  
```  
  
## 使用例  
 次の例は、ネイティブ関数を使用する純粋なクライアントを作成します。  ただし、**\/clr:pure** の呼び出し規約は [\_\_clrcall](../../cpp/clrcall.md) です。  次の例では LNK2031 エラーが生成されます。  
  
```  
// LNK2031_b.cpp  
// compile with: /clr:pure LNK2031.lib  
// LNK2031 expected  
extern "C" int func();  
  
int main() {  
   return func();  
}  
```  
  
## 使用例  
 次の例は、純粋なイメージからネイティブ関数を使用する方法を示します。  明示的な **\_\_cdecl** 呼び出し規約の指定子が使用されています。  
  
```  
// LNK2031_c.cpp  
// compile with: /clr:pure LNK2031.lib  
extern "C" int __cdecl func();  
  
int main() {  
   return func();  
}  
```
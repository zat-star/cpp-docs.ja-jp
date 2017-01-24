---
title: "noreturn | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noreturn_cpp"
  - "noreturn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], noreturn"
  - "noreturn __declspec キーワード"
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# noreturn
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 この `__declspec` 属性は、コンパイラに、関数が戻らないことを示します。  結果として、コンパイラは **\_\_declspec\(noreturn\)** 関数への呼び出しに続くコードは制御が渡らないことを認識します。  
  
 コンパイラで値を返さないコントロール パスの関数が検出されると、警告 \(C4715\) またはエラー メッセージ \(C2202\) が生成されます。  関数が値を返さないためコントロール パスに到達できない場合は、**\_\_declspec\(noreturn\)** を使用してこの警告やエラーを回避できます。  
  
> [!NOTE]
>  返されると予想される関数へ **\_\_declspec\(noreturn\)** を追加すると、未定義の動作になることがあります。  
  
## 使用例  
 次の例では、**else** 句に return ステートメントは含まれていません。  `fatal` を **\_\_declspec\(noreturn\)** として宣言すると、エラーまたは警告メッセージを回避できます。  
  
```  
// noreturn2.cpp  
__declspec(noreturn) extern void fatal () {}  
  
int main() {  
   if(1)  
     return 1;  
   else if(0)  
     return 0;  
   else  
     fatal();  
}  
```  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)
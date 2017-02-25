---
title: "リンカー ツールの警告 LNK4224 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4224"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4224"
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# リンカー ツールの警告 LNK4224
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

option はサポートされていません。無視されます。  
  
 現在では使用されていない無効なリンカー オプションが指定されています。このオプションは無視されます。  
  
 たとえば、LNK4224 は .obj に \/comment ディレクティブがある場合に発生することがあります。  \/comment ディレクティブは、使用されなくなった exestr オプションを使用して [コメント](../../preprocessor/comment-c-cpp.md) プラグマを介して追加された可能性があります。  .obj ファイルでリンカー ディレクティブを表示するには、dumpbin [\/ALL](../../build/reference/all.md) を使用します。  
  
 可能な場合は、.obj のソースを変更してこのプラグマを削除します。  この警告を無視すると、**\/clr:pure** を指定してコンパイルした .executable が予想外の動作をする可能性があります。  
  
## 使用例  
 次の例では LNK4224 エラーが生成されます。  
  
```  
// LNK4224.cpp  
// compile with: /c /Zi  
// post-build command: link LNK4224.obj /debug /debugtype:map  
int main () {  
   return 0;  
}  
```
---
title: "コンパイラ エラー C3170 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3170"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3170"
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3170
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロジェクト内で異なるモジュールの識別子を指定することはできません。  
  
 コンパイル中に、2 つのファイルで名前の異なる [module](../../windows/module-cpp.md) 属性が見つかりました。  一意の `module` 属性は、コンパイルごとに 1 つだけ指定できます。  
  
 複数のソース コード ファイルでは同じ `module` 属性を指定できます。  
  
 たとえば、次の **module** 属性が見つかったとします。  
  
```  
// C3170.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
int main() {}  
```  
  
 次に、以下のコードを実行します。  
  
```  
// C3170b.cpp  
// compile with: C3170.cpp  
// C3170 expected  
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
```  
  
 この場合は C3170 エラーになります。名前が異なることに注意してください。
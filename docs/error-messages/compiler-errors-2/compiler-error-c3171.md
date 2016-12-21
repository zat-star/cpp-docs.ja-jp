---
title: "コンパイラ エラー C3171 | Microsoft Docs"
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
  - "C3171"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3171"
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3171
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'module' : プロジェクト内で異なるモジュールの属性を指定することはできません。  
  
 コンパイル中に、2 つのファイルでパラメーター リストが異なる [module](../../windows/module-cpp.md) 属性が見つかりました。  一意の `module` 属性は、コンパイルごとに 1 つだけ指定できます。  
  
 複数のソース コード ファイルでは同じ `module` 属性を指定できます。  
  
 たとえば、次の `module` 属性が見つかったとします。  
  
```  
// C3171.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];  
int main() {}  
```  
  
 次に、以下のコードを実行します。  
  
```  
// C3171b.cpp  
// compile with: C3171.cpp  
// C3171 expected  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];  
```  
  
 この場合は C3171 エラーになります。バージョンの値が異なることに注意してください。
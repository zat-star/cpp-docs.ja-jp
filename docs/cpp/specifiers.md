---
title: "指定子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "宣言指定子"
  - "宣言, 指定子"
  - "指定子, 宣言内"
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 指定子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、[宣言](../misc/declarations.md)の *decl\-specifiers* \(宣言指定子\) コンポーネントについて説明します。  
  
 次のプレースホルダーと言語キーワードは宣言指定子です。  
  
 *storage\-class\-specifier*  
  
 *type\-specifier*  
  
 *function\-specifier*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [Typedef](http://msdn.microsoft.com/ja-jp/cc96cf26-ba93-4179-951e-695d1f5fdcf1)  
  
 [\_\_declspec](../cpp/declspec.md) `(` *extended\-decl\-modifier\-seq* `)`  
  
## 解説  
 宣言の *decl\-specifiers* 部分は、型名を示すために使用できる最も長い *decl\-specifiers* のシーケンスであり、ポインターや参照修飾子を含みません。  宣言の残りは、導入された名前を含む *declarator* \(宣言子\) です。  
  
 次の表は、4 つの宣言を一覧表示し、次に各宣言の *decl\-specifers* コンポーネントと *declarator* コンポーネントを別々に一覧表示します。  
  
|宣言|*decl\-specifiers*|`declarator`|  
|--------|------------------------|------------------|  
|`char *lpszAppName;`|`char`|`*lpszAppName`|  
|`typedef char * LPSTR;`|`char`|`*LPSTR`|  
|`const int func1();`|`const int`|`func1`|  
|`volatile void *pvvObj;`|`volatile void`|`*pvvObj`|  
  
 `signed`、`unsigned`、`long` および `short` はすべて `int` を意味するため、これらのキーワードの 1 つに続く `typedef` 名は *decl\-specifiers* ではなく、*declarator\-list* のメンバーであると見なされます。  
  
> [!NOTE]
>  名前は再宣言できるため、その解釈は、現在のスコープ内の最新の宣言に従います。  再宣言は、名前 \(特に `typedef` 名\) がコンパイラによってどのように解釈されるかに影響を与える可能性があります。  
  
## 参照  
 [宣言](../misc/declarations.md)
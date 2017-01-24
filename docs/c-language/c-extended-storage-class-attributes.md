---
title: "C 拡張ストレージ クラス属性 | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "__declspec キーワード [C]"
  - "拡張属性"
  - "拡張ストレージ クラス属性"
  - "ストレージ クラス指定子, C のストレージ クラス"
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 拡張ストレージ クラス属性
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 このトピックの最新情報は、「[\_\_declspec \(C\+\+ リファレンス\)](../cpp/declspec.md)」を参照してください。  
  
 拡張属性構文は、Microsoft 固有の C 言語拡張機能を簡略化し、標準化します。  拡張属性構文を使用するストレージ クラス属性には、thread、naked、dllimport、dllexport があります。  
  
 ストレージ クラス情報を指定するための拡張属性構文は、\_\_declspec キーワードを使用します。これは、指定された型のインスタンスを、Microsoft 固有のストレージ クラス属性 \(thread、naked、dllimport、または dllexport\) で保存することを指定します。  他のストレージ クラス修飾子の例としては、static および extern キーワードがあります。  ただし、これらのキーワードは ANSI C 規格の一部であるため、拡張属性構文では扱われません。  
  
## 構文  
 *storage\-class\-specifier*:  
 `__declspec` \( *extended\-decl\-modifier\-seq* \) \/\* Microsoft 固有 \*\/  
  
 *extended\-decl\-modifier\-seq*:  
 *extended\-decl\-modifier*  opt  
  
 *extended\-decl\-modifier\-seq extended\-decl\-modifier*  
  
 *extended\-decl\-modifier*:  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
 空白は、宣言修飾子を区切ります。  *extended\-decl\-modifier\-seq* は空にできます。この場合、\_\_declspec は無効になります。  
  
 thread、naked、dllimport、および dllexport ストレージ クラス属性は、適用先のデータまたは関数を宣言するだけのプロパティです。関数自体の型属性は再定義しません。  thread 属性はデータだけに影響します。  naked 属性は関数だけに影響します。  dllimport 属性と dllexport 属性は関数とデータに影響します。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [型の宣言](../c-language/declarations-and-types.md)
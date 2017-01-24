---
title: "継承 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス [C++], 派生"
  - "派生クラス"
  - "派生クラス, 派生クラスの概要"
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 継承 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このセクションでは、派生クラスを使用して拡張可能プログラムを生成する方法について説明します。  
  
## 概要  
 "継承" というメカニズムを使用して、既存のクラスから新しいクラスを派生させることができます \(「[Single Inheritance \(単一継承\)](../cpp/single-inheritance.md)」から始まる情報を参照\)。  派生に使用されるクラスは、特定の派生クラスの "基底クラス" と呼ばれます。  派生クラスは、次の構文を使用して宣言します。  
  
```  
 class Derived : [virtual] [access-specifier] Base  
{  
   // member list  
};  
 class Derived : [virtual] [access-specifier] Base1,  
 [virtual] [access-specifier] Base2, . . .  
{  
   // member list  
};  
```  
  
 クラスのタグ \(名前\) の後ろにコロンを指定し、その後ろに基本指定のリストが続きます。  したがって、基底クラスは、あらかじめ宣言しておく必要があります。  基本指定には、アクセス指定子を含めることができます。これは、**public**、`protected`、または `private` のいずれかになります。  これらのアクセス指定子は、基底クラス名の前に指定され、その基底クラスにのみ適用されます。  これらの指定子は、派生クラスで基底クラスのメンバーに対して使用されるアクセス許可を制御します。  基底クラス メンバーへのアクセスについては、「[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)」を参照してください。  アクセス指定子を省略すると、その基底クラスへのアクセスは `private` と見なされます。  基本指定に、仮想継承を示す **virtual** キーワードが含まれる場合があります。  このキーワードがある場合は、アクセス指定子の前または後に指定されます。  仮想継承を使用する場合、基底クラスは、仮想基底クラスと呼ばれます。  詳細については、「[仮想基底クラス](../Topic/Virtual%20Base%20Classes.md)」を参照してください。  
  
 複数の基底クラスをコンマで区切って指定できます。  単一の基底クラスを指定した場合、継承モデルは[単一継承](../cpp/single-inheritance.md)になります。複数の基底クラスを指定した場合の継承モデルは、[多重継承](http://msdn.microsoft.com/ja-jp/3b74185e-2beb-4e29-8684-441e51d2a2ca)と呼ばれます。  
  
 ここでは、次のトピックについて説明します。  
  
-   [単一継承](../cpp/single-inheritance.md)  
  
-   [多重継承](http://msdn.microsoft.com/ja-jp/3b74185e-2beb-4e29-8684-441e51d2a2ca)  
  
-   [多重基底クラス](../cpp/multiple-base-classes.md)  
  
-   [仮想基底クラス](../Topic/Virtual%20Base%20Classes.md)  
  
-   [仮想関数](../cpp/virtual-functions.md)  
  
-   [明示的なオーバーライド](../cpp/explicit-overrides-cpp.md)  
  
-   [抽象クラス](../cpp/abstract-classes-cpp.md)  
  
-   [スコープ規則の概要](../cpp/summary-of-scope-rules.md)  
  
 [\_\_super](../cpp/super.md) および [\_\_interface](../Topic/__interface.md) キーワードについては、このセクションで説明します。  
  
## 参照  
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)
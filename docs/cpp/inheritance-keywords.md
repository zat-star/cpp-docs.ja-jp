---
title: "継承キーワード | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__multiple_inheritance"
  - "__single_inheritance_cpp"
  - "__virtual_inheritance_cpp"
  - "__virtual_inheritance"
  - "__multiple_inheritance_cpp"
  - "__single_inheritance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__multiple_inheritance キーワード [C++]"
  - "__single_inheritance キーワード [C++]"
  - "__virtual_inheritance キーワード [C++]"
  - "派生クラスの宣言"
  - "派生クラス, 宣言"
  - "継承, 派生クラスの宣言"
  - "継承, キーワード"
  - "キーワード [C++], inheritance キーワード"
ms.assetid: bb810f56-7720-4fea-b8b6-9499edd141df
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 継承キーワード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
```  
  
class [__single_inheritance] class-name; class [__multiple_inheritance] class-name; class [__virtual_inheritance] class-name;  
```  
  
 それぞれの文字について以下に説明します。  
  
 *class\-name*  
 宣言するクラスの名前。  
  
 C\+\+ では、クラスを定義する前にクラス メンバーへのポインターを宣言できます。  次に例を示します。  
  
```  
class S;  
int S::*p;  
```  
  
 上記のコードでは、`p` は、クラス S の整数メンバーへのポインターとして宣言しています。  ただし、`class S` は、このコードでまだ定義されていません。宣言されているだけです。  コンパイラがこのようなポインターを検出した場合、そのポインターの汎化表現を作成する必要があります。  この表現のサイズは、指定した継承モデルによって異なります。  コンパイラに継承モデルを指定するには 4 つの方法があります。  
  
-   IDE の **\[pointer\-to\-member 表現\]** で指定する  
  
-   コマンド ラインで、[\/vmg](../build/reference/vmb-vmg-representation-method.md) スイッチを使って指定する  
  
-   [pointers\_to\_members](../Topic/pointers_to_members.md) プラグマを使って指定する  
  
-   継承キーワード `__single_inheritance`、`__multiple_inheritance`、および `__virtual_inheritance` を使って指定する  この手法により、クラス単位で継承モデルを制御します。  
  
    > [!NOTE]
    >  常にクラスを定義した後で、そのクラスのメンバーへのポインターを宣言する場合は、これらのオプションを使用する必要がありません。  
  
 クラスを定義する前に、そのクラスのメンバーへのポインターを宣言すると、作成される実行可能ファイルのサイズと速度に影響を与えます。  クラスで使用する継承が複雑になるほど、そのクラスのメンバーへのポインターを表すために必要なバイト数が多くなります。したがって、そのポインターの解釈に必要なコードも大きくなります。  単一継承は最も簡素で、仮想継承は最も複雑です。  
  
 上記の例を次のように変更します。  
  
```  
class __single_inheritance S;  
int S::*p;  
```  
  
 この場合、コマンド ライン オプションやプラグマに関係なく、`class S` のメンバーへのポインターは最小サイズの表現を使用します。  
  
> [!NOTE]
>  メンバーへのクラス ポインター表現の同じ前方宣言は、そのクラスのメンバーへのポインターを宣言する各翻訳単位で発生する必要があり、その宣言はメンバーへのポインターを宣言する前に発生する必要があります。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)
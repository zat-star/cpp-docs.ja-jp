---
title: "コンパイラの警告 (レベル 1) C4691 | Microsoft Docs"
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
  - "C4691"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4691"
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4691
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : 参照された型は参照されていないアセンブリ 'ファイル' で必要です。現在の翻訳単位で定義された型が使用されます  
  
 元の型定義を含むメタデータ ファイルが参照されていません。コンパイラはローカルの型定義を使用しています。  
  
 *file*を再ビルドしている場合は、[warning](../../preprocessor/warning.md)プラグマは C4691 を無視するまたは無効にできます。つまり、ビルドしているファイルが、コンパイラが型定義を検索するファイルと同じ場合は、C4691 を無視できます。  
  
 ただし、メタデータで参照されるアセンブリとは別のアセンブリの定義をコンパイラで使用する場合は、予期しない動作が発生する可能性があります。CLR 型は型名によってだけでなく、アセンブリによっても型指定されるためです。つまり、アセンブリ z.dll の型 Z とアセンブリ y.dll の型 Z は異なります。  
  
## 使用例  
 次の例では、元の型定義を使用します。  
  
```  
// C4691_a.cpp  
// compile with: /clr /LD /W1  
public ref class Original_Type {};  
```  
  
## 使用例  
 次の例では C4691\_a.dll を参照し、型 Original\_Type のフィールドを宣言します。  
  
```  
// C4691_b.cpp  
// compile with: /clr /LD  
#using "C4691_a.dll"  
public ref class Client {  
public:  
   Original_Type^ ot;  
};  
```  
  
## 使用例  
 次の例では C4691 エラーが生成されます。この例では Original\_Type の定義を使用し、C4691a.dll を参照しません。  
  
 この警告を解決するには、元の型定義を含むメタデータ ファイルを参照し、ローカル宣言とローカル定義を削除します。  
  
```  
// C4691_c.cpp  
// compile with: /clr /LD /W1  
// C4691 expected  
  
// Uncomment the following line to resolve.  
// #using "C4691_a.dll"  
#using "C4691_b.dll"  
  
// Delete the following line to resolve.  
ref class Original_Type;  
  
public ref class MyClass : Client {};  
```
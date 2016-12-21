---
title: "implementation_only | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "implementation_only"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "implementation_only 属性"
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# implementation_only
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 .tlh ヘッダー ファイル \(プライマリ ヘッダー ファイル\) の生成を抑制します。  
  
## 構文  
  
```  
implementation_only  
```  
  
## 解説  
 このファイルには、タイプ ライブラリ コンテンツを公開するために使用されているすべての宣言が含まれます。  ラッパー メンバー関数を実装した .tli ヘッダー ファイルが生成され、コンパイルに含められます。  
  
 この属性の指定時には、.tli ヘッダーのコンテンツは .tlh ヘッダーで通常使用される同じ名前空間にあります。  また、メンバー関数はインライン関数として宣言されていません。  
  
 `implementation_only` 属性は、プリコンパイルされたヘッダー \(PCH\) ファイルの外部に実装を維持する方法として、[no\_implementation](../preprocessor/no-implementation.md) 属性と共に使用することが想定されています。  `no_implementation` 属性を含む `#import` ステートメントは、PCH の作成に使用されるソース領域に配置されます。  生成される PCH は、多数のソース ファイルによって使用されます。  これによって、`implementation_only` 属性を含む `#import` ステートメントが PCH 領域の外部で使用されます。  いずれかのソース ファイルでこのステートメントを 1 回だけ使用する必要があります。  これによって、各ソース ファイルについて追加の再コンパイルを行う必要なく、すべてのラッパー メンバー関数が生成されます。  
  
> [!NOTE]
>  1 つの `#import` ステートメントで `implementation_only` 属性を使用し、同時に `no_implementation` 属性を含む同じタイプ ライブラリの別の `#import` ステートメントを使用する必要があります。  それ以外の場合は、コンパイラ エラーが生成されます。  これは、`no_implementation` 属性を含む `#import` ステートメントによって生成されたラッパー クラス定義が、`implementation_only` 属性によって生成された実装をコンパイルするために必要であるためです。  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)
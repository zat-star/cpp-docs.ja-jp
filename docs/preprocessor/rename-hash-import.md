---
title: "名前の変更 (#import) | Microsoft Docs"
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
  - "Rename"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "属性の名前の変更..."
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 名前の変更 (#import)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 名前の衝突の問題を回避します。  
  
## 構文  
  
```  
rename("OldName","NewName")  
```  
  
#### パラメーター  
 `OldName`  
 タイプ ライブラリ内の古い名前。  
  
 `NewName`  
 古い名前の代わりに使用する名前。  
  
## 解説  
 この属性を指定すると、コンパイラは、結果のヘッダー ファイルで、タイプ ライブラリの *OldName* の出現箇所をすべてユーザーが指定した *NewName* に置き換えます。  
  
 この属性は、タイプ ライブラリ内の名前がシステム ヘッダー ファイル内のマクロ定義と一致する場合に使用できます。  この状況が解決されない場合は、[コンパイラ エラー C2059](../Topic/Compiler%20Error%20C2059.md) や [コンパイラ エラー C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md) などのさまざまな構文エラーが発生します。  
  
> [!NOTE]
>  置換は、結果のヘッダー ファイルで使用される名前ではなく、タイプ ライブラリで使用される名前に対して実行されます。  
  
 たとえば `MyParent` という名前のプロパティがタイプ ライブラリにあり、マクロ `GetMyParent` がヘッダー ファイルに定義され、`#import` の前で使用されているとします。  `GetMyParent` は、エラー処理の **get** プロパティのラッパー関数の既定の名前であるため、名前の競合が発生します。  問題を回避するには、`#import` ステートメント内で次の属性を使用します。  
  
```  
rename("MyParent","MyParentX")  
```  
  
 これにより、タイプ ライブラリ内の `MyParent` の名前が変更されます。  `GetMyParent` ラッパーの名前を変更しようとすると、失敗します:  
  
```  
rename("GetMyParent","GetMyParentX")  
```  
  
 これは、名前 `GetMyParent` が、結果のタイプ ライブラリ ヘッダー ファイルにのみ出現するためです。  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)
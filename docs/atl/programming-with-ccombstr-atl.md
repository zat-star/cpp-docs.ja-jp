---
title: "CComBSTR を使用したプログラミング (ATL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComBSTR クラス, プログラミング"
  - "Unicode, 使用 (CComBSTR [ATL] を)"
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CComBSTR を使用したプログラミング (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL クラス [CComBSTR](../atl/reference/ccombstr-class.md) は `BSTR` のデータ型のラッパーを提供します。  `CComBSTR` が便利なツールですが、注意を必要とするいくつかの状態になります。  
  
-   [変換の問題](#programmingwithccombstr_conversionissues)  
  
-   [範囲の問題](#programmingwithccombstr_scopeissues)  
  
-   [CComBSTR のオブジェクトを明示的に解放できます。](#programmingwithccombstr_explicitlyfreeing)  
  
-   [ループの CComBSTR のオブジェクトを使用する](#programmingwithccombstr_usingloops)  
  
-   [メモリ リークの問題](#programmingwithccombstr_memoryleaks)  
  
##  <a name="programmingwithccombstr_conversionissues"></a> 変換の問題  
 `CComBSTR` の複数のメソッドが Unicode に自動的に ANSI 文字列の引数をに変換しますが、メソッドは Unicode 形式の文字列を常に返します。  ANSI に、出力文字列を変換するには、ATL 変換クラスを使用します。  ATL 変換クラスの詳細については、[ATL と MFC の文字列変換マクロ](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md)を参照してください。  
  
### 例  
 [!CODE [NVC_ATL_Utilities#114](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#114)]  
  
 `CComBSTR` のオブジェクトを変更する場合にリテラル文字列を使用する場合はワイド文字列を使用します。  これは、不要な変換が低くなります。  
  
### 例  
 [!CODE [NVC_ATL_Utilities#115](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#115)]  
  
##  <a name="programmingwithccombstr_scopeissues"></a> 範囲の問題  
 すべての行儀が、クラスと同様に、`CComBSTR` がスコープ外に出るとリソースを解放します。  関数が `CComBSTR` の文字列へのポインターを返す場合、これは、ポインターが既に解放されているメモリを参照すると問題ができます。  このような場合、次に示すように **\[コピー\]** のメソッドを使用します。  
  
### 例  
 [!CODE [NVC_ATL_Utilities#116](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#116)]  
  
##  <a name="programmingwithccombstr_explicitlyfreeing"></a> CComBSTR のオブジェクトを明示的に解放できます。  
 オブジェクトがスコープ外になる前に明示的に `CComBSTR` のオブジェクトに含まれる文字列を解放することはできます。  文字列がリリースされた場合は、`CComBSTR` のオブジェクトは無効です。  
  
### 例  
 [!CODE [NVC_ATL_Utilities#117](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#117)]  
  
##  <a name="programmingwithccombstr_usingloops"></a> ループの CComBSTR のオブジェクトを使用する  
 特定の操作を、**\[追加\]** の `+=` の演算子やメソッドなどの実行するに `CComBSTR` のクラスがバッファーを割り当てるため、短いループ内の文字列操作を実行することはお勧めできません。  この場合、`CStringT` は、より優れたパフォーマンスを実現します。  
  
### 例  
 [!CODE [NVC_ATL_Utilities#118](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#118)]  
  
##  <a name="programmingwithccombstr_memoryleaks"></a> メモリ リークの問題  
 **\[out\]** のパラメーターとして関数に初期化された `CComBSTR` のアドレスを渡すと、メモリ リークが発生します。  
  
 次の例では、文字列 `"Initialized"` を保持するために割り当てる文字列は、関数 `MyGoodFunction` が文字列を置き換える場合漏ります。  
  
 [!CODE [NVC_ATL_Utilities#119](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#119)]  
  
 リークを回避するには、**\[out\]** のアドレスをパラメーターとして渡す前に `CComBSTR` のあるオブジェクトの **\[空\]** のメソッドを呼び出します。  
  
 関数パラメーターが **\[in, out\]**同じコードがリークが発生しないことに注意してください。  
  
## 参照  
 [概念](../atl/active-template-library-atl-concepts.md)   
 [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)   
 [wstring](../Topic/wstring.md)   
 [文字列変換に関するマクロ](../atl/reference/string-conversion-macros.md)
---
title: "CString の基本操作 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "文字, アクセス (CStrings での)"
  - "CString オブジェクト"
  - "CString オブジェクト, 基本操作"
  - "リテラル文字列, CString の操作"
  - "文字列比較, CString の操作"
  - "リテラル文字列, CString の操作"
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
caps.latest.revision: 17
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CString の基本操作
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、次の基本的な [CString](../atl-mfc-shared/reference/cstringt-class.md) 操作について説明します。  
  
-   [標準 C リテラル文字列からの CString オブジェクトの生成](#_core_creating_cstring_objects_from_standard_c_literal_strings)  
  
-   [CString 中の文字のアクセス](#_core_accessing_individual_characters_in_a_cstring)  
  
-   [2 つの CString オブジェクトの結合](#_core_concatenating_two_cstring_objects)  
  
-   [CString オブジェクトの比較](#_core_comparing_cstring_objects)  
  
-   [CString オブジェクトの変換](#_core_converting_cstring_objects)  
  
 `Class CString` は、クラス テンプレート [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md) に基づいています。  `CString` は、`CStringT` の `typedef` です。  正確には、`CString` は、クラス テンプレートを使用してクラスを定義する一般的な方法である `CStringT` の*明示的特殊化*の `typedef` です。  同様に定義されたクラスは、`CStringA` および `CStringW` です。  明示的特殊化の詳細については、「[クラス テンプレートのインスタンス化](../Topic/Class%20Template%20Instantiation.md)」を参照してください。  
  
 `CString`、`CStringA`、および `CStringW` は、atlstr.h で定義されます。  `CStringT` は、cstringt.h で定義されます。  
  
 `CString`、`CStringA`、および  `CStringW` は、`CStringT` で定義されたメソッドおよび演算子のセットを取得して、サポート対象の文字列データで使用します。  メソッドの一部は、C ランタイム ライブラリの文字列操作機能と同等か、場合によっては拡張されたものです。  
  
 メモ: `CString` はネイティブ クラスです。  C\+\+\/CLI マネージ プロジェクト用の文字列クラスの場合は、`System.String` を使用します。  
  
##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> 標準 C リテラル文字列からの CString オブジェクトの生成  
 1 つの `CString` オブジェクトを別のオブジェクトに代入できるのと同様に、C 形式のリテラル文字列を `CString` に代入できます。  
  
-   C リテラル文字列の値を `CString` オブジェクトに代入する場合。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_1.cpp)]  
  
-   `CString` オブジェクトの値を他の `CString` オブジェクトに代入する場合。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_2.cpp)]  
  
     `CString` オブジェクトを別の `CString` オブジェクトに代入すると、オブジェクトの内容がコピーされます。  したがって、2 つの文字列が、その文字列を構成する実際の文字への参照を共有することはありません。  `CString` オブジェクトを値として使用する方法の詳細については、「[CString の評価](../atl-mfc-shared/cstring-semantics.md)」を参照してください。  
  
    > [!NOTE]
    >  Unicode または ANSI 用にコンパイルできるアプリケーションを作成するには、\_T マクロを使用してリテラル文字列を記述します。  詳細については、「[Unicode とマルチバイト文字セット \(MBCS: Multibyte Character Set\) のサポート](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)」を参照してください。  
  
##  <a name="_core_accessing_individual_characters_in_a_cstring"></a> CString 中の文字のアクセス  
 `CString` オブジェクト内の個々の文字には、`GetAt` メソッドおよび `SetAt` メソッドを使用してアクセスできます。  `GetAt` の代わりに配列要素、つまり添字演算子 \(\[ \]\) を使用して、個々の文字を取得することもできます。  この方法は、標準の C 形式文字列で、インデックスを使用して配列要素にアクセスする方法と似ています。`CString` 内の文字のインデックス値は、0 から始まります。  
  
##  <a name="_core_concatenating_two_cstring_objects"></a> 2 つの CString オブジェクトの結合  
 2 つの `CString` オブジェクトを結合するには、結合演算子 \(\+ または \+\=\) を使用します。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_3.cpp)]  
  
 結合演算子 \(\+ または \+\=\) の引数のうち少なくとも 1 つは `CString` オブジェクトにする必要がありますが、それ以外の引数には文字列定数 \(`"big"` など\) または `char` \(x など\) を使用できます。  
  
##  <a name="_core_comparing_cstring_objects"></a> CString オブジェクトの比較  
 `Compare` メソッド、および  `CString` の \=\= 演算子は等価です。  `Compare`、`operator==`、および `CompareNoCase` は MBCS および Unicode に対応しています。また、`CompareNoCase` は大文字と小文字を区別しません。  `CString` の `Collate` メソッドはロケールを認識しますが、`Compare` よりも動作が遅い場合があります。  `Collate` は、固有の並べ替え順序をサポートする必要がある場合以外は使用しないでください。  
  
 [CString](../atl-mfc-shared/reference/cstringt-class.md) の比較関数および相当する Unicode\/MBCS 互換の C ランタイム ライブラリ関数を次の表に示します。  
  
|CString の関数|MBCS ランタイム関数|Unicode 関数|  
|-----------------|------------------|----------------|  
|`Compare`|`_mbscmp`|`wcscmp`|  
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|  
|`Collate`|`_mbscoll`|`wcscoll`|  
  
 `CStringT` クラス テンプレートは、`CString` で使用できる関係演算子 \(\<、\<\=、\>\=、\>、\=\=、および \!\=\) を定義します。  次の例に示すように、これらの演算子を使用して、2 つの `CStrings` を比較できます。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_4.cpp)]  
  
##  <a name="_core_converting_cstring_objects"></a> CString オブジェクトの変換  
 CString オブジェクトを他の文字列型に変換する方法については、「[方法: さまざまな文字列型間で変換する](../Topic/How%20to:%20Convert%20Between%20Various%20String%20Types.md)」を参照してください。  
  
## wcout として CString の使用  
 CString の `wcout` を使用するには、次の例に示すように、明示的に `const wchar_t*` にオブジェクトをキャストする必要があります:  
  
```  
CString cs("meow");  
  wcout << (const wchar_t*) cs << endl;  
  
```  
  
 キャストを使用せずに、`cs` は `void*` と `wcout` は、オブジェクトのアドレスを印刷すると同時に処理されます。  この動作は C\+\+ 標準に準拠正しく、自身にあるテンプレート引数を差し引いたとオーバーロードの解決の間の滑らかな相互作用によって発生します。  
  
## 参照  
 [文字列](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)   
 [クラス テンプレートのインスタンス化](../Topic/Class%20Template%20Instantiation.md)   
 [クラス テンプレートの明示的特殊化](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)   
 [クラス テンプレートの部分的特殊化](../cpp/template-specialization-cpp.md)   
 [方法: さまざまな文字列型間で変換する](../Topic/How%20to:%20Convert%20Between%20Various%20String%20Types.md)
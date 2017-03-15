---
title: "方法: .NET コレクションを STL/CLR コンテナーに変換する | Microsoft Docs"
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
  - "STL/CLR コンテナー [STL/CLR]"
  - "STL/CLR, 変換 (.NET コレクションから)"
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: .NET コレクションを STL/CLR コンテナーに変換する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、等価 STL\/CLR のコンテナーに .NET のコレクションを変換する方法を示します。  一例として、STL\/CLR [vector](../dotnet/vector-stl-clr.md) に .NET <xref:System.Collections.Generic.List%601> を変換する方法と、STL\/CLR [マップ](../dotnet/map-stl-clr.md)に .NET <xref:System.Collections.Generic.Dictionary%602> を変換する方法について説明しますが、プロシージャは、すべてのコレクションおよびコンテナーに似ています。  
  
### コレクションのコンテナーを作成するには  
  
1.  コレクション全体を変換するには、STL\/CLR のコンテナーを作成し、コンストラクターにコレクションを渡します。  
  
     最初の例では、この手順を示します。  
  
 または  
  
1.  [collection\_adapter](../Topic/collection_adapter%20\(STL-CLR\).md) オブジェクトを作成してジェネリック STL\/CLR のコンテナーを作成します。  このテンプレート クラスは、引数として .NET インターフェイスのコレクションを取得します。  どのインターフェイスがサポートされているかを確認するには、[collection\_adapter](../Topic/collection_adapter%20\(STL-CLR\).md)を参照してください。  
  
2.  コンテナーに .NET のコレクションの内容をコピーします。  これは [アルゴリズム](../Topic/algorithm%20\(STL-CLR\).md)STL\/CLR を使用するか、.NET のコレクションを反復処理し、STL\/CLR のコンテナーに各要素のコピーを挿入することによって行うことができます。  
  
     2 番目の例では、この手順を示します。  
  
## 使用例  
 この例では、ジェネリック <xref:System.Collections.Generic.List%601> を作成し、5 個の要素を追加します。  次に、引数として <xref:System.Collections.Generic.IEnumerable%601> を受け取るコンストラクターを使用して `vector` を作成します。  
  
```  
// cliext_convert_list_to_vector.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/algorithm>  
#include <cliext/vector>  
  
using namespace System;  
using namespace System::Collections;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    List<int> ^primeNumbersColl = gcnew List<int>();  
    primeNumbersColl->Add(2);  
    primeNumbersColl->Add(3);  
    primeNumbersColl->Add(5);  
    primeNumbersColl->Add(7);  
    primeNumbersColl->Add(11);  
  
    cliext::vector<int> ^primeNumbersCont =  
        gcnew cliext::vector<int>(primeNumbersColl);  
  
    Console::WriteLine("The contents of the cliext::vector are:");  
    cliext::vector<int>::const_iterator it;  
    for (it = primeNumbersCont->begin(); it != primeNumbersCont->end(); it++)  
    {  
        Console::WriteLine(*it);  
    }  
}  
```  
  
  **cliext::vector の内容は次のとおりです。:**  
**2**  
**3**  
**5**  
**7**  
**11**   
## 使用例  
 この例では、ジェネリック <xref:System.Collections.Generic.Dictionary%602> を作成し、5 個の要素を追加します。  その後、単純な STL\/CLR のコンテナーとして <xref:System.Collections.Generic.Dictionary%602> をラップするために `collection_adapter` を作成します。  最後に、`map` を作成し、`map` に `collection_adapter`を反復処理して <xref:System.Collections.Generic.Dictionary%602> の内容をコピーします。  このプロセスの間に、`make_pair` 関数を使用して、新しいコントロールを作成し、`map`に新しいペアを挿入します。  
  
```  
// cliext_convert_dictionary_to_map.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/algorithm>  
#include <cliext/map>  
  
using namespace System;  
using namespace System::Collections;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    System::Collections::Generic::Dictionary<float, int> ^dict =  
        gcnew System::Collections::Generic::Dictionary<float, int>();  
    dict->Add(42.0, 42);  
    dict->Add(13.0, 13);  
    dict->Add(74.0, 74);  
    dict->Add(22.0, 22);  
    dict->Add(0.0, 0);  
  
    cliext::collection_adapter<System::Collections::Generic::IDictionary<float, int>> dictAdapter(dict);  
    cliext::map<float, int> aMap;  
    for each (KeyValuePair<float, int> ^kvp in dictAdapter)  
    {  
        cliext::pair<float, int> aPair = cliext::make_pair(kvp->Key, kvp->Value);  
        aMap.insert(aPair);  
    }  
  
    Console::WriteLine("The contents of the cliext::map are:");  
    cliext::map<float, int>::const_iterator it;  
    for (it = aMap.begin(); it != aMap.end(); it++)  
    {  
        Console::WriteLine("Key: {0:F} Value: {1}", it->first, it->second);  
    }  
}  
```  
  
  **cliext::map の内容は次のとおりです。:**  
**Key: 0.00 Value: 0**  
**Key: 13.00 Value: 13**  
**Key: 22.00 Value: 22**  
**Key: 42.00 Value: 42**  
**Key: 74.00 Value: 74**   
## 参照  
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)   
 [adapter](../dotnet/adapter-stl-clr.md)   
 [方法: STL\/CLR コンテナーを .NET コレクションに変換する](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)
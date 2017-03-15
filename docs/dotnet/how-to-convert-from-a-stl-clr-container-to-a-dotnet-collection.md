---
title: "方法: STL/CLR コンテナーを .NET コレクションに変換する | Microsoft Docs"
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
  - "STL/CLR, 変換 (.NET コレクションに)"
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: STL/CLR コンテナーを .NET コレクションに変換する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、等価の .NET コレクションに STL\/CLR のコンテナーを変換する方法を示します。  一例として、.NET <xref:System.Collections.Generic.ICollection%601> に [vector](../dotnet/vector-stl-clr.md) STL\/CLR を変換する方法、および .NET <xref:System.Collections.Generic.IDictionary%602>に [マップ](../dotnet/map-stl-clr.md) STL\/CLR を変換する方法について説明しますが、プロシージャは、すべてのコレクションおよびコンテナーに似ています。  
  
### コンテナーのコレクションを作成するには  
  
1.  次の方法のいずれかを使用します。  
  
    -   コンテナーの一部を変換し、[make\_collection](../dotnet/make-collection-stl-clr.md) 関数を呼び出し、.NET のコレクションにコピーされる STL\/CLR のコンテナーの開始の反復子と最後の反復子を渡します。  このテンプレート関数は、テンプレート引数として STL\/CLR の反復子を取得します。  最初の例では、このメソッドを示しています。  
  
    -   全体のコンテナーを変換するには、適切な .NET のコレクション インターフェイスまたはインターフェイス コレクションにコンテナーをキャストしてください。  2 番目の例では、このメソッドを示しています。  
  
## 使用例  
 この例では、`vector` STL\/CLR を作成し、5 個の要素を追加します。  次に、`make_collection` 関数を呼び出して、.NET のコレクションを作成します。  最後に、新しく作成されたコレクションの内容が表示されます。  
  
```  
// cliext_convert_vector_to_icollection.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/vector>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::vector<int> primeNumbersCont;  
    primeNumbersCont.push_back(2);  
    primeNumbersCont.push_back(3);  
    primeNumbersCont.push_back(5);  
    primeNumbersCont.push_back(7);  
    primeNumbersCont.push_back(11);  
  
    System::Collections::Generic::ICollection<int> ^iColl =  
        make_collection<cliext::vector<int>::iterator>(  
            primeNumbersCont.begin() + 1,  
            primeNumbersCont.end() - 1);  
  
    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");  
    for each (int i in iColl)  
    {  
        Console::WriteLine(i);  
    }  
}  
```  
  
  **System::Collections::Generic::ICollection の内容は次のとおりです。:**  
**3**  
**5**  
**7**   
## 使用例  
 この例では、`map` STL\/CLR を作成し、5 個の要素を追加します。  次に、.NET <xref:System.Collections.Generic.IDictionary%602> を作成し、`map` を直接割り当てられます。  最後に、新しく作成されたコレクションの内容が表示されます。  
  
```  
// cliext_convert_map_to_idictionary.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/map>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;  
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));  
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));  
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));  
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));  
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));  
  
    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;  
  
    Console::WriteLine("The contents of the IDictionary are:");  
    for each (KeyValuePair<float, int> ^kvp in iDict)  
    {  
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);  
    }  
}  
```  
  
  **IDictionary の内容は次のとおりです。:**  
**Key: 0.00 Value: 0**  
**Key: 13.00 Value: 13**  
**Key: 22.00 Value: 22**  
**Key: 42.00 Value: 42**  
**Key: 74.00 Value: 74**   
## 参照  
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)   
 [方法: .NET コレクションを STL\/CLR コンテナーに変換する](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)   
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)
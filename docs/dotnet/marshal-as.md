---
title: "marshal_as | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_as"
  - "msclr.interop.marshal_as"
  - "msclr::interop::marshal_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_as テンプレート [C++]"
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# marshal_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このメソッドは、ネイティブ環境とマネージ環境の間でデータを変換します。  
  
## 構文  
  
```  
To_Type marshal_as<To_Type>(  
   From_Type input   
);  
```  
  
#### パラメーター  
 \[入力\] `input`  
 `To_Type` 変数にマーシャリングしようとする値。  
  
## 戻り値  
 `input`の値を変換した後の `To_Type` 型の変数。  
  
## 解説  
 このメソッドは、ネイティブ型とマネージ型の間でデータを変換する簡素化された方法を提供します。  どのデータ型がサポートされているかを確認するには、[C\+\+ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md) を参照してください。  一部のデータ変換では、コンテキストが必要です。  [marshal\_context クラス](../dotnet/marshal-context-class.md) を使用してそれらのデータ型を変換できます。  
  
 サポートされていない 2 つのデータ型をマーシャリングしようとすると、`marshal_as` は、コンパイル時にエラー [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) を生成します。  詳細については、このエラーと共に提供されるメッセージを参照してください。  `C4996` エラーは、使用されなくなった関数の場合に加えて、他の状況で生成される可能性もあります。  このエラーの 1 つの例は、サポートされていない 2 つのデータ型をマーシャリングしようとする場合です。  
  
 マーシャリング ライブラリは、複数のヘッダー ファイルで構成されます。  どの変換でもただ 1 つのファイルが必要ですが、他の変換で必要とされる追加ファイルをインクルードすることもできます。  どのファイルにどの変換が関連付けられているかを確認するには、`Marshaling Overview` の表を参照してください。  どの変換を行おうとするかにかかわりなく、名前空間の要件が常に有効になります。  
  
## 使用例  
 この例では、`const char*` から `System::String` 変数型へのマーシャリングを行います。  
  
```  
// marshal_as_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   const char* message = "Test String to Marshal";  
   String^ result;  
   result = marshal_as<String^>( message );  
   return 0;  
}  
```  
  
## 必要条件  
 **Header file:** \<msclr\\marshal.h、\> \<msclr\\marshal\_windows.h、\> \<msclr\\marshal\_cppstd.h、または\> \<msclr\\marshal\_atl.h\>  
  
 **名前空間:** msclr::interop  
  
## 参照  
 [C\+\+ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_context クラス](../dotnet/marshal-context-class.md)
---
title: "marshal_context::marshal_as | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_context::marshal_as"
  - "marshal_context.marshal_as"
  - "msclr.interop.marshal_context.marshal_as"
  - "msclr::interop::marshal_context::marshal_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context クラス [C++], 操作"
ms.assetid: 24a1afee-51c0-497c-948c-f77fe43635c8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# marshal_context::marshal_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

特定のデータ オブジェクトのマーシャリングをマネージとネイティブ データ型間の変換します。  
  
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
 この関数は、特定のデータ オブジェクトのマーシャリングを実行します。  [C\+\+ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)の表に示す変換でのみ、この関数を使用します。  
  
 サポートされていない 2 つのデータ型をマーシャリングしようとすると、`marshal_as` は、コンパイル時にエラー [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) を生成します。  詳細については、このエラーと共に提供されるメッセージを参照してください。  `C4996` エラーは、使用されなくなった関数の場合に加えて、他の状況で生成される可能性もあります。  このエラーを生成するには、2 種類の条件はサポートされていないデータ型のペアをマーシャリングすると、コンテキストを必要とする変換に `marshal_as` を使用しようとしています。  
  
 マーシャリング ライブラリは、複数のヘッダー ファイルで構成されます。  どの変換でもただ 1 つのファイルが必要ですが、他の変換で必要とされる追加ファイルをインクルードすることもできます。  どのマーシャリング ファイルが各変換に含める必要があるか `Marshaling Overview in C++` の表に示します。  
  
## 使用例  
 この例では `System::String` にマーシャリングするためのコンテキストを `const char *` から変数の型を作成します。  変換されたデータはコンテキストを削除する行の後には有効ではありません。  
  
```  
// marshal_context_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   marshal_context^ context = gcnew marshal_context();  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = context->marshal_as<const char*>( message );  
   delete context;  
   return 0;  
}  
```  
  
## 必要条件  
 **Header file:** \<msclr\\marshal.h、\> \<msclr\\marshal\_windows.h、\> \<msclr\\marshal\_cppstd.h、または\> \<msclr\\marshal\_atl.h\>  
  
 **名前空間:** msclr::interop  
  
## 参照  
 [C\+\+ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)   
 [marshal\_context クラス](../dotnet/marshal-context-class.md)
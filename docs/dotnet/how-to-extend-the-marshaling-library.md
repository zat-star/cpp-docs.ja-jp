---
title: "方法: マーシャリング ライブラリを拡張する | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "マーシャリング ライブラリ, 拡張"
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: マーシャリング ライブラリを拡張する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、データ型間の変換をより充実させるためにマーシャリング ライブラリを拡張する方法について説明します。  ユーザーは、現在ライブラリでサポートされていないどんなデータ変換についてでもマーシャリング ライブラリを拡張することができます。  
  
 マーシャリング ライブラリの拡張は 2 つの方法のいずれかによって行うことができます。[marshal\_context クラス](../dotnet/marshal-context-class.md) を使う方法と使わない方法です。  [C\+\+ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md) のトピックを参照して、新しい変換がコンテキストを必要とするかどうかを確認してください。  
  
 どちらの場合もまず、新しいマーシャリング変換のためのファイルを作成します。  これを行うのは、標準マーシャリング ライブラリ ファイルの整合性を保持するためです。  プロジェクトを別のコンピューターまたは別のプログラマに移植する場合は、残りのプロジェクトと共に新しいマーシャリング ファイルをコピーする必要があります。  こうして、プロジェクトを受け取るユーザーは新しい変換も受け取ることになり、ライブラリ ファイルの変更を行わずにすみます。  
  
### コンテキストを必要としない変換でマーシャリング ライブラリを拡張するには  
  
1.  新しいマーシャリング機能を格納するファイル \(たとえば MyMarshal.h\) を作成します。  
  
2.  次のうちの 1 つ以上のマーシャル ライブラリ ファイルを組み込みます。  
  
    -   marshal.h \(基本型用\)。  
  
    -   marshal\_windows.h \(Windows データ型用\)。  
  
    -   marshal\_cppstd.h \(STL データ型用\)。  
  
    -   marshal\_atl.h \(ATL データ型用\)。  
  
3.  この手順の最後にあるコードを使用して、変換関数を作成します。  このコードの TO は変換先の型、FROM は変換元の型、`from` は変換されるパラメーターです。  
  
4.  変換ロジックに関するコメントをコードに置き換えます。このコードは、`from` パラメーターを TO 型のオブジェクトに変換し、変換されたオブジェクトを戻します。  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      inline TO marshal_as<TO, FROM> (const FROM& from) {  
         // Insert conversion logic here, and return a TO parameter.  
      }  
   }  
}  
```  
  
### コンテキストを必要とする変換でマーシャリング ライブラリを拡張するには  
  
1.  新しいマーシャリング機能を格納するファイル \(たとえば MyMarshal.h\) を作成します。  
  
2.  次のうちの 1 つ以上のマーシャル ライブラリ ファイルを組み込みます。  
  
    -   marshal.h \(基本型用\)。  
  
    -   marshal\_windows.h \(Windows データ型用\)。  
  
    -   marshal\_cppstd.h \(STL データ型用\)。  
  
    -   marshal\_atl.h \(ATL データ型用\)。  
  
3.  この手順の最後にあるコードを使用して、変換関数を作成します。  このコードの TO は変換先の型、FROM は変換元の型、`toObject` は結果を格納するポインター、`fromObject` は変換されるパラメーターです。  
  
4.  初期化に関するコメントを、`toPtr` を適切な空の値に初期化するコードに置き換えます。  たとえば、ポインターの場合は `NULL` に設定します。  
  
5.  *TO* の型のオブジェクトに `from` パラメーターを変換するコードに変換ロジックに関するコメントを置き換えます。  この変換されたオブジェクトは `toPtr` に格納されます。  
  
6.  `toObject` の設定に関するコメントを、`toObject` を変換後のオブジェクトに設定するコードに置き換えます。  
  
7.  ネイティブ リソースのクリーンアップに関するコメントを、`toPtr` によって割り当てられたすべてのメモリを解放するコードに置き換えます。  `toPtr` が `new` を使ってメモリを割り当てた場合は、`delete` を使用してメモリを解放します。  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<TO, FROM> : public context_node_base  
      {  
      private:  
         TO toPtr;  
      public:  
         context_node(TO& toObject, FROM fromObject)  
         {  
            // (Step 4) Initialize toPtr to the appropriate empty value.  
            // (Step 5) Insert conversion logic here.  
            // (Step 6) Set toObject to the converted parameter.  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // (Step 7) Clean up native resources.  
         }  
      };  
   }  
}   
```  
  
## 使用例  
 コンテキストを必要としない変換でマーシャリング ライブラリを拡張する例を次に示します。  この例のコードは、従業員情報をネイティブ データ型からマネージ データ型に変換します。  
  
```  
// MyMarshalNoContext.cpp  
// compile with: /clr  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   char* name;  
   char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      inline ManagedEmp^ marshal_as<ManagedEmp^, NativeEmp> (const NativeEmp& from) {  
         ManagedEmp^ toValue = gcnew ManagedEmp;  
         toValue->name = marshal_as<System::String^>(from.name);  
         toValue->address = marshal_as<System::String^>(from.address);  
         toValue->zipCode = from.zipCode;  
         return toValue;  
      }  
   }  
}  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {   
   NativeEmp employee;  
  
   employee.name = "Jeff Smith";  
   employee.address = "123 Main Street";  
   employee.zipCode = 98111;  
  
   ManagedEmp^ result = marshal_as<ManagedEmp^>(employee);  
  
   Console::WriteLine("Managed name: {0}", result->name);  
   Console::WriteLine("Managed address: {0}", result->address);  
   Console::WriteLine("Managed zip code: {0}", result->zipCode);  
  
   return 0;  
}  
```  
  
 前の例では、`marshal_as` 関数は変換されたデータへのハンドルを戻します。  これは、データのコピーがそれ以上作成されないようにするために行われました。  変数を直接戻すと、それに伴って不要なパフォーマンス コストが発生します。  
  
  **Managed name: Jeff Smith**  
**Managed address: 123 Main Street**  
**Managed zip code: 98111**   
## 使用例  
 従業員情報をマネージ データ型からネイティブ データ型に変換する例を次に示します。  この変換は、マーシャリング コンテキストを必要とします。  
  
```  
// MyMarshalContext.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   const char* name;  
   const char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<NativeEmp*, ManagedEmp^> : public context_node_base  
      {  
      private:  
         NativeEmp* toPtr;  
         marshal_context context;  
      public:  
         context_node(NativeEmp*& toObject, ManagedEmp^ fromObject)  
         {  
            // Conversion logic starts here  
            toPtr = NULL;  
  
            const char* nativeName;  
            const char* nativeAddress;  
  
            // Convert the name from String^ to const char*.  
            System::String^ tempValue = fromObject->name;  
            nativeName = context.marshal_as<const char*>(tempValue);  
  
            // Convert the address from String^ to const char*.  
            tempValue = fromObject->address;  
            nativeAddress = context.marshal_as<const char*>(tempValue);  
  
            toPtr = new NativeEmp();  
            toPtr->name = nativeName;  
            toPtr->address = nativeAddress;  
            toPtr->zipCode = fromObject->zipCode;  
  
            toObject = toPtr;  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // When the context is deleted, it will free the memory  
            // allocated for toPtr->name and toPtr->address, so toPtr  
            // is the only memory that needs to be freed.  
            if (toPtr != NULL) {  
               delete toPtr;  
               toPtr = NULL;  
            }  
         }  
      };  
   }  
}   
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   ManagedEmp^ employee = gcnew ManagedEmp();  
  
   employee->name = gcnew String("Jeff Smith");  
   employee->address = gcnew String("123 Main Street");  
   employee->zipCode = 98111;  
  
   marshal_context context;  
   NativeEmp* result = context.marshal_as<NativeEmp*>(employee);  
  
   if (result != NULL) {  
      printf_s("Native name: %s\nNative address: %s\nNative zip code: %d\n",  
         result->name, result->address, result->zipCode);  
   }  
  
   return 0;  
}  
```  
  
  **Native name: Jeff Smith**  
**Native address: 123 Main Street**  
**Native zip code: 98111**   
## 参照  
 [C\+\+ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)
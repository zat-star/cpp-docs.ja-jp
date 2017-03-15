---
title: "try、throw、および catch ステートメント (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "catch_cpp"
  - "throw"
  - "try_cpp"
  - "try"
  - "throw_cpp"
  - "catch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "catch キーワード [C++]"
  - "キーワード [C++] 例外処理"
  - "C++ 例外処理、ステートメントの構文"
  - "try-catch 例外処理は、try-catch キーワード [C++]"
  - "throw キーワード [C++]"
  - "try-catch キーワード [C++]"
  - "try-catch キーワード [C++] 例外処理"
  - "例外はスローされず、throw キーワード"
  - "try-catch キーワード [C++]、throw キーワード [C++]"
  - "C++ 例外処理を実装する例外のスロー"
  - "スロー (例外を)"
  - "throw キーワード [C++] throw() および throw (...)"
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
caps.latest.revision: 24
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# try、throw、および catch ステートメント (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C++ で例外処理を実装するには、`try`、`throw`、`catch` の式を使用します。  
  
 まず、`try` ブロックを使用して、例外をスローする可能性がある 1 つ以上のステートメントを囲みます。  
  
 `throw` は、`try` ブロックで例外条件 (多くの場合はエラー) が発生したことを通知するために使用します。 任意の型のオブジェクトを `throw` 式のオペランドとして使用できます。 通常、このオブジェクトを使用してエラーに関する情報を通知します。 使用することお勧めをほとんどの場合、 [std::exception](../standard-library/exception-class1.md) クラスまたは標準ライブラリで定義されている派生クラスのいずれかです。 これらのいずれのクラスも適さない場合は、`std::exception` から派生させた独自の例外クラスを使用することをお勧めします。  
  
 スローされる可能性のある例外を処理するために、1 つ以上の `catch` ブロックを `try` ブロックの直後に実装します。 各 `catch` ブロックには、処理できる例外の型を指定します。  
  
 次の例では、`try` ブロックとそのハンドラーを示しています。 `GetNetworkResource()` では、ネットワーク接続を介してデータを取得するとします。また、2 つの型の例外として `std::exception` から派生させたユーザー定義のクラスを使用するとします。 例外は `const` ステートメントの `catch` 参照でキャッチしています。 例外は値でスローし、const 参照でキャッチすることをお勧めします。  
  
## <a name="example"></a>例  
  
```  
  
MyData md;  
try {  
   // Code that could throw an exception  
   md = GetNetworkResource();  
}  
catch (const networkIOException& e) {  
   // Code that executes when an exception of type  
   // networkIOException is thrown in the try block  
   // ...  
   // Log error message in the exception object  
   cerr << e.what();  
}  
catch (const myDataFormatException& e) {  
   // Code that handles another exception type  
   // ...  
   cerr << e.what();  
}  
  
// The following syntax shows a throw expression  
MyData GetNetworkResource()  
{  
   // ...  
   if (IOSuccess == false)  
      throw networkIOException("Unable to connect");  
   // ...  
   if (readError)  
      throw myDataFormatException("Format error");   
   // ...  
}  
```  
  
## <a name="remarks"></a>コメント  
 `try` 句の後ろのコードは、コードの保護されたコード セクションです。  `throw` 式 *スロー*-つまりを発生させます — 例外です。 `catch` 句の後ろのコード ブロックが例外ハンドラーです。 これは、ハンドラーを *キャッチ* 場合にスローされる例外の型、 `throw` と `catch` 式に互換性があります。 型の一致を制御する規則の一覧については `catch` ブロックを参照してください [方法 Catch ブロックの評価](../Topic/How%20Catch%20Blocks%20are%20Evaluated%20\(C++\).md)します。 `catch` ステートメントで型ではなく省略記号 (...) を指定した場合、`catch` ブロックはいずれの型の例外も処理します。 コンパイルするときに、 [/EHa](../build/reference/eh-exception-handling-model.md) オプション、C 構造化例外とメモリ保護、0 による除算、および浮動小数点の違反などのシステムまたはアプリケーションによって生成される非同期例外が含まれます。 `catch` ブロックは一致する型を検索するプログラムの順序で処理されるため、省略記号を指定したハンドラーは関連付ける `try` ブロックの最後のハンドラーにする必要があります。 `catch(...)` は慎重に使用してください。プログラムの実行が継続されるには、キャッチした特定の例外を処理する方法を catch ブロックに記述する必要があります。 `catch(...)` ブロックは通常、プログラムの実行を停止する前に、エラーを記録して特別なクリーンアップを実行するために使用します。  
  
 オペランドのない `throw` 式は現在処理中の例外を再スローします。 この方法は例外を再スローするときにお勧めします。元の例外のポリモーフィックな型情報が保持されるためです。 このような式は `catch` ハンドラー内か、`catch` ハンドラーから呼び出された関数内でのみ使用する必要があります。 再スローされた例外オブジェクトはコピーではなく元の例外オブジェクトです。  
  
```  
try {  
   throw CSomeOtherException();  
}  
catch(...) {  
   // Catch all exceptions – dangerous!!!  
   // Respond (perhaps only partially) to the exception, then  
   // re-throw to pass the exception to some other handler  
   // ...  
   throw;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 例外処理](../cpp/cpp-exception-handling.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [未処理の C++ 例外](../cpp/unhandled-cpp-exceptions.md)   
 [__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)
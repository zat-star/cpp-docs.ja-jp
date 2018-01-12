---
title: "try、throw、および catch ステートメント (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- catch_cpp
- try_cpp
- throw_cpp
dev_langs: C++
helpviewer_keywords:
- catch keyword [C++]
- keywords [C++], exception handling
- C++ exception handling, statement syntax
- try-catch keyword [C++], about try-catch exception handling
- throw keyword [C++]
- try-catch keyword [C++]
- try-catch keyword [C++], exception handling
- throwing exceptions [C++], throw keyword
- try-catch keyword [C++], throw keyword [C++]s
- throwing exceptions [C++], implementing C++ exception handling
- throwing exceptions [C++]
- throw keyword [C++], throw() vs. throw(...)
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b100f1ee61b06639e75290fafd01dca6a10a820c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="try-throw-and-catch-statements-c"></a>try、throw、および catch ステートメント (C++)
C++ で例外処理を実装するには、`try`、`throw`、`catch` の式を使用します。  
  
 まず、`try` ブロックを使用して、例外をスローする可能性がある 1 つ以上のステートメントを囲みます。  
  
 `throw` は、`try` ブロックで例外条件 (多くの場合はエラー) が発生したことを通知するために使用します。 任意の型のオブジェクトを `throw` 式のオペランドとして使用できます。 通常、このオブジェクトを使用してエラーに関する情報を通知します。 使用することお勧めをほとんどの場合、 [std::exception](../standard-library/exception-class.md)クラスまたは標準ライブラリで定義されている派生クラスのいずれか。 これらのいずれのクラスも適さない場合は、`std::exception` から派生させた独自の例外クラスを使用することをお勧めします。  
  
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
 `try` 句の後ろのコードは、コードの保護されたコード セクションです。 `throw`式*スロー*-を発生させます — 例外。 `catch` 句の後ろのコード ブロックが例外ハンドラーです。 これは、ハンドラーを*キャッチ*場合にスローされる例外内の型、`throw`と`catch`式は互換性があります。 型が一致するかを制御する規則の一覧については`catch`ブロックを参照してください[方法 Catch ブロックの評価](../cpp/how-catch-blocks-are-evaluated-cpp.md)です。 `catch` ステートメントで型ではなく省略記号 (...) を指定した場合、`catch` ブロックはいずれの型の例外も処理します。 コンパイルするとき、 [/EHa](../build/reference/eh-exception-handling-model.md)オプション、C 構造化例外とメモリの保護、0 による除算、および浮動小数点の違反などのシステムまたはアプリケーションによって生成される非同期例外が含まれます. `catch` ブロックは一致する型を検索するプログラムの順序で処理されるため、省略記号を指定したハンドラーは関連付ける `try` ブロックの最後のハンドラーにする必要があります。 `catch(...)` は慎重に使用してください。プログラムの実行が継続されるには、キャッチした特定の例外を処理する方法を catch ブロックに記述する必要があります。 `catch(...)` ブロックは通常、プログラムの実行を停止する前に、エラーを記録して特別なクリーンアップを実行するために使用します。  
  
 オペランドのない `throw` 式は現在処理中の例外を再スローします。 この方法は例外を再スローするときにお勧めします。元の例外のポリモーフィックな型情報が保持されるためです。 このような式は `catch` ハンドラー内か、`catch` ハンドラーから呼び出された関数内でのみ使用する必要があります。 再スローされた例外オブジェクトはコピーではなく元の例外オブジェクトです。  
  
```  
try {  
   throw CSomeOtherException();  
}  
catch(...) {  
   // Catch all exceptions - dangerous!!!  
   // Respond (perhaps only partially) to the exception, then  
   // re-throw to pass the exception to some other handler  
   // ...  
   throw;  
}  
```  
  
## <a name="see-also"></a>参照  
 [C++ 例外処理](../cpp/cpp-exception-handling.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [未処理の C++ 例外](../cpp/unhandled-cpp-exceptions.md)   
 [__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)
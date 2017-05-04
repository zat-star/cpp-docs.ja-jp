---
title: "Array と WriteOnlyArray (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
caps.latest.revision: 28
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 28
---
# Array と WriteOnlyArray (C++/CX)
[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] プログラムでは、正規の C スタイル配列または [std::array](../standard-library/array-class-stl.md) を自由に使用できます \(ただし、[std::vector](../Topic/vector%20Class%201.md) の方が適していることが多い\) が、メタデータで発行されるどの API においても、使用法に応じて、C スタイル配列またはベクターを [Platform::Array](../cppcx/platform-array-class.md) 型または [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) 型に変換する必要があります。[Platform::Array](../cppcx/platform-array-class.md) 型は、[std::vector](../Topic/vector%20Class%201.md) ほどには効率的でも強力でもありません。そのため、一般的なガイドラインとして、配列要素で多くの操作を実行する内部コードでは使用を避ける必要があります。  
  
 次の配列型は、ABI を介して渡すことができます。  
  
1.  const Platform::Array^  
  
2.  Platform::Array^\*  
  
3.  Platform::WriteOnlyArray  
  
4.  Platform::Array^ の戻り値  
  
 これらの配列型は、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] によって定義された 3 種類の配列パターンの実装に使用します。  
  
 PassArray  
 呼び出し元が、配列をメソッドに渡すときに使用します。 C\+\+ 入力パラメーターの型は、`const`[Platform::Array](../cppcx/platform-array-class.md)\<T\> です。  
  
 FillArray  
 呼び出し元が、メソッドが入力する配列を渡すときに使用します。 C\+\+ 入力パラメーターの型は、[Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)\<T\> です。  
  
 ReceiveArray  
 呼び出し元が、メソッドが割り当てる配列を受け取るときに使用します。 C\+\+\/CX では、配列を Array^ として戻り値で返すことも、型 Array^\* として Out パラメーターとして返すこともできます。  
  
## PassArray パターン  
 クライアント コードが配列を C\+\+ メソッドに渡し、メソッドがその配列を変更しない場合、メソッドはその配列を定数 Array^ として受け入れます。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] アプリケーション バイナリ インターフェイス \(ABI\) レベルでは、これは PassArray と呼ばれます。 次の例は、JavaScript に割り当てられた配列を、読み取り側の C\+\+ 関数に渡す方法を示しています。  
  
 [!code-javascript[cx_arrays#101](../snippets/javascript/VS_Snippets_Misc/cx_arrays/javascript/default.js#101)]  
  
 次のスニペットは、C\+\+ メソッドを示します。  
  
 [!code-cpp[cx_arrays#01](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.cpp#01)]  
  
## ReceiveArray パターン  
 ReceiveArray パターンでは、クライアント コードは配列を宣言し、それにメモリを割り当てて初期化するメソッドに渡します。 C\+\+ 入力パラメーターの型は、ハットへのポインター `Array<T>^*` です。 次の例は、JavaScript で配列オブジェクトを宣言し、それを、メモリを割り当て、要素を初期化して JavaScript に返す C\+\+ 関数に渡す方法を示しています。 JavaScript は、割り当てられた配列を戻り値として扱いますが、C\+\+ 関数は出力パラメーターとして扱います。  
  
 [!code-javascript[cx_arrays#102](../snippets/javascript/VS_Snippets_Misc/cx_arrays/javascript/default.js#102)]  
  
 次のスニペットは、C\+\+ メソッドを実装する 2 通りの方法を示します。  
  
 [!code-cpp[cx_arrays#02](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.cpp#02)]  
  
## Fill 配列  
 配列を呼び出し元で割り当て、呼び出し先で初期化または変更する場合は、`WriteOnlyArray` を使用します。 次の例は、`WriteOnlyArray` を使用する C\+\+ 関数を実装して、JavaScript から呼び出す方法を示しています。  
  
 [!code-javascript[cx_arrays#103](../snippets/javascript/VS_Snippets_Misc/cx_arrays/javascript/default.js#103)]  
  
 次のスニペットは、C\+\+ メソッドを実装する方法を示します。  
  
 [!code-cpp[cx_arrays#03](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.cpp#03)]  
  
## 配列変換  
 この例では、[Platform::Array](../cppcx/platform-array-class.md) を使用して、その他の種類のコレクションを構築する方法を示しています。  
  
 [!code-cpp[cx_arrays#05](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.cpp#05)]  
  
 次の例は、[Platform::Array](../cppcx/platform-array-class.md) を C スタイル配列から構築して、パブリック メソッドから返す方法を示しています。  
  
 [!code-cpp[cx_arrays#06](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.cpp#06)]  
  
## ジャグ配列  
 Windows ランタイムの型システムは、ジャグ配列の概念をサポートしていないため、パブリック メソッドで `IVector<Platform::Array<T>>` を戻り値またはメソッド パラメーターとして使用することはできません。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、`IVector<IVector<T>^>` を使用します。  
  
## ArrayReference 使用による、データ コピーの回避  
 データが ABI を介して [Platform::Array](../cppcx/platform-array-class.md) に渡されており、最終的にはそのデータを C スタイル配列で処理して効率性を追求するシナリオでは、[Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) を使用して、不要なコピー操作を回避できます。`Platform::Array` を受け取るパラメーターに引数として [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) が渡されると、`ArrayReference` は、そのデータを指定された C スタイル配列に直接格納します。`ArrayReference` にソース データへのロック オンがないため、呼び出しが完了する前に別のスレッドでそのデータが変更されるかまたは削除された場合、結果は不確定になることに注意してください。  
  
 次のコード スニペットは、[DataReader](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.datareader.aspx) 操作の結果を `Platform::Array` にコピーする方法 \(通常のパターン\) と、`ArrayReference` を代わりに使用してデータを C スタイル配列に直接コピーする方法を示します。  
  
 [!code-cpp[cx_arrays#07](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.h#07)]  
  
## 配列をプロパティとして公開することを回避する方法  
 一般に、ref クラスで `Platform::Array` 型をプロパティとして公開することは避ける必要があります。これは、クライアント コードが単一要素にアクセスしようとしている場合でも、配列全体が返されるためです。 パブリック ref クラスでシーケンス コンテナーをプロパティとして公開する必要があるときは、[Windows::Foundation::IVector](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) の方が適切です。 プライベートまたは内部 API \(メタデータに発行されません\) では、[std::vector](../Topic/vector%20Class%201.md) などの標準 C\+\+ コンテナーの使用を検討してください。  
  
## 参照  
 [型システム](../cppcx/type-system-c-cx.md)   
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)
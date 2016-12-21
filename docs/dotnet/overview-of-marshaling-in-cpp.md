---
title: "C++ におけるマーシャリングの概要 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshaling"
  - "marshalling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ のサポート ライブラリ, マーシャリング"
  - "マーシャリング, マーシャリングの概要"
  - "Visual C++, マーシャリング"
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ におけるマーシャリングの概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

混合モードでは、ネイティブ型とマネージ型の間でデータをマーシャリングすることが必要な場合があります。  [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)] は、単純な方法でデータをマーシャリングして変換できるようにするためのマーシャリング ライブラリを導入しました。  
  
 マーシャリング ライブラリは、[marshal\_context クラス](../dotnet/marshal-context-class.md) ありでもなしでも使用できます。  一部の変換では、コンテキストが必要です。  他の変換は、[marshal\_as](../dotnet/marshal-as.md) 関数を使用して実装できます。  次の表は、現在サポートされている変換と、コンテキストが必要かどうか、含める必要があるマーシャリング ファイルを示しています。  
  
|変換前の型|変換後の型|マーシャリング メソッド|インクルード ファイル|  
|-----------|-----------|------------------|-----------------|  
|System::String^|const char\*|marshal\_context|marshal.h|  
|const char\*|System::String^|marshal\_as|marshal.h|  
|char\*|System::String^|marshal\_as|marshal.h|  
|System::String^|const wchar\_t\*|marshal\_context|marshal.h|  
|const wchar\_t \*|System::String^|marshal\_as|marshal.h|  
|wchar\_t\*|System::String^|marshal\_as|marshal.h|  
|System::IntPtr|HANDLE|marshal\_as|marshal\_windows.h|  
|HANDLE|System::IntPtr|marshal\_as|marshal\_windows.h|  
|System::String^|BSTR|marshal\_context|marshal\_windows.h|  
|BSTR|System::String^|marshal\_as|marshal.h|  
|System::String^|bstr\_t|marshal\_as|marshal\_windows.h|  
|bstr\_t|System::String^|marshal\_as|marshal\_windows.h|  
|System::String^|std::string|marshal\_as|marshal\_cppstd.h|  
|std::string|System::String^|marshal\_as|marshal\_cppstd.h|  
|System::String^|std::wstring|marshal\_as|marshal\_cppstd.h|  
|std::wstring|System::String^|marshal\_as|marshal\_cppstd.h|  
|System::String^|CStringT\<char\>|marshal\_as|marshal\_atl.h|  
|CStringT\<char\>|System::String^|marshal\_as|marshal\_atl.h|  
|System::String^|CStringT\<wchar\_t\>|marshal\_as|marshal\_atl.h|  
|CStringT\<wchar\_t\>|System::String^|marshal\_as|marshal\_atl.h|  
|System::String^|CComBSTR|marshal\_as|marshal\_atl.h|  
|CComBSTR|System::String^|marshal\_as|marshal\_atl.h|  
  
 マーシャリングにコンテキストが必要なのは、マネージ データ型からネイティブ データ型にマーシャリングし、変換先のネイティブ型に自動クリーンアップ用のデストラクターがない場合のみです。  マーシャリング コンテキストは、デストラクターの中で割り当てられているネイティブ データ型を破棄します。  したがって、コンテキストを必要とする変換は、コンテキストが削除されるまでしか有効ではありません。  マーシャリングされた値を保存するには、独自の変数に値をコピーする必要があります。  
  
> [!NOTE]
>  文字列に `NULL` が埋め込まれている場合、文字列のマーシャリング結果は保証されません。  埋め込まれた `NULL` により、文字列が切り詰められたり残されたりする場合があります。  
  
 マーシャリング ライブラリ ヘッダーは、インクルード ディレクトリの msclr サブディレクトリにあります。  次の例では、インクルード ヘッダー宣言で msclr ディレクトリをインクルードする方法を示しています。  
  
 `#include "msclr\marshal_cppstd.h"`  
  
 マーシャリング ライブラリは、独自のマーシャリング型を追加できるように拡張できます。  マーシャリング ライブラリの拡張の詳細については、「[方法: マーシャリング ライブラリを拡張する](../dotnet/how-to-extend-the-marshaling-library.md)」を参照してください。  
  
 以前のバージョンでは、[プラットフォーム呼び出し](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md)を使用してデータをマーシャリングできました。  `PInvoke` の詳細については、「[マネージ コードからのネイティブ関数の呼び出し](../dotnet/calling-native-functions-from-managed-code.md)」を参照してください。  
  
## 参照  
 [C\+\+ のサポート ライブラリ](../dotnet/cpp-support-library.md)   
 [方法: マーシャリング ライブラリを拡張する](../dotnet/how-to-extend-the-marshaling-library.md)
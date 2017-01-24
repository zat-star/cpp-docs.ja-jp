---
title: "C++ での明示的な PInvoke (DllImport 属性) の使用方法  | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 相互運用機能, プラットフォーム呼び出し"
  - "データ マーシャリング [C++], プラットフォーム呼び出し"
  - "相互運用 [C++], プラットフォーム呼び出し"
  - "マーシャリング [C++], プラットフォーム呼び出し"
  - "プラットフォーム呼び出し [C++], マーシャリング (C++ の)"
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ での明示的な PInvoke (DllImport 属性) の使用方法 
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.NET Framework では、明示的なプラットフォーム呼び出し \(PInvoke\) 機能に、マネージ アプリケーションが DLL 内部にパッケージ化されているアンマネージ関数を呼び出すことができるようにする `Dllimport` 属性を備えています。  明示的な PInvoke は、アンマネージ API が DLL としてパッケージ化され、ソース コードが利用できない場合に必要です。  たとえば、Win32 関数の呼び出しには、PInvoke が必要です。  それ以外の場合、暗黙の P{Invoke を使用します。詳細については、「[C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。  
  
 PInvoke を機能させるには、<xref:System.Runtime.InteropServices.DllImportAttribute> を使用します。  この属性は、その最初の引数として DLL 名を使用し、使用する各 DLL エントリ ポイントの関数宣言の前に置かれます。  関数のシグネチャは、DLL によってエクスポートされた関数名に一致する必要があります \(ただし、型変換によっては、マネージ型を使用して `DllImport` 宣言を定義することで、暗黙的に実行できるものもあります\)。  
  
 その結果、これは、必要な遷移コード \(または、サンク\) と単純データ変換を含む各ネイティブ DLL 関数のマネージ エントリ ポイントになります。  その後、マネージ関数は、これらのエントリ ポイントを介して DLL を呼び出します。  PInvoke の結果モジュールに挿入されたコードは、完全に管理されており、明示的な PInvoke は、**\/clr**、**\/clr:pure**、**\/clr:safe** コンパイルでサポートされます。  詳細については、「[純粋なコードと検証可能なコード](../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。  
  
## このセクションの内容  
  
-   [マネージ コードからのネイティブ関数の呼び出し](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [方法: PInvoke を使用してマネージ コードからネイティブ DLL を呼び出す](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [方法: PInvoke を使用して文字列をマーシャリングする](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [方法: PInvoke を使用して構造体をマーシャリングする](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [方法: PInvoke を使用して配列をマーシャリングする](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [方法: PInvoke を使用して関数ポインターをマーシャリングする](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [方法: PInvoke を使用して埋め込みポインターをマーシャリングする](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## 参照  
 [マネージ コードからのネイティブ関数の呼び出し](../dotnet/calling-native-functions-from-managed-code.md)
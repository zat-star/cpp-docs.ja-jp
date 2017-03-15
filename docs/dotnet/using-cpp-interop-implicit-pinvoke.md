---
title: "C++ Interop (暗黙の PInvoke) の使用 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - ".NET [C++], 移植 (C++ ネイティブを)"
  - "blittable 型 [C++]"
  - "C++ COM 相互運用機能"
  - "C++ 相互運用機能"
  - "C++, 相互運用"
  - "COM インターフェイス [C++]"
  - "データ マーシャリング [C++], C++ 相互運用機能"
  - "例 [C++], 相互運用性"
  - "暗黙のプラットフォーム呼び出し"
  - "相互運用 [C++], 機能"
  - "相互運用性 [C++]"
  - "相互運用性 [C++], 暗黙の PInvoke"
  - "マーシャリング [C++], C++ 相互運用機能"
  - "プラットフォーム呼び出し [C++], 例"
  - "プラットフォーム呼び出し [C++], implicit"
  - "移植 [C++], C++ ネイティブを .NET に"
  - "型 [C++], blittable"
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ Interop (暗黙の PInvoke) の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

他の .NET 言語とは異なり、Visual C\+\+ には相互運用性サポートが備えられています。相互運用性サポートを使用すると、[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md) プラグマにより、マネージ コードとアンマネージ コードは同じアプリケーション内、また同じファイルでも共存できるようになります。  これにより、Visual C\+\+ 開発者は、他のアプリケーションの動作を妨げることなく、既存の Visual C\+\+ アプリケーションに .NET 機能を統合できます。  
  
 また、[dllexport、dllimport](../cpp/dllexport-dllimport.md) を使用して、マネージ コンパイル単位からアンマネージ関数を呼び出すこともできます。  
  
 関数パラメーターのマーシャリング方法を指定したり、DllImportAttribute を明示的に呼び出す際に指定できるその他の詳細設定を行ったりする必要がない場合は、暗黙の PInvoke を使用すると便利です。  
  
 Visual C\+\+ では、マネージ関数とアンマネージ関数を相互運用するために 2 つの方法があります。  
  
-   [C\+\+ での明示的な PInvoke \(DllImport 属性\) の使用方法 ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
 明示的な PInvoke は、.NET Framework でサポートされており、ほとんどの .NET 言語で使用できます。  ただし、その名前からわかるように、C\+\+ Interop は Visual C\+\+ 固有の機能です。  
  
## C\+\+ Interop  
 明示的な PInvoke よりも C\+\+ Interop を使用することをお勧めします。C\+\+ Interop は、より優れたタイプセーフを提供し、通常、実装も容易で、アンマネージ API が変更された場合もより柔軟に対処できるからです。また、明示的な PInvoke では不可能なパフォーマンスの向上も実現できます。  ただし、アンマネージ ソース コードが利用できない場合や、**\/clr:safe** を指定してコンパイルするときは、C\+\+ Interop は使用できません。詳細については、「[純粋なコードと検証可能なコード](../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。  
  
## C\+\+ COM Interop  
 Visual C\+\+ がサポートしている相互運用機能は、COM コンポーネントとの相互運用性において、他の .NET 言語に比べ特に優れた効果を発揮します。  データ型のサポートに制限が存在したり、全 COM インターフェイスのすべてのメンバーの公開が義務付けられたりするなどの、.NET Framework [Tlbimp.exe \(タイプ ライブラリ インポーター\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md) の制限にとらわれることなく、C\+\+ Interop では、COM コンポーネントに自由にアクセスでき、独立した相互運用機能アセンブリは必要ありません。  詳細については、「[Using COM from .NET](http://msdn.microsoft.com/ja-jp/03976661-6278-4227-a6c1-3b3315502c15)」を参照してください。  
  
## blittable 型  
 シンプルな組み込み型を使用するアンマネージ API については \(「[Blittable 型と非 Blittable 型](../Topic/Blittable%20and%20Non-Blittable%20Types.md)」を参照\)、メモリ内に同じデータ型表現があるため、特別なコーディングは必要ありません。ただし、複雑なデータ型については、明示的なデータ マーシャリングが必要です。  例については、「[方法: PInvoke を使用してマネージ コードからネイティブ DLL を呼び出す](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)」を参照してください。  
  
## 使用例  
  
```  
// vcmcppv2_impl_dllimp.cpp  
// compile with: /clr:pure user32.lib  
using namespace System::Runtime::InteropServices;  
  
// Implicit DLLImport specifying calling convention  
extern "C" int __stdcall MessageBeep(int);  
  
// explicit DLLImport needed here to use P/Invoke marshalling because  
// System::String ^ is not the type of the first parameter to printf  
[DllImport("msvcrt.dll", EntryPoint = "printf", CallingConvention = CallingConvention::Cdecl,  CharSet = CharSet::Ansi)]  
// or just  
// [DllImport("msvcrt.dll")]  
int printf(System::String ^, ...);   
  
int main() {  
   // (string literals are System::String by default)  
   printf("Begin beep\n");  
   MessageBeep(100000);  
   printf("Done\n");  
}  
```  
  
  **Begin beep**  
**Done**   
## このセクションの内容  
  
-   [方法: C\+\+ Interop を使用して ANSI 文字列をマーシャリングする](../Topic/How%20to:%20Marshal%20ANSI%20Strings%20Using%20C++%20Interop.md)  
  
-   [方法: C\+\+ Interop を使用して Unicode 文字列をマーシャリングする](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [方法: C\+\+ Interop を使用して COM 文字列をマーシャリングする](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
-   [方法: C\+\+ Interop を使用して構造体をマーシャリングする](../dotnet/how-to-marshal-structures-using-cpp-interop.md)  
  
-   [方法: C\+\+ Interop を使用して配列をマーシャリングする](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)  
  
-   [方法: C\+\+ Interop を使用してコールバックおよびデリゲートをマーシャリングする](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
-   [方法: C\+\+ Interop を使用して埋め込みポインターをマーシャリングする](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)  
  
-   [方法: System::String の文字にアクセスする](../dotnet/how-to-access-characters-in-a-system-string.md)  
  
-   [方法: char \* 文字列を System::Byte 配列に変換する](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)  
  
-   [方法: System::String を wchar\_t\* または char\* に変換する](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)  
  
-   [方法: System::String を標準文字列に変換する](../dotnet/how-to-convert-system-string-to-standard-string.md)  
  
-   [方法: 標準文字列を System::String に変換する](../dotnet/how-to-convert-standard-string-to-system-string.md)  
  
-   [方法 : バイト配列へのポインターを取得する](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)  
  
-   [方法: アンマネージ リソースをバイト配列に読み込む](../Topic/How%20to:%20Load%20Unmanaged%20Resources%20into%20a%20Byte%20Array.md)  
  
-   [方法: ネイティブ関数の参照クラスを変更する](../Topic/How%20to:%20Modify%20Reference%20Class%20in%20a%20Native%20Function.md)  
  
-   [方法: イメージがネイティブであるか CLR であるかを確認する](../Topic/How%20to:%20Determine%20if%20an%20Image%20is%20Native%20or%20CLR.md)  
  
-   [方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加する](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)  
  
-   [方法: 値型への参照をネイティブ型で保持する](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)  
  
-   [方法: アンマネージ メモリ内にオブジェクト参照を保持する](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)  
  
-   [方法: Detect \/clr コンパイルを検出する](../dotnet/how-to-detect-clr-compilation.md)  
  
-   [方法: System::Guid と \_GUID の間で変換を行う](../Topic/How%20to:%20Convert%20Between%20System::Guid%20and%20_GUID.md)  
  
-   [方法: out パラメーターを指定する](../dotnet/how-to-specify-an-out-parameter.md)  
  
-   [方法: \/clr コンパイルでネイティブ型を使用する](../Topic/How%20to:%20Use%20a%20Native%20Type%20in%20a%20-clr%20Compilation.md)  
  
-   [方法: ネイティブ型のハンドルを宣言する](../dotnet/how-to-declare-handles-in-native-types.md)  
  
-   [方法: ネイティブ クラスを C\# で使用できるようにラップする](../Topic/How%20to:%20Wrap%20Native%20Class%20for%20Use%20by%20C%23.md)  
  
 相互運用シナリオでのデリゲートの使用については、[delegate](../windows/delegate-cpp-component-extensions.md) のトピックを参照してください。  
  
## 参照  
 [マネージ コードからのネイティブ関数の呼び出し](../dotnet/calling-native-functions-from-managed-code.md)
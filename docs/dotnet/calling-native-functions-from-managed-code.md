---
title: "マネージからネイティブ関数を呼び出すコード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- native functions called from managed code [C++]
- managed code [C++], interoperability
- platform invoke [C++], interoperability
- interoperabiliy [C++], calling native functions from managed code
- calling native functions from managed code
- interop [C++], calling native functions from managed code
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 159b80fcc015db2999309fe99e9617f7dcd409ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="calling-native-functions-from-managed-code"></a>マネージ コードからのネイティブ関数の呼び出し
共通言語ランタイムにはプラットフォーム呼び出しサービス (PInvoke: Platform Invocation Services) が用意されており、マネージ コードでネイティブなダイナミック リンク ライブラリ (DLL : Dynamic Link Library) の C スタイルの関数を呼び出すことができます。 COM とランタイムの相互運用と、"It Just Works (そのままで動く)" つまり IJW 機構のどちらにも、同じデータ マーシャリングが使用されています。  
  
 詳細については次を参照してください:  
  
-   [C++ での明示的な PInvoke (DllImport 属性) の使用方法](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
-   [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [詳しく見てプラットフォーム呼び出し](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
  
 このセクションのサンプルで、`PInvoke` の使い方を示します。 `PInvoke` を使用すると、マーシャリング情報を手続き的なコードで書く代わりに属性として宣言できるため、データ マーシャリングを簡単にカスタマイズできます。  
  
> [!NOTE]
>  マーシャリング ライブラリにより、最適化された方法でネイティブ環境とマネージ環境との間でデータ変換を行うことができるようになります。 参照してください[概要の C++ におけるマーシャ リング](../dotnet/overview-of-marshaling-in-cpp.md)マーシャ リング ライブラリの詳細についてはします。 マーシャリング ライブラリは関数には使用できず、データにしか使用できません。  
  
## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke と DllImport 属性  
 次の例は、Visual C++ プログラムで `PInvoke` を使用する方法を示しています。 ネイティブ関数 puts が msvcrt.dll で定義されています。 DllImport 属性は puts の宣言に使用されます。  
  
```  
// platform_invocation_services.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[DllImport("msvcrt", CharSet=CharSet::Ansi)]  
extern "C" int puts(String ^);  
  
int main() {  
   String ^ pStr = "Hello World!";  
   puts(pStr);  
}  
```  
  
 次の例は上のサンプルと同じものですが、IJW を使用しています。  
  
```  
// platform_invocation_services_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#include <stdio.h>  
  
int main() {  
   String ^ pStr = "Hello World!";  
   char* pChars = (char*)Marshal::StringToHGlobalAnsi(pStr).ToPointer();   
   puts(pChars);  
  
   Marshal::FreeHGlobal((IntPtr)pChars);  
}  
```  
  
### <a name="advantages-of-ijw"></a>IJW の長所  
  
-   プログラムで使用するアンマネージ API のために `DLLImport` 属性を宣言する必要がありません。 ヘッダー ファイルをインクルードし、インポート ライブラリをリンクするだけです。  
  
-   IJW 機構の方が多少高速です。たとえば、データ項目の固定またはコピーは開発者が明示的に行うため、IJW スタブでその必要性をチェックする必要はありません。  
  
-   パフォーマンスの問題が明確になります。 この例では、Unicode 文字列から ANSI 文字列に変換しており、それに伴うメモリの割り当てと解放も行っています。 IJW でコードを書けば、`_putws` を呼び出し、`PtrToStringChars` を使用した方がパフォーマンスが良くなることがわかります。  
  
-   同じデータを使用して複数のアンマネージ API を呼び出す場合は、データを 1 回マーシャリングし、マーシャリングしたコピーを渡す方が毎回マーシャリングするよりも効率的です。  
  
### <a name="disadvantages-of-ijw"></a>IJW の短所  
  
-   マーシャリングは、属性ではなくコードに明示的に指定する必要があります (多くの場合、属性には適切な既定値があります)。  
  
-   マーシャリング コードがインラインであるため、アプリケーション ロジックのフローが途切れやすくなります。  
  
-   API の明示的なマーシャリングでは、32 ビットから 64 ビットへの変換のため、`IntPtr` 型が返されます。そのため、さらに `ToPointer` を呼び出す必要があります。  
  
 C++ によって公開された特定のメソッドの方が、ある程度複雑になりますが、わかりやすく効率的です。  
  
 アプリケーションで主にアンマネージ データ型を使用する場合、または .NET Framework API よりもアンマネージ API を多く呼び出す場合は、IJW 機能の使用をお勧めします。 アプリケーションの大部分でマネージ コードを使用し、ときどきアンマネージ API を呼び出す程度であれば、どちらを選択しても大きな違いはありません。  
  
## <a name="pinvoke-with-windows-apis"></a>PInvoke と Windows API  
 PInvoke は、Windows の関数を呼び出すときに便利です。  
  
 次の例では、Visual C++ プログラムと Win32 API に属する MessageBox 関数との相互運用を示します。  
  
```  
// platform_invocation_services_4.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
typedef void* HWND;  
[DllImport("user32", CharSet=CharSet::Ansi)]  
extern "C" int MessageBox(HWND hWnd, String ^ pText, String ^ pCaption, unsigned int uType);  
  
int main() {  
   String ^ pText = "Hello World! ";  
   String ^ pCaption = "PInvoke Test";  
   MessageBox(0, pText, pCaption, 0);  
}  
```  
  
 出力は「PInvoke Test」というタイトルのメッセージ ボックスで、「Hello World!」というテキストが表示されています。  
  
 PInvoke は、DLL から関数を検索するとき、マーシャリング情報も使用します。 user32.dll には実際は MessageBox 関数はありませんが、CharSet=CharSet::Ansi により、PInvoke は Unicode バージョンの MessageBoxW ではなく ANSI バージョンの MessageBoxA を使用できます。 一般に、Unicode バージョンのアンマネージ API を使用することをお勧めします。これは、.NET Framework の文字列オブジェクトのネイティブな形式である Unicode を ANSI に変換するオーバーヘッドがないためです。  
  
## <a name="when-not-to-use-pinvoke"></a>PInvoke の使用が適さないケース  
 PInvoke は、DLL に属するすべての C スタイルの関数に適しているわけではありません。 たとえば、次のように宣言された mylib.dll の MakeSpecial 関数について考えてみます。  
  
 `char * MakeSpecial(char * pszString);`  
  
 Visual C++ アプリケーションで PInvoke を使用する場合、次のようなコードになります。  
  
 `[DllImport("mylib")]`  
  
 `extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);`  
  
 ここで問題なのは、MakeSpecial によって返されるアンマネージ文字列のメモリを削除できないことです。 PInvoke によって呼び出された他の関数は、ユーザーによるメモリ解放の必要のない内部バッファーへのポインターを返します。 このケースでは、IJW 機能の方が適しているのは明らかです。  
  
## <a name="limitations-of-pinvoke"></a>PInvoke の制限  
 パラメーターとして使用したものと同じ正確なポインターをネイティブ関数から返すことはできません。 PInvoke によってそれにマーシャリングされたポインターをネイティブ関数が返す場合、メモリが破損したり例外が発生したりすることがあります。  
  
```  
__declspec(dllexport)  
char* fstringA(char* param) {  
   return param;  
}  
```  
  
 次の例はこの問題を示しています。プログラムが正確な出力を与えるように見える場合でも、その出力は既に解放されたメモリから行われています。  
  
```  
// platform_invocation_services_5.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
#include <limits.h>  
  
ref struct MyPInvokeWrap {  
public:  
   [ DllImport("user32.dll", EntryPoint = "CharLower", CharSet = CharSet::Ansi) ]  
   static String^ CharLower([In, Out] String ^);  
};  
  
int main() {  
   String ^ strout = "AabCc";  
   Console::WriteLine(strout);  
   strout = MyPInvokeWrap::CharLower(strout);  
   Console::WriteLine(strout);  
}  
```  
  
## <a name="marshaling-arguments"></a>引数のマーシャリング  
 `PInvoke` を使用する場合、マネージ型と C++ のネイティブなプリミティブ型が同じフォームを持っていれば、マーシャリングの必要はありません。 たとえば、Int32 と int、または Double と double との間では、マーシャリングは不要です。  
  
 しかし、フォームが異なる場合はマーシャリングが必要です。 フォームが異なる型とは、char、string、struct などの型です。 次の表は、マーシャラーが各型に使用するマップを示します。  
  
|wtypes.h|Visual C++|/clr を指定した Visual C++|共通言語ランタイム|  
|--------------|------------------|-----------------------------|-----------------------------|  
|HANDLE|void*|void*|IntPtr、UIntPtr|  
|BYTE|unsigned char|unsigned char|Byte|  
|SHORT|short|short|Int16|  
|WORD|unsigned short|unsigned short|UInt16|  
|INT|int|int|Int32|  
|UINT|unsigned int|unsigned int|UInt32|  
|LONG|long|long|Int32|  
|BOOL|long|bool|ブール型|  
|DWORD|unsigned long|unsigned long|UInt32|  
|ULONG|unsigned long|unsigned long|UInt32|  
|CHAR|char|char|Char|  
|LPCSTR|char*|String ^ [in], StringBuilder ^ [in, out]|String ^ [in], StringBuilder ^ [in, out]|  
|LPCSTR|const char*|String ^|String|  
|LPWSTR|wchar_t*|String ^ [in], StringBuilder ^ [in, out]|String ^ [in], StringBuilder ^ [in, out]|  
|LPCWSTR|const wchar_t *|String ^|String|  
|FLOAT|float|float|Single|  
|DOUBLE|double|double|倍精度浮動小数点型|  
  
 マーシャラーは、ランタイム ヒープに割り当てられたメモリのアドレスをアンマネージ関数に渡す場合、メモリを自動的に固定します。 メモリの固定によって、割り当てられたメモリ ブロックをガベージ コレクターが圧縮時に移動することはなくなります。  
  
 このトピックの最初に示した例では、DllImport の CharSet パラメーターでマネージ型の String をマーシャリングする方法を示しています。この場合、マネージ型の String をネイティブ側で使用できるように ANSI 文字列にマーシャリングしています。  
  
 ネイティブ関数で使用する各引数のマーシャリング情報については、MarshalAs 属性で指定できます。 String * 引数をマーシャリングする場合、BStr、ANSIBStr、TBStr、LPStr、LPWStr、および LPTStr などの選択肢があります。 既定値は LPStr です。  
  
 この例では、文字列を 2 バイトの Unicode 文字列 LPWStr としてマーシャリングしています。 出力は、Hello World の最初の文字です。 マーシャ リングされた文字列の 2 番目のバイトが null であり、格納するための文字列の末尾を示すマーカーとして解釈します。  
  
```  
// platform_invocation_services_3.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[DllImport("msvcrt", EntryPoint="puts")]  
extern "C" int puts([MarshalAs(UnmanagedType::LPWStr)] String ^);  
  
int main() {  
   String ^ pStr = "Hello World!";  
   puts(pStr);  
}  
```  
  
 MarshalAs 属性は System::Runtime::InteropServices 名前空間にあります。 この属性は、配列などのほかのデータ型にも使用できます。  
  
 このトピックで既に述べたように、マーシャリング ライブラリにより、最適化された新しい方法でネイティブ環境とマネージ環境との間でデータ変換を行うことができます。 詳細については、次を参照してください。[概要の C++ におけるマーシャ リング](../dotnet/overview-of-marshaling-in-cpp.md)です。  
  
## <a name="performance-considerations"></a>パフォーマンスに関する考慮事項  
 PInvoke は、1 回の呼び出しで 10 ～ 30 個分の x86 命令のオーバーヘッドを要します。 この固定コストのほかに、マーシャリングによってオーバーヘッドが発生します。 マネージ コードとアンマネージ コードの間で同じ表現である blittable 型については、マーシャリングのコストはかかりません。 たとえば、int と Int32 との間の変換にコストは不要です。  
  
 パフォーマンスを上げるには、マーシャリングするデータが少ない PInvoke 呼び出しを何度も行うより、できるだけ多くのデータを少ない PInvoke 呼び出しでマーシャリングすることをお勧めします。  
  
## <a name="see-also"></a>参照  
 [ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)
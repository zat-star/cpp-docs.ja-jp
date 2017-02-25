---
title: "CLR 列挙型 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "enum class キーワード [C++]"
  - "enum struct キーワード [C++]"
  - "スコープ, CLR enum の"
ms.assetid: 4541d952-97bb-4e35-a7f8-d14f5f6a6606
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CLR 列挙型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

列挙型 \(Enum\) の宣言と動作は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から変更されています。  
  
 マネージ拡張では、列挙型 \(Enum\) の宣言の前部に `__value` キーワードを使用します。  これは、`System::ValueType` から派生して類似した機能を備える CLR の列挙型 \(Enum\) をネイティブな列挙型 \(Enum\) と区別するためです。  たとえば、次のようになります。  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};  
```  
  
 新しい構文では、ネイティブな列挙型 \(Enum\) と CLR の列挙型 \(Enum\) の区別の問題は、値型のルートではなく、CLR の列挙型 \(Enum\) のクラスの性質を強調することで解消しています。  これにより、`__value` キーワードは破棄され、`enum class` のスペース区切りキーワード ペアに置き換えられています。  これが、参照クラスの宣言、値クラスの宣言、およびインターフェイス クラスの宣言に対応するキーワード ペアを提供しています。  
  
```  
enum class ec;  
value class vc;  
ref class rc;  
interface class ic;  
```  
  
 次に、新しい構文における列挙体ペアの `e1` と `e2` の変換を示します。  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 このように構文が多少変わったこと以外に、CLR 列挙型の動作もいくつか変更されています。  
  
-   CLR 列挙型の事前の宣言はサポートされなくなりました。  マップは行われず、  コンパイル時のエラーとして示されます。  
  
```  
__value enum status; // Managed Extensions: ok  
enum class status;   // new syntax: error  
```  
  
-   組み込みの数値型と `Object` クラス階層構造の間でのオーバーロードの解決は、2 つの言語バージョン間に戻されました。  その副次効果として、CLR 列挙型が暗黙のうちに数値型に変換されることはなくなりました。  
  
-   マネージ拡張の場合とは異なり、新しい構文では CLR 列挙型は独自のスコープを維持します。  以前のバージョンでは、列挙子はその列挙型を含んでいるスコープ内で参照できました。  今後、列挙子は対応する列挙型のスコープ内にカプセル化されます。  
  
## CLR の列挙型 \(Enum\) はオブジェクトの一種  
 次のコードがあるとします。  
  
```  
__value enum status { fail, pass };  
  
void f( Object* ){ Console::WriteLine("f(Object)\n"); }  
void f( int ){ Console::WriteLine("f(int)\n"); }  
  
int main()  
{  
   status rslt = fail;  
  
   f( rslt ); // which f is invoked?  
}  
```  
  
 一般にネイティブな C\+\+ プログラマの場合、呼び出されたオーバーロード `f()` のインスタンスはどれであるかという質問に対する答えは、`f(int)` のインスタンスであるとなります。  列挙型 \(Enum\) は整数の記号定数で、このケースでは優先される標準の整数の上位変換に参加します。実際、マネージ拡張では、これは呼び出しが解決されるインスタンスでした。  このため、ネイティブな C\+\+ フレームで使用する場合ではなく、`Enum` が `Object` から間接的に派生する、既存の BCL \(基本クラス ライブラリ\) フレームワークとの対話に列挙型 \(Enum\) を必要とした場合に驚くことが多数あります。  [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] 言語デザインでは、呼び出される `f()` のインスタンスは `f(Object^)` のインスタンスです。  
  
 これを強制するために、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] は、CLR の列挙型と数値型の暗黙の型変換をサポートしていません。  したがって、CLR の列挙型のオブジェクトを数値型に割り当てるには明示的なキャストが必要となります。  例を次に示します。  
  
```  
void f( int );  
```  
  
 マネージ拡張では、オーバーロードされていないメソッドとして、次の呼び出しが認められています。  
  
```  
f( rslt ); // ok: Managed Extensions; error: new syntax  
```  
  
 `rslt` に格納される値は、暗黙的に整数値に変換されます。  [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では、この呼び出しはコンパイル エラーになります。  この変換を正しく行うには、次のように変換演算子を挿入する必要があります。  
  
```  
f( safe_cast<int>( rslt )); // ok: new syntax  
```  
  
## CLR の列挙型のスコープ  
 C 言語と C\+\+ 言語の相違の 1 つに、C\+\+ 言語では構造体ファミリにスコープが追加されたことがあります。  C 言語では、構造体は単なるデータの集約で、インターフェイスまたは関連スコープのいずれもサポートしていませんでした。  これは当時としてはきわめて急進的な変更で、C 言語から移行した新しい C\+\+ ユーザー間で論争の的となりました。  ネイティブな列挙型 \(Enum\) と CLR の列挙型 \(Enum\) の関係に似ています。  
  
 マネージ拡張では、ネイティブな列挙型 \(Enum\) のスコープの欠落をシミュレートするために、CLR の列挙型 \(Enum\) の列挙子に弱く挿入された名前を定義することを試みました。  これは失敗に終わりました。  問題は、これにより列挙子がグローバル名前空間に流出してしまい、名前の衝突の管理が困難になることでした。  新しい構文では、別の CLR 言語に準拠して、CLR の列挙型 \(Enum\) でスコープをサポートしています。  
  
 このため、新しい構文では、CLR の列挙型 \(Enum\) の列挙子を修飾せずに使用することは認められません。  実際の例を見てみましょう。  
  
```  
// Managed Extensions supporting weak injection  
__gc class XDCMake {  
public:  
   __value enum _recognizerEnum {   
      UNDEFINED,  
      OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6,  
   };  
  
   ListDictionary* optionList;  
   ListDictionary* itagList;  
  
   XDCMake() {  
      optionList = new ListDictionary;  
  
      // here are the problems …  
      optionList->Add(S"?", __box(OPTION_USAGE)); // (1)  
      optionList->Add(S"help", __box(OPTION_USAGE)); // (2)  
  
      itagList = new ListDictionary;  
      itagList->Add(S"returns",   
         __box(XDC0004_WRN_XML_LOAD_FAILURE)); // (3)  
   }  
};  
```  
  
 ソース コードをコンパイルするには、修飾せずに使用されている 3 つの列挙子の名前 \(`(1)`、`(2)`、`(3)`\) を変換時に修飾する必要があります。  次に、元のソース コードの正しい変換を示します。  
  
```  
ref class XDCMake {  
public:  
   enum class _recognizerEnum {  
      UNDEFINED, OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6  
   };  
  
   ListDictionary^ optionList;  
   ListDictionary^ itagList;  
  
   XDCMake() {  
      optionList = gcnew ListDictionary;  
      optionList->Add("?",_recognizerEnum::OPTION_USAGE); // (1)  
      optionList->Add("help",_recognizerEnum::OPTION_USAGE); //(2)  
      itagList = gcnew ListDictionary;  
      itagList->Add( "returns",   
         _recognizerEnum::XDC0004_WRN_XML_LOAD_FAILURE); //(3)  
   }  
};  
```  
  
 これにより、ネイティブな列挙型 \(Enum\) と CLR の列挙型 \(Enum\) の間のデザイン戦略が変更されます。  [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では、CLR の列挙型 \(Enum\) の関連スコープが維持されるため、列挙型 \(Enum\) の宣言をクラスにカプセル化する必要も意味もありません。  この表現形式は、グローバル名の汚染問題を解決するために Bell Laboratories で cfront 2.0 のころに作成されました。  
  
 Bell Laboratories の Jerry Schwarz が新しい iostream ライブラリのオリジナルのベータ版をリリースしたとき、ライブラリに定義されているすべての関連列挙型 \(Enum\) をカプセル化せず、`read`、`write`、`append` などの一般的な列挙子によって既存のコードをほとんどコンパイルできないようにしました。  第 1 の解決方法は、`io_read``io_write`などのわかりやすい名前を、分解することです。第 2 の解決方法は、列挙型のスコープを追加することによって言語を変更できます。これは、当時、現実的ではありません。  中間的な解決方法は、クラスまたはクラス階層構造に列挙型 \(Enum\) をカプセル化することでした。この場合、列挙型 \(Enum\) のタグ名と列挙子が、外側のクラスを設定しました。つまり、列挙型 \(Enum\) をクラスに置いたのは、少なくとも本来は、哲学的な動機からではなく、グローバル名前空間の汚染問題に対する実際的な動機によるものでした。  
  
 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] の列挙型 \(Enum\) では、列挙型 \(Enum\) をクラス内にカプセル化する十分な利点はありません。  実際、`System` 名前空間を見ると、列挙型 \(Enum\)、クラス、およびインターフェイスのすべてが同じ宣言空間に存在しています。  
  
## 参照  
 [値型とその動作 \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [列挙型クラス](../windows/enum-class-cpp-component-extensions.md)
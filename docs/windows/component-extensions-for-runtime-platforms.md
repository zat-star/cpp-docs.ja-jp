---
title: "Component Extensions for Runtime Platforms | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "what's new [C++], keywords"
  - "what's new [C++], language features"
  - "Visual C++, keywords"
  - "keywords [C++]"
  - "Managed Extensions for C++, replacement syntax"
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
caps.latest.revision: 77
caps.handback.revision: 77
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Component Extensions for Runtime Platforms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ には、ランタイム プラットフォームに対するプログラミングに役立つ言語拡張が用意されています。  [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)]\) を使用することで、ネイティブ コードにコンパイルされる [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリやコンポーネントをプログラミングできます。  [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリを [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] の COM インターフェイスに対して直接プログラミングして作成する方法もありますが、[!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)] を使用すると、コンストラクターや例外など、最新の C\+\+ プログラミングの表現方法を使用できます。  .NET プラットフォームでマネージ実行環境での C\+\+ プログラミングを有効にするには、[!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] を使用します。  
  
 **2 つのランタイムに共通の拡張**  
  
 [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)] は [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] のサブセットです。  [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)] と [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] に共通の拡張では、対象が共通言語ランタイム \(CLR\) か [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]かに応じてセマンティクスが異なります。  アプリを [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]で動作するようにコンパイルする場合は **\/ZW** コンパイラ オプションを指定し、  CLR で動作するようにコンパイルする場合は **\/clr** コンパイラ オプションを指定します。  Visual Studio を使用してプロジェクトを作成すると、これらのスイッチが自動的に設定されます。  
  
 C\+\+ で [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリを作成する方法の詳細については、「[C\+\+ を使った Windows ランタイム アプリのためのロードマップ](http://msdn.microsoft.com/library/windows/apps/hh700360.aspx)」を参照してください。  
  
 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] は ISO\/ANSI C\+\+ 規格を拡張したものであり、Ecma [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] 規格で定義されています。  詳細については、「[C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)」を参照してください。  
  
## データ型のキーワード  
 言語拡張には、*集計キーワード*という、空白で区切られた 2 つのトークンで構成されるキーワードが含まれます。  これらのトークンは、単独で使用した場合と一緒に使用した場合で意味が異なることがあります。  たとえば、"ref" は通常の識別子であり、"class" はネイティブ クラスを宣言するキーワードです。  しかし、これらを組み合わせて `ref class` として使用した場合は、*ランタイム クラス*と呼ばれるエンティティを宣言する集計キーワードになります。  
  
 拡張には、*状況依存*のキーワードも含まれます。  キーワードが状況依存のキーワードとして扱われるかどうかは、キーワードを含むステートメントの種類と、そのステートメント内でのキーワードの配置で決まります。  たとえば、"property" というトークンは、識別子として使用されることもあれば、特殊なパブリック クラスのメンバーを宣言するために使用されることもあります。  
  
 次の表に、C\+\+ 言語拡張のキーワードの一覧を示します。  
  
|キーワード|状況依存|目的|参照|  
|-----------|----------|--------|--------|  
|`ref class`<br /><br /> `ref struct`|いいえ|クラスを宣言します。|[Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`value class`<br /><br /> `value struct`|いいえ|値クラスを宣言します。|[Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`interface class`<br /><br /> `interface struct`|いいえ|インターフェイスを宣言します。|[interface class](../windows/interface-class-cpp-component-extensions.md)|  
|`enum class`<br /><br /> `enum struct`|いいえ|列挙型を宣言します。|[列挙型クラス](../windows/enum-class-cpp-component-extensions.md)|  
|`property`|はい|プロパティを宣言します。|[property](../windows/property-cpp-component-extensions.md)|  
|`delegate`|はい|デリゲートを宣言します。|[delegate](../windows/delegate-cpp-component-extensions.md)|  
|`event`|はい|イベントを宣言します。|[event](../windows/event-cpp-component-extensions.md)|  
  
## オーバーライド指定子  
 次のキーワードは、派生のオーバーライド動作を修飾するために使用できます。  `new` キーワードは C\+\+ の拡張ではありませんが、追加のコンテキストで使用できるキーワードとしてこの一覧に含めてあります。  一部の指定子は、ネイティブのプログラミングに対しても有効です。  詳細については、「[方法: ネイティブ コンパイルでオーバーライド指定子を宣言する](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)」を参照してください。  
  
|キーワード|状況依存|目的|参照|  
|-----------|----------|--------|--------|  
|`abstract`|はい|関数またはクラスが抽象型であることを示します。|[abstract](../windows/abstract-cpp-component-extensions.md)|  
|`new`|いいえ|関数が基底クラスのバージョンのオーバーライドでないことを示します。|[new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|  
|`override`|はい|メソッドが基底クラスのバージョンのオーバーライドでなければならないことを示します。|[override](../windows/override-cpp-component-extensions.md)|  
|`sealed`|はい|クラスを基底クラスとして使用しないことを示します。|[sealed](../windows/sealed-cpp-component-extensions.md)|  
  
## ジェネリックのキーワード  
 ジェネリック型をサポートするために追加されたキーワードを次に示します。  詳細については、「[Generics](../windows/generics-cpp-component-extensions.md)」を参照してください。  
  
|キーワード|状況依存|目的|  
|-----------|----------|--------|  
|`generic`|いいえ|ジェネリック型を宣言します。|  
|`where`|はい|ジェネリック型パラメーターに適用される制約を指定します。|  
  
## その他のキーワード  
 C\+\+ 拡張に追加されたその他のキーワードを次に示します。  
  
|キーワード|状況依存|目的|参照|  
|-----------|----------|--------|--------|  
|`finally`|はい|例外処理の既定の動作を示します。|[Exception Handling](../windows/exception-handling-cpp-component-extensions.md)|  
|`for each, in`|いいえ|コレクションの要素を列挙します。|[for each、in](../dotnet/for-each-in.md)|  
|`gcnew`|いいえ|ガベージ コレクション ヒープに型を割り当てます。  `new` と `delete` の代わりに使用します。|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`ref new`|はい|[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]型を割り当てます。  `new` と `delete` の代わりに使用します。|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`initonly`|はい|宣言または静的コンストラクターでしかメンバーを初期化できないことを示します。|[initonly](../dotnet/initonly-cpp-cli.md)|  
|`literal`|はい|リテラル変数を作成します。|[literal](../windows/literal-cpp-component-extensions.md)|  
|`nullptr`|いいえ|ハンドルまたはポインターでオブジェクトを参照しないことを示します。|[nullptr](../windows/nullptr-cpp-component-extensions.md)|  
  
## テンプレートの構成要素  
 次の言語構成要素は、キーワードとしてではなく、テンプレートとして実装されています。  **\/ZW** コンパイラ オプションを指定した場合は `lang` 名前空間で定義され、  **\/clr** コンパイラ オプションを指定した場合は `cli` 名前空間で定義され、  
  
|キーワード|目的|参照|  
|-----------|--------|--------|  
|`array`|配列を宣言します。|[Arrays](../windows/arrays-cpp-component-extensions.md)|  
|`interior_ptr`|\(CLR のみ\) 参照型でデータを参照します。|[interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)|  
|`pin_ptr`|\(CLR のみ\) CLR 参照型を参照して、ガベージ コレクション システムを一時的に無効にします。|[pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md)|  
|`safe_cast`|ランタイム型の最適なキャスト方法を特定して実行します。|[safe\_cast](../windows/safe-cast-cpp-component-extensions.md)|  
|`typeid`|\(CLR のみ\) 指定した型またはオブジェクトを表す <xref:System.Type?displayProperty=fullName> オブジェクトを取得します。|[typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md)|  
  
## 宣言子  
 割り当てられたオブジェクトの有効期間と削除をランタイムで自動的に管理するように指定する型の宣言子を次に示します。  
  
|演算子|目的|参照|  
|---------|--------|--------|  
|`^`|オブジェクトを識別するハンドル \(使用できなくなったときに自動的に削除される [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] オブジェクトまたは CLR オブジェクトへのポインター\) を宣言します。|[オブジェクト演算子 \(^\) へのハンドル](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|  
|`%`|追跡参照 \(使用できなくなったときに自動的に削除される [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] オブジェクトまたは CLR オブジェクトへの参照\) を宣言します。|[Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md)|  
  
## その他の構成要素と関連トピック  
 ここでは、その他のプログラミング構成要素と CLR の関連トピックを示します。  
  
|トピック|説明|  
|----------|--------|  
|[\_\_identifier \(C\+\+\/CLI\)](../windows/identifier-cpp-cli.md)|\([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]および CLR\) キーワードを識別子として使用できるようにします。|  
|[Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|\([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]および CLR\) 関数で受け取ることができる引数の数を可変にします。|  
|[C\+\+ ネイティブ型と等価な .NET Framework ネイティブ型](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|C\+\+ の整数型の代わりに使用される CLR 型を示します。|  
|[appdomain](../Topic/appdomain.md) `__declspec` 修飾子|`__declspec` 修飾子は、appdomain ごとに静的変数とグローバル変数を必須にする修飾子です。|  
|[C\-Style Casts with \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)|C スタイル キャストがどのように解釈されるかについて説明します。|  
|[\_\_clrcall](../cpp/clrcall.md) 呼び出し規約|CLR 準拠の呼び出し規約を示します。|  
|`__cplusplus_cli`|[定義済みマクロ](../preprocessor/predefined-macros.md)|  
|[Custom Attributes](../windows/custom-attributes-cpp.md)|独自の CLR 属性を定義する方法について説明します。|  
|[Exception Handling](../windows/exception-handling-cpp-component-extensions.md)|例外処理の概要を示します。|  
|[Explicit Overrides](../windows/explicit-overrides-cpp-component-extensions.md)|メンバー関数で任意のメンバーをオーバーライドする方法を示します。|  
|[フレンド アセンブリ \(C\+\+\)](../dotnet/friend-assemblies-cpp.md)|クライアント アセンブリでアセンブリ コンポーネントのすべての型にアクセスする方法について説明します。|  
|[Boxing](../windows/boxing-cpp-component-extensions.md)|値型がボックス化される条件を示します。|  
|[Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|コンパイル時に型の特性を検出する方法について説明します。|  
|[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md) プラグマ|同じモジュールにマネージ関数とアンマネージ関数を共存させる方法を示します。|  
|[プロセス](../cpp/process.md) `__declspec` 修飾子|`__declspec` 修飾子は、process ごとに静的変数とグローバル変数を必須にする修飾子です。|  
|[リフレクション](../dotnet/reflection-cpp-cli.md)|CLR バージョンのランタイム型情報を示します。|  
|[String](../windows/string-cpp-component-extensions.md)|文字列リテラルから <xref:System.String> へのコンパイラによる変換について説明します。|  
|[Type Forwarding \(C\+\+\/CLI\)](../windows/type-forwarding-cpp-cli.md)|クライアント コードを再コンパイルしなくても済むように、出荷時のアセンブリの型を別のアセンブリに移動できるようにします。|  
|[User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md)|ユーザー定義の属性を示します。|  
|[\#using ディレクティブ](../preprocessor/hash-using-directive-cpp.md)|外部アセンブリをインポートします。|  
|[XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)|[\/doc \(ドキュメント コメントの処理\)](../build/reference/doc-process-documentation-comments-c-cpp.md) を使用した XML ベースのコード ドキュメントについて説明します|  
  
## 参照  
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [ネイティブと .NET の相互運用性](../Topic/Native%20and%20.NET%20Interoperability.md)
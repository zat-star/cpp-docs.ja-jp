---
title: "C++ 言語リファレンス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
f1_keywords: 
  - "c++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++, 言語リファレンス"
  - "言語リファレンス"
  - "言語リファレンス, Visual C++"
  - "Visual C++, 言語リファレンス"
ms.assetid: 4be9cacb-c862-4391-894a-3a118c9c93ce
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 言語リファレンス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このリファレンスでは、Microsoft Visual C\+\+ に実装されている C\+\+ プログラミング言語について説明します。  このリファレンスの構成は、Margaret Ellis と Bjarne Stroustrup の『The Annotated C\+\+ Reference Manual』と ANSI\/ISO C\+\+ 国際規格 \(ISO\/IEC FDIS 14882\) に基づいています。  C\+\+ 言語機能の Microsoft 固有実装が含まれます。  
  
 キーワードまたは演算子をすばやく見つけるには、次の表を参照してください。  
  
-   [C\+\+ のキーワード](../cpp/keywords-cpp.md)  
  
-   [C\+\+ Operators](../cpp/cpp-built-in-operators-precedence-and-associativity.md)  
  
## このセクションの内容  
 [構文規則](../cpp/lexical-conventions.md)  
 C\+\+ プログラムの基本的な構文の要素: トークン、コメント、演算子、キーワード、区切り記号、リテラル。  また、ファイルの変換、演算子の優先順位\/結合規則。  
  
 [基本的な概念](../cpp/basic-concepts-cpp.md)  
 スコープ、リンケージ、プログラムの起動と終了、ストレージ クラス、および型。  
  
 [標準変換](../cpp/standard-conversions.md)  
 組み込み型 \(基本型\) 間の型変換。  また、ポインター、参照、およびメンバーへのポインター型の間の算術変換および変換。  
  
 [演算子およびその優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)  
 C\+\+ 言語の演算子。  
  
 [式](../cpp/expressions-cpp.md)  
 式の型とセマンティクス、演算子の参照トピック、キャスト演算子、実行時の型情報。  
  
 [ラムダ式](../cpp/lambda-expressions-in-cpp.md)  
 暗黙的に関数オブジェクト クラスを定義し、そのクラス型の関数オブジェクトを生成するプログラミング手法。  
  
 [ステートメント](../cpp/statements-cpp.md)  
 式、NULL、複合、選択、イテレーション、ジャンプ、および宣言ステートメント。  
  
 [宣言](../misc/declarations.md)  
 ストレージ クラス指定子、関数定義、初期化、列挙体、クラス宣言、構造体宣言、および共用体宣言、および typedef 宣言。  また、インライン関数、定数のキーワード、名前空間。  
  
 [宣言子](http://msdn.microsoft.com/ja-jp/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838)  
 オブジェクト、型、または関数の名前を指定する宣言ステートメントの要素。  抽象宣言子、型名、初期化子、関数宣言と定義、配列、参照。  
  
 [クラス、構造体、および共用体](../Topic/Classes%20and%20Structs%20\(C++\).md)  
 クラス、構造体、および共用体の概要。  また、メンバー関数、データ メンバー、ビット フィールド、このポインター、入れ子になったクラス。  
  
 [派生クラス](../cpp/inheritance-cpp.md)  
 単一継承と多重継承、仮想関数、複数の基底クラス、抽象クラス、スコープ規則。  また、\_\_super および \_\_interface キーワード。  
  
 [メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)  
 クラス メンバーへのアクセスの制御: public、private、および protected キーワード。  friend 関数および friend クラス。  
  
 [特殊なメンバー関数](../misc/special-member-functions-cpp.md)  
 クラス型に固有の特殊な機能: コンストラクター、デストラクター、変換関数、代入演算子、operator new 関数と operator delete 関数。  
  
 [オーバーロード](../misc/overloading-cpp.md)  
 オーバーロード関数、宣言の一致、引数の一致。  また、オーバーロードされた演算子、演算子のオーバーロードの規則。  
  
 [例外処理](../cpp/exception-handling-in-visual-cpp.md)  
 例外処理ステートメントの記述に使用される C\+\+ 例外処理、構造化例外処理 \(SEH\)、キーワード。  
  
 [アサーションとユーザー指定のメッセージ](../cpp/assertion-and-user-supplied-messages-cpp.md)  
 `#error` ディレクティブ、`static_assert` キーワード、`assert` マクロ。  
  
 [テンプレート](../Topic/Templates%20\(C++\).md)  
 テンプレートの仕様、関数テンプレート、クラス テンプレート、typename キーワード、テンプレートと  マクロの比較、テンプレート、スマート ポインター。  
  
 [イベント処理](../cpp/event-handling.md)  
 イベントとイベント ハンドラーの宣言。  
  
 [Microsoft 固有の修飾子](../Topic/Microsoft-Specific%20Modifiers.md)  
 Microsoft C\+\+ 固有の修飾子。  メモリのアドレス指定、呼び出し規約、naked 関数、拡張ストレージ クラス属性 \(\_\_declspec\)、\_\_w64。  
  
 [インライン アセンブラー](../assembler/inline/inline-assembler.md)  
 \_\_asm ブロックでのアセンブリ言語と C\+\+ の使用。  
  
 [コンパイラの COM サポート](../Topic/Compiler%20COM%20Support.md)  
 COM 型をサポートするために使用する Microsoft 固有のクラスとグローバル関数への参照。  
  
 [Microsoft 拡張機能](../cpp/microsoft-extensions.md)  
 C\+\+ の Microsoft 拡張機能。  
  
 [非標準動作](../Topic/Nonstandard%20Behavior.md)  
 Visual C\+\+ コンパイラの非標準動作に関する情報。  
  
## 関連項目  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)  
 共通言語ランタイムを対象とするための Visual C\+\+ の使用に関するリファレンス資料。  
  
 [C\/C\+\+ ビルドのリファレンス](../Topic/C-C++%20Building%20Reference.md)  
 コンパイラ オプション、リンカー オプション、およびその他のビルド ツール。  
  
 [C\/C\+\+ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)  
 プラグマ、プリプロセッサ ディレクティブ、定義済みマクロ、およびプリプロセッサに関するリファレンス資料。  
  
 [Visual C\+\+ のライブラリ](http://msdn.microsoft.com/ja-jp/fec23c40-10c0-4857-9cdc-33a3b99b30ae)  
 Visual C\+\+ のさまざまなライブラリの参照のスタート ページへのリンクの一覧。  
  
## 参照  
 [C 言語リファレンス](../Topic/C%20Language%20Reference.md)
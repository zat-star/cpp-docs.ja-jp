---
title: "#if、#elif、#else、および #endif ディレクティブ (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#else"
  - "#endif"
  - "#if"
  - "#elif"
  - "Defined"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#elif ディレクティブ"
  - "#else ディレクティブ"
  - "#endif ディレクティブ"
  - "#if ディレクティブ"
  - "条件付きコンパイル, ディレクティブ"
  - "定義済みディレクティブ"
  - "elif ディレクティブ (#elif)"
  - "else ディレクティブ (#else)"
  - "endif ディレクティブ (#endif)"
  - "if ディレクティブ (#if)"
  - "プリプロセッサ, ディレクティブ"
ms.assetid: c77a175f-6ca8-47d4-8df9-7bac5943d01b
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #if、#elif、#else、および #endif ディレクティブ (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`#if` ディレクティブは、`#elif`、`#else`、および `#endif` ディレクティブと共にソース ファイルの各部分のコンパイルを制御します。  `#if` の後に記述した式がゼロ以外の値になる場合、`#if` ディレクティブの直後の一連の行が翻訳単位として保持されます。  
  
## 文法  
 *conditional*:  
 *if\-part elif\-parts* opt *else\-part*opt *endif\-line*  
  
 *if\-part* :  
 *if\-line text*  
  
 *if\-line*:  
 **\#if**  *constant\-expression*  
  
 **\#ifdef**  *identifier*  
  
 **\#ifndef**  *identifier*  
  
 *elif\-parts* :  
 *elif\-line text*  
  
 *elif\-parts elif\-line text*  
  
 *elif\-line* :  
 **\#elif**  *constant\-expression*  
  
 *else\-part* :  
 *else\-line text*  
  
 *else\-line* :  
 `#else`  
  
 *endif\-line* :  
 `#endif`  
  
 ソース ファイルの各 `#if` ディレクティブは `#endif` 終了ディレクティブと対応している必要があります。  `#if` ディレクティブと `#endif` ディレクティブの間に、`#elif` ディレクティブはいくつでも記述できますが、`#else` ディレクティブは 1 つしか記述できません。  `#else` ディレクティブ \(存在する場合\) は、`#endif` の前の最後のディレクティブである必要があります。  
  
 `#if`、`#elif`、`#else`、および `#endif` ディレクティブは、他の `#if` ディレクティブのテキスト部分に入れ子にできます。  入れ子になった `#else`、`#elif`、または `#endif` ディレクティブは、最も近い先行する `#if` ディレクティブに属します。  
  
 `#if` や **\#ifdef** など、すべての条件付きコンパイル ディレクティブは、ファイルの終わりの前にある `#endif` 終了ディレクティブと対になっている必要があります。なっていない場合は、エラー メッセージが生成されます。  条件付きコンパイル ディレクティブがインクルード ファイルに含まれている場合も同じ条件を満たす必要があります。つまり、インクルード ファイルの終わりに対になる条件付きコンパイル ディレクティブが必要です。  
  
 マクロの置き換えは、コマンド ラインの `#elif` コマンドの後で実行されるので、マクロの呼び出しは *constant\-expression* で使用できます。  
  
 プリプロセッサは、見つかったいずれかの *text* を選択して、後続の処理に使用します。  *text* で指定されるブロックは、テキストのシーケンスです。  複数行にまたがる場合があります。  通常、*text* はコンパイラまたはプリプロセッサに対して意味を持つプログラム テキストです。  
  
 プリプロセッサは選択した *text* を処理し、それをコンパイラに渡します。  *text* にプリプロセッサ ディレクティブが含まれている場合、プリプロセッサでそれらのディレクティブが実行されます。  プリプロセッサによって選択されたテキスト ブロックだけがコンパイルされます。  
  
 プリプロセッサは、`#if` または `#elif` ディレクティブに続く定数式を、true \(ゼロ以外\) の定数式が見つかるまで評価することで、1 つの *text* 項目を選択します。  プリプロセッサは、対応する `#elif`、`#else`、または `#endif` までのすべてのテキストを \(**\#** で始まる他のプリプロセッサ ディレクティブも含めて\) 選択します。  
  
 見つかった *constant\-expression* がすべて false であるか、または `#elif` ディレクティブが存在しない場合、プリプロセッサは `#else` 句の後のテキスト ブロックを選択します。  `#else` 句が省略され、`#if` ブロック内の *constant\-expression* のすべてのインスタンスが false の場合、テキスト ブロックは選択されません。  
  
 *constant\-expression* は、次のような追加の制限がある整数定数式です。  
  
-   式は、整数型である必要があり、整数定数、文字定数、**defined** 演算子のみ含めることができます。  
  
-   この式は `sizeof` または型キャスト演算子を使用できません。  
  
-   ターゲット環境は整数のすべての範囲を表現できるとは限りません。  
  
-   `int` 型は **long** 型と同じ型、`unsigned int` は `unsigned long` と同じ型と解釈されます。  
  
-   トランスレーターは、ターゲット環境とは別のコード値のセットに文字定数を翻訳できます。  ターゲット環境のプロパティを調べるには、ターゲット環境向けにビルドされたアプリケーションで LIMITS.H からマクロの値を確認します。  
  
-   この式は、環境に関する照会を実行できないように、ターゲット コンピューターの実装の詳細から分離しておく必要があります。  
  
 **定義された**プリプロセッサ演算子は、次の構文に示すように、特別な定数式で使用できます。  
  
 defined\( `identifier` \)  
  
 defined `identifier`  
  
 この定数式は *identifier* がそのとき定義されている場合は true \(ゼロ以外\) と見なされます。それ以外の場合、条件は false \(0\) です。  空のテキストとして定義された識別子は、定義されていると見なされます。  **defined** ディレクティブは、`#if` と `#elif` ディレクティブで使用することができ、これ以外の場所では使用できません。  
  
 次の例では、`#if` と `#endif` のディレクティブが、3 つの関数呼び出しの 1 つに対するコンパイルを制御します。  
  
```  
#if defined(CREDIT)  
    credit();  
#elif defined(DEBIT)  
    debit();  
#else  
    printerror();  
#endif  
```  
  
 `credit` の関数呼び出しは、`CREDIT` 識別子が定義されている場合、コンパイルされます。  `DEBIT` 識別子が定義されている場合、`debit` の関数呼び出しがコンパイルされます。  どちらの識別子も定義されていない場合、`printerror` の呼び出しがコンパイルされます。  `CREDIT` と `credit` は、大文字小文字が異なるため、C および C\+\+ で別々の識別子になることに注意してください。  
  
 次の例の条件付きコンパイル ステートメントは、`DLEVEL` というシンボリック定数が定義済みとします。  
  
```  
#if DLEVEL > 5  
    #define SIGNAL  1  
    #if STACKUSE == 1  
        #define STACK   200  
    #else  
        #define STACK   100  
    #endif  
#else  
    #define SIGNAL  0  
    #if STACKUSE == 1  
        #define STACK   100  
    #else  
        #define STACK   50  
    #endif  
#endif  
#if DLEVEL == 0  
    #define STACK 0  
#elif DLEVEL == 1  
    #define STACK 100  
#elif DLEVEL > 5  
    display( debugptr );  
#else  
    #define STACK 200  
#endif  
```  
  
 最初の `#if` ブロックには、`#if`、`#else`、`#endif` ディレクティブの 2 セットが入れ子になっています。  最初のセットのディレクティブは、`DLEVEL > 5` が true の場合にのみ処理されます。  そうでない場合は、\#**else** の後のステートメントが処理されます。  
  
 2 つ目のブロックでは、`#elif` ディレクティブと `#else` ディレクティブを使用して、`DLEVEL` の値に基づいて 4 つの選択肢のいずれかが選択されるようにしています。  `DLEVEL` の定義により、定数 `STACK` は 0、100、または 200 に設定されます。  `DLEVEL` が 5 より大きい場合、次のステートメントがコンパイルされます。  
  
```  
#elif DLEVEL > 5  
display(debugptr);  
```  
  
 この場合、`STACK` は定義されません。  
  
 条件付きコンパイルの一般的な用途は、同じヘッダー ファイルの多重インクルードを防ぐことです。  C\+\+ では、クラスをヘッダー ファイルで定義することが多いため、多重定義を防ぐために次のようなコンストラクターを使用できます。  
  
```  
/*  EXAMPLE.H - Example header file  */  
#if !defined( EXAMPLE_H )  
#define EXAMPLE_H  
  
class Example  
{  
...  
};  
  
#endif // !defined( EXAMPLE_H )  
```  
  
 前のコードは、シンボリック定数 `EXAMPLE_H` が定義されているかどうかを確認します。  定義されている場合、ヘッダー ファイルは既にインクルードされており、再処理する必要はありません。  定義されていない場合、EXAMPLE.H が処理されてから、`EXAMPLE_H` が処理済みとマークされます。  
  
## 参照  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)
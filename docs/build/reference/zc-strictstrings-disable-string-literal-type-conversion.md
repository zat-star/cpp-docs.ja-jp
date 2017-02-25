---
title: "/Zc:strictStrings (文字列リテラル型の変換の無効化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:strictStrings"
  - "strictStrings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc コンパイラ オプション (C++)"
  - "/Zc:strictStrings"
  - "strictStrings"
  - "Zc コンパイラ オプション (C++)"
  - "-Zc コンパイラ オプション (C++)"
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /Zc:strictStrings (文字列リテラル型の変換の無効化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された場合、コンパイラは、文字列リテラルを使用して初期化されたポインターに対して `const` 修飾による標準への厳密な準拠を要求します。  
  
## 構文  
  
```  
/Zc:strictStrings[-]  
```  
  
## 解説  
 **\/Zc:strictStrings** が指定されると、コンパイラは、文字列リテラルに標準 C\+\+ の `const` 修飾を \(宣言によって、型 "`const` `char` の配列" または "`const` `wchar_t` の配列" として\) 強制します。  文字列リテラルは変更不可であり、文字列リテラルの内容を変更しようとすると、実行時にアクセス違反エラーが発生します。  文字列ポインターは `const` として宣言して文字列リテラルで初期化するか、明示的な `const_cast` を使用して非 `const` ポインターを初期化する必要があります。  **\/Zc:strictStrings\-** が指定されている場合、または既定では、文字列リテラルで初期化された文字列ポインターに対して、コンパイラは標準 C\+\+ の `const` 修飾を強制しません。  
  
 **\/Zc:strictStrings** オプションは、不適切なコードのコンパイルを防ぐために使用します。  この例では、単純な宣言エラーが実行時のクラッシュを招くことを示しています。  
  
```cpp  
// strictStrings_off.cpp  
// compile by using: cl /W4 strictStrings_off.cpp  
int main() {  
   wchar_t* str = L"hello";  
   str[2] = L'a'; // run-time error: access violation  
}  
```  
  
 **\/Zc:strictStrings** を有効にした場合は、同じコードで `str` 宣言エラーが報告されます。  
  
```cpp  
// strictStrings_on.cpp  
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp  
int main() {  
   wchar_t* str = L"hello"; // error: Conversion from string literal   
   // loses const qualifier  
   str[2] = L'a';   
}  
```  
  
 `auto` を使用して文字列ポインターを宣言すると、正しい `const` ポインター型宣言がコンパイラによって作成されます。  `const` ポインターの内容を変更しようとすると、コンパイラによってエラーとして報告されます。  
  
> [!NOTE]
>  [!INCLUDE[cpp_dev12_long](../../build/reference/includes/cpp_dev12_long_md.md)] の標準 C\+\+ ライブラリでは、デバッグ ビルドでの **\/Zc:strictStrings** コンパイラ オプションがサポートされていません。  ビルド出力で複数の [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md) エラーが発生している場合は、このことが原因である可能性があります。  
  
 Visual C\+\+ の準拠に関する問題の詳細については、「[非標準動作](../Topic/Nonstandard%20Behavior.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  `/Zc:strictStrings` が含まれるように **"追加オプション"** プロパティを変更し、**\[OK\]** をクリックします。  
  
## 参照  
 [\/Zc \(準拠\)](../../build/reference/zc-conformance.md)
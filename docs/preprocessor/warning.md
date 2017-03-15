---
title: "warning | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "warning_CPP"
  - "vc-pragma.warning"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pop warning プラグマ"
  - "プラグマ, 警告"
  - "push pragma warning"
  - "warning pragma"
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# warning
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンパイラの警告メッセージの動作の選択的な変更を有効にします。  
  
## 構文  
  
```  
  
      #pragma warning(   
      warning-specifier  
       :   
      warning-number-list [; warning-specifier : warning-number-list...] )  
#pragma warning( push[ ,n ] )  
#pragma warning( pop )  
```  
  
## 解説  
 次の警告指定子パラメーターを使用できます。  
  
|警告指定子|説明|  
|-----------|--------|  
|`1, 2, 3, 4`|指定された警告に特定のレベルを適用します。  これは、既定で無効になっている指定された警告も有効にします。|  
|`default`|警告の動作を既定値にリセットします。  これは、既定で無効になっている指定された警告も有効にします。  警告は、既定の文書化されたレベルで生成されます。<br /><br /> 詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。|  
|`disable`|指定した警告メッセージを発行しません。|  
|`error`|指定した警告をエラーとして報告します。|  
|`once`|指定したメッセージを 1 回だけ表示します。|  
|`suppress`|プラグマの現在の状態をスタックにプッシュし、次の行に対して指定された警告を無効にします。次に、プラグマの状態がリセットされるように警告スタックをポップします。|  
  
 次のコード ステートメントは、`warning-number-list` パラメーターが複数の警告の数を含むことができること、および複数の `warning-specifier` パラメーターが同じプラグマ ディレクティブで指定できることを示しています。  
  
```  
#pragma warning( disable : 4507 34; once : 4385; error : 164 )  
```  
  
 これは、次のコードと機能的に同等です。  
  
```  
// Disable warning messages 4507 and 4034.  
#pragma warning( disable : 4507 34 )  
  
// Issue warning 4385 only once.  
#pragma warning( once : 4385 )  
  
// Report warning 4164 as an error.  
#pragma warning( error : 164 )  
```  
  
 コンパイラは、0 と 999 の間の任意の警告番号に 4000 を追加します。  
  
 コードの生成に関連する 4700 ～ 4999 の警告番号の場合、コンパイラで関数の左中かっこが検出された場合の有効な警告の状態は、他の関数に対しても有効になります。  関数で `warning` プラグマを使用して番号が 4699 より大きい警告の状態を変更すると、その関数が終了した後でのみ有効になります。  次の例では、コード生成の警告メッセージを無効にし、これを復元するための、`warning` プラグマの正しい配置を示します。  
  
```  
// pragma_warning.cpp  
// compile with: /W1  
#pragma warning(disable:4700)  
void Test() {  
   int x;  
   int y = x;   // no C4700 here  
   #pragma warning(default:4700)   // C4700 enabled after Test ends  
}  
  
int main() {  
   int x;  
   int y = x;   // C4700  
}  
```  
  
 関数本体全体において、`warning` プラグマの最後の設定が関数全体に対して有効になることに注意してください。  
  
## プッシュおよびポップ  
 `warning` プラグマは、次の構文もサポートします。  
  
 `#pragma warning(` `push` \[ `,``n` \] `)`  
  
 `#pragma warning(` `pop )`  
  
 `n` は警告レベル \(1 ～ 4\) を表します。  
  
 プラグマ `warning( push )` は、警告ごとに現在の警告状態を格納します。  プラグマ `warning( push,` `n``)`  は、警告ごとに現在の状態を保存し、グローバル警告レベルを `n` に設定します。  
  
 プラグマ `warning( pop )` は、スタックにプッシュされた最後の警告状態をポップします。  `push` と `pop` の間の警告状態に行った変更は元に戻されます。  次の例について考えます。  
  
```  
#pragma warning( push )  
#pragma warning( disable : 4705 )  
#pragma warning( disable : 4706 )  
#pragma warning( disable : 4707 )  
// Some code  
#pragma warning( pop )   
```  
  
 このコードの最後に、`pop` は、すべての警告の状態をコードの開始時の状態に復元します \(4705、4706、および 4707 が含まれます\)。  
  
 ヘッダー ファイルを作成するときは、`push` および `pop` を使用して、ユーザーが行った警告状態の変更がヘッダーによるコンパイルの正常な実行を妨げないようにできます。  `push` はヘッダーの先頭で、`pop` は末尾で使用します。  たとえば、警告レベル 4 で正しくコンパイルされていないヘッダーがある場合は、次のコードで警告レベルを 3 に変更し、ヘッダーの終わりで元の警告レベルを復元します。  
  
```  
#pragma warning( push, 3 )  
// Declarations/definitions  
#pragma warning( pop )   
```  
  
 警告を非表示にする場合に役立つコンパイラ オプションの詳細については、「[\/FI](../Topic/-FI%20\(Name%20Forced%20Include%20File\).md)」および「[\/w](../build/reference/compiler-option-warning-level.md)」を参照してください。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
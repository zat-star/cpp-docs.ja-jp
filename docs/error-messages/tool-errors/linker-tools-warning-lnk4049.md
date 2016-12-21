---
title: "リンカー ツールの警告 LNK4049 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4049"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4049"
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ローカルで定義されたシンボル 'symbol' がインポートされました。  
  
 指定されたシンボルに対して、プログラムからのエクスポートとプログラムへのインポートが同時に行われています。  
  
 この警告は、特定のシンボルが `__declspec(dllexport)` ストレージ クラス属性を使って宣言されているオブジェクト ファイルと、そのシンボルを `__declspec(dllimport)` 属性で参照する別のオブジェクト ファイルとをリンカーで関連付けようとした場合に生成されます。  
  
 警告 LNK4049 は、[リンカー ツールの警告 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md) をより一般化した警告です。  インポート対象となるシンボルの参照元をリンカーが確認できなかった場合に、警告 LNK4049 が生成されます。  
  
 LNK4217 ではなく LNK4049 が生成される一般的な事例を次に示します。  
  
-   [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) オプションを使用してインクリメント リンクを実行した場合。  
  
-   [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) オプションを使用してプログラム全体の最適化を実行した場合。  
  
 LNK4049 を解決するには、以下のいずれかの操作を実行します。  
  
-   LNK4049 の原因となったシンボルの事前の宣言から `__declspec(dllimport)` の名前宣言を削除します。  バイナリ イメージからシンボルを検索するには、**DUMPBIN** ユーティリティを使用します。  **DUMPBIN \/SYMBOLS** スイッチを指定すると、イメージの COFF シンボル テーブルが表示されます。  **DUMPBIN** ユーティリティの詳細については、「[DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)」を参照してください。  
  
-   インクリメント リンクおよびプログラム全体の最適化を一時的に無効にします。  アプリケーションを再コンパイルすると、インポート対象となるシンボルの参照元の関数名を含んだ警告 LNK4217 が生成されます。  インポート対象のシンボルから `__declspec(dllimport)` 宣言を削除し、必要に応じてインクリメント リンクまたはプログラム全体の最適化を有効にします。  
  
 最終的に生成されるコードは正常に動作しますが、インポートされた関数を呼び出すためのコードは、関数を直接呼び出す場合と比べて効率が落ちます。  [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) オプションを使用してコンパイルした場合、この警告は表示されません。  
  
 データをインポートしたりエクスポートしたりするための宣言の詳細については、「[dllexport、dllimport](../../cpp/dllexport-dllimport.md)」を参照してください。  
  
## 使用例  
 次の 2 つのモジュールをリンクすると、LNK4049 が生成されます。  1 つ目のモジュールでは、エクスポートされた関数を 1 つ含むオブジェクト ファイルが生成されます。  
  
```  
// LNK4049a.cpp  
// compile with: /c  
  
__declspec(dllexport) int func()   
{  
   return 3;  
}  
```  
  
## 使用例  
 2 つ目のモジュールでは、この関数 \(`main` 関数内\) の呼び出しと共に、1 つ目のモジュールでエクスポートされた関数の事前の宣言を含むオブジェクト ファイルが生成されます。  このモジュールを 1 つ目のモジュールとリンクすると、LNK4049 が生成されます。  `__declspec(dllimport)` 宣言を削除すると、この警告が解消されます。  
  
```  
// LNK4049b.cpp  
// compile with: /link /WX /LTCG LNK4049a.obj  
// LNK4049 expected  
  
__declspec(dllimport) int func();  
// try the following line instead  
// int func();  
  
int main()  
{  
   return func();  
}  
```  
  
## 参照  
 [リンカー ツールの警告 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)   
 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)
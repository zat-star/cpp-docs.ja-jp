---
title: "-Zc: 自動 (変数の型の推測) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc:auto
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd2f0ff353e1243685c94da0c28f29e810b2a9ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (変数の型の推測)
**/Zc:auto [-]**コンパイラ オプションを使用する方法をコンパイラに指示、 [auto キーワード](../../cpp/auto-keyword.md)変数を宣言します。 既定のオプションを指定する場合**/Zc:auto**コンパイラには、その初期化式から宣言された変数の型があると推測します。 指定した場合**/Zc:auto-**コンパイラは自動ストレージ クラスに変数を割り当てます。  
  
## <a name="syntax"></a>構文  
  
```  
/Zc:auto[-]  
```  
  
## <a name="remarks"></a>コメント  
 C++ 基準は、`auto` キーワードの元の意味と改定された意味を定義します。 前に[!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)]、自動ストレージ クラスで変数を宣言するキーワードです。 つまり、変数を持つローカルな有効期間。 以降で[!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)]キーワードには、宣言の初期化式から変数の型があると推測します。 使用して、 **/Zc:auto [-]**の元のまたは改訂された意味を使用するようにコンパイラに指示するコンパイラ オプション、`auto`キーワード。  
  
 `auto` キーワードの使用が現在のコンパイラ オプションと矛盾している場合、コンパイラは適切な診断メッセージを発行します。 詳細については、次を参照してください。 [auto キーワード](../../cpp/auto-keyword.md)です。 Visual C の準拠の問題に関する詳細については、次を参照してください。[非標準動作](../../cpp/nonstandard-behavior.md)です。  
  
### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**構成プロパティ**ノード。  
  
3.  クリックして、 **C/C++**ノード。  
  
4.  クリックして、**コマンドライン**ノード。  
  
5.  追加**/Zc:auto**または**/Zc:auto-**を**追加オプション:**ウィンドウです。  
  
## <a name="see-also"></a>参照  
 [/Zc (準拠)](../../build/reference/zc-conformance.md)   
 [auto キーワード](../../cpp/auto-keyword.md)
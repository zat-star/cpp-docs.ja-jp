---
title: "ワイルドカード引数の展開 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: b8444a15e8f0fb9a8e4322f1bb2001b19d38eec1
ms.lasthandoff: 02/24/2017

---
# <a name="expanding-wildcard-arguments"></a>ワイルドカード引数の展開
**Microsoft 固有の仕様**  
  
 C プログラムを実行する際、コマンド ラインのファイル名引数とパス引数の指定に、2 つのワイルドカード (疑問符 (?) およびアスタリスク (*)) のいずれかを使用できます。  
  
 既定では、ワイルドカードはコマンドラインの引数では展開されません。 setargv.obj または wsetargv.obj ファイルとリンクしてワイルドカードを展開し、標準の引数ベクターの `argv` 読み込みルーチンをワイルドカードを展開するバージョンと置き換えることができます。 プログラムが `main` 関数を使用している場合は、setargv.obj とリンクします。 プログラムが `wmain` 関数を使用している場合は、wsetargv.obj とリンクします。 これら両方の動作は同等です。  
  
 setargv.obj または wsetargv.obj とリンクするには、 **/link** オプションを使用します。 例:  
  
 **cl example.c /link setargv.obj**  
  
 ワイルドカードはオペレーティング システム コマンドと同じように展開されます (ワイルドカードの使用経験がない場合は、オペレーティング システムのユーザー ガイドを参照)。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [リンク オプション](../c-runtime-library/link-options.md)   
 [main 関数とプログラム実行](../c-language/main-function-and-program-execution.md)

---
title: "ワイルドカードの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- _setargv function
- command line, processing arguments
- command line, wildcards
- command-line wildcards
- question mark, wildcard
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 779a788cae6523a48a82694e55edf3c1da5519d7
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="wildcard-expansion"></a>ワイルドカードの展開
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 コマンド ラインでファイル名とパスの引数を指定するときに、ワイルドカード (疑問符 (?) およびアスタリスク (*)) を使用できます。  
  
 コマンドライン引数はというルーチンによって処理される**_setargv** (または**_wsetargv**ワイド文字環境で)、既定では展開されませんワイルドカード、で個別の文字列に`argv`文字列配列。 参照してワイルドカードの展開を有効にする方法の詳細については、[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)です。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [main: プログラムの起動](../cpp/main-program-startup.md)

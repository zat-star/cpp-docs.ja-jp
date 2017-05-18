---
title: "assert 関数によって出力される診断 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
caps.latest.revision: 6
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3ea5d1b75fbec63deb68e13fcce6e77369e39e1c
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert 関数によって出力される診断
**ANSI 4.2** **assert** 関数が印刷する診断と関数の終了動作  
  
 **assert** 関数は診断メッセージを表示し、式が false (0) の場合に **abort** ルーチンを呼び出します。 診断メッセージにフォームがあります  
  
 **アサーションに失敗しました**: *expression***, ファイル** *filename***, 行** *linenumber*  
  
 ここで、filename はソース ファイルの名前であり、linenumber はソース ファイルで失敗したアサーションの行番号です。 式が true の場合 (ゼロ以外)、アクションは発生しません。  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ関数](../c-language/library-functions.md)
